<template>
  <div :class="className"
      ref="imgContainer"
  >
    <picture>
      <source
        type="image/webp"
        :srcset="webpSrcset"
      >
      <img v-show="imgLoaded"
        :width="imgData.width"
        :height="imgData.height"
        :alt="imgData.alt"
        :src="src"
        :srcset="srcset"
        @load="onImgLoad"
      >
    </picture>
  </div>
</template>

<script>
  export default {
    data() {
      return {
          imgLoaded: false,
      }
    },
    props: {
      className: String,
      imgData: Object,
    },
    methods: {
      onImgLoad() {
        this.$refs.imgContainer.style.backgroundColor = '#ffffff00';
        this.$data.imgLoaded = true;
      }
    },
    computed: {
      webpSrcset() {
        return `
          /images/${this.imgData.name}@1x.webp 1x,
          /images/${this.imgData.name}@2x.webp 1.5x,
          /images/${this.imgData.name}@2x.webp 2x,
          /images/${this.imgData.name}@2x.webp 3x
        `
      },
      src() {
        return `/images/${this.imgData.name}@1x.png`
      },
      srcset() {
        return `
          /images/${this.imgData.name}@2x.png 1.5x,
          /images/${this.imgData.name}@2x.png 2x,
          /images/${this.imgData.name}@2x.png 3x
        `
      }
    }
  }
</script>