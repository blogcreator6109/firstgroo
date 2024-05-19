<template>
  <div class="youtube" :class="{ active }" ref="video">
    <iframe
      :src="'https://www.youtube.com/embed/' + value"
      title="First Groo Video"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
  </div>
</template>

<script setup>
defineProps({
  value: String,
});

const video = ref(null);

const active = ref(false);

const handleIntersect = (entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      active.value = true;

      entry.unobserve(video.value);
    }
  });
};

onMounted(() => {
  const observer = new IntersectionObserver(handleIntersect, {
    threshold: 0.3,
  });
  observer.observe(video.value);
});
</script>

<style lang="scss">
.youtube {
  width: 100%;
  aspect-ratio: 16 / 9;

  iframe {
    width: 100%;
    height: 100%;
  }
}
</style>
