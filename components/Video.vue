<template>
  <div class="video" :class="{ active }">
    <video controls :poster="thumbnail" ref="video">
      <source
        :src="'https://pub-aff0fbcc703d4dc28e7f8d3ff764b467.r2.dev/' + src"
        type="video/mp4"
      />
    </video>
  </div>
</template>

<script setup>
const props = defineProps({
  src: String,
  thumbnail: String,
});

const video = ref(null);

const active = ref(false);
let observer = null;

const handleIntersect = (entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      active.value = true;

      observer.unobserve(video.value);
    }
  });
};

onMounted(() => {
  observer = new IntersectionObserver(handleIntersect, {
    threshold: 0.3,
  });
  observer.observe(video.value);
});
</script>

<style lang="scss">
.video {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  video {
    width: 100%;
    height: 100%;
  }
}
</style>
