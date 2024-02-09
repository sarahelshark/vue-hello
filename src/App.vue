<script>
export default {
  name: "App",
  data() {
    return {
      message: "Hello world",
      image: "https://picsum.photos/200/300",
      activeImage: 0,
      slider: {
        name: "Mandalorian",
        images: [
          "https://image.tmdb.org/t/p/original/9zcbqSxdsRMZWHYtyCd1nXPr2xq.jpg",

          "https://image.tmdb.org/t/p/original/aZ4fmjMUAhS6PWhVLDDfT0RAdNe.jpg",

          "https://image.tmdb.org/t/p/original/p7fwOnlxYYlB4A8U2b0JfX21Rr1.jpg",

          "https://image.tmdb.org/t/p/original/qruRhG6jE5M8lWnW1AGOBxtdmCO.jpg",

          "https://image.tmdb.org/t/p/original/lMu3y10KgIYtXFPeCMim3D8iihV.jpg",
        ],
        cathegory: "Action",
        length: 40,
      },
    };
  },
  mounted() {
    console.log(this.slider);
  },
  methods: {
    prev() {
      console.log("prev");
      this.activeImage--

      if(this.activeImage<0){
        this.activeImage=this.slider.images.length - 1
      }
    },
    next() {
      console.log("next");
      this.activeImage++

      if(this.activeImage > this.slider.images.length - 1){
        this.activeImage=0;
      }
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>{{ slider.name }}</h1>

    <div class="slides">
      <img :src="slider.images[activeImage]" alt="random picture" />
    </div>

    <div class="navigator">
      <button class="prev" @click="prev">prev</button>

      <button class="next" @click="next">next</button>
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

img {
  max-width: 100%;
}

.container {
  width: 70%;
  max-width: 1176px;
  margin: auto;
}

.row {
  display: flex;
  flex-wrap: wrap;
  margin: 0 - 1rem;
}

.col {
  width: auto;
  padding: 1rem;
  flex-basis: auto;
}

.navigator{
  display: flex;
  justify-content: space-between;
}
</style>
