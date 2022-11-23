<template>
  <div></div>
</template>

<script>
export default {
  props: ['src', 'options'],
  data() {
    return {
      waveSurfer: {}
    };
  },
  async mounted() {
    let options = this.options;
    let wsOptions = Object.assign({ container: this.$el }, options);
    let WaveSurfer = (await import('wavesurfer.js')).default;
    this.waveSurfer = new WaveSurfer.create(wsOptions);
    await this.waveSurfer.load(this.src);
  },
  beforeDestroy() {
    this.waveSurfer.destroy();
  }
};
</script>

<style lang="css" scoped>
div {
  position: relative;
}
</style>
