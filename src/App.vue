<template>
  <div id="app">
    <div>
      <img
        :src="$options.imgUrl"
        :class="{
          'img-default-size': true,
          'img-shrunk-size': imageShrunk,
        }"
        @mouseover="shrinkImage"
        @mouseout="enlargeImage"
      />
    </div>
    <div class="np-credits">wwww.nightprogrammer.com</div>
  </div>
</template>

<script>
export default {
  name: "ImageShrink",
  created() {
    this.$options.imgUrl =
      "https://images.unsplash.com/photo-1658148900843-bf9d17c2ca2e";
  },
  data() {
    return {
      imageShrunk: false,
    };
  },
  methods: {
    enlargeImage() {
      this.imageShrunk = false;
    },
    shrinkImage() {
      this.imageShrunk = true;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}
.img-default-size {
  height: 300px;
  transition: all 0.2s;
}

.img-shrunk-size {
  height: 270px;
  transition: all 0.2s;
}

.np-credits {
  font-size: 12px;
  margin-bottom: 12px;
  color: #4b4b4b;
}
</style>