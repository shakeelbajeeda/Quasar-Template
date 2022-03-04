<template>
  <q-carousel swipeable animated v-model="slide" thumbnails infinite>
    <q-carousel-slide
      v-for="image in images"
      :key="image"
      :name="image"
      :img-src="image"
      title="shakeel ahmad"
    />
  </q-carousel>
</template>

<script>
export default {
  props: ["images"],
  data() {
    return {
      slide: this.images[0],
    };
  },
};
</script>
