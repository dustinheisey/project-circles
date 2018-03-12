<template>
  <div id="app">
    <h1 class="heading" id="heading">{{heading}}</h1>
    <div v-for="(item, index) in art" :key="index" class="item" :class="'img-' + (index + 1)">
      <a :href="item.src" download>
        <img :src="item.src" :alt="item.heading">
      </a>
    </div>
  </div>
</template>

<script>
const path = "../static/assets/";
export default {
  name: "app",
  data() {
    return {
      heading: "Circles",
      art: [
        { heading: "circle", src: path + "circle.jpg" },
        { heading: "circles", src: path + "circles.jpg" },
        { heading: "triangle", src: path + "triangle.jpg" },
        { heading: "triangles", src: path + "triangles.jpg" },
        { heading: "square", src: path + "square.jpg" },
        { heading: "squares", src: path + "squares.jpg" },
        { heading: "pentagon", src: path + "pentagon.jpg" },
        { heading: "pentagons", src: path + "pentagons.jpg" },
        { heading: "hexagon", src: path + "hexagon.jpg" },
        { heading: "hexagons", src: path + "hexagons.jpg" },
        { heading: "octagon", src: path + "octagon.jpg" },
        { heading: "octagons", src: path + "octagons.jpg" }
      ]
    };
  },
  beforeMount() {
    this.art.sort((a, b) => {
      return 0.5 - Math.random();
    });
  },
  created() {
    setInterval(() => {
      this.heading = this.art[
        Math.floor(this.art.length * Math.random())
      ].heading;
    }, 3000);
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "lato", sans-serif;
  font-size: 10px;
  background-color: #fff;
  color: #00d8d6;
  padding: 2%;
}

#app {
  max-width: 100%;
  display: grid;

  grid-template-rows: repeat(23, 12vmin);
  grid-template-columns: repeat(8, 12vmin);

  grid-template-areas:
    "a a a a a a a a"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "b b b b b b b b"
    "c c c c c c d d"
    "c c c c c c d d"
    "c c c c c c e e"
    "c c c c c c e e"
    "c c c c c c f f"
    "c c c c c c f f"
    "g g g g h h h h"
    "g g g g h h h h"
    "g g g g h h h h"
    "g g g g h h h h"
    "i i k k k k l l"
    "i i k k k k l l"
    "j j k k k k m m"
    "j j k k k k m m";

  align-content: center;
  justify-content: center;
  grid-gap: 4vmin;
}

@media screen and (max-width: 900px) and (min-width: 600px) {
  .site {
    grid-template-rows: repeat(23, 8vmin);
    grid-template-columns: repeat(8, 8vmin);
  }
}

@media screen and (max-width: 599px) {
  .site {
    grid-template-rows: repeat(23, 7vmin);
    grid-template-columns: repeat(8, 7vmin);
  }
}

.item {
  border: 1rem solid #00d8d6;
  -webkit-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
  -moz-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
  box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
}

@media screen and (min-width: 1800px) {
  .item {
    border: 2rem solid #00d8d6;
  }
}

@media screen and (max-width: 599px) {
  .item {
    border: 0.5rem solid #00d8d6;
  }
}

.item:hover {
  -webkit-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.5);
  box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.5);
}

img {
  width: 100%;
}

.heading {
  text-transform: uppercase;
  font-weight: 900;
  font-size: 10vmin;
  text-align: center;
  grid-area: a;
  align-self: center;
}

@media screen and (max-width: 599px) {
  .heading {
    font-size: 7vmin;
  }
}

.img-1 {
  grid-area: b;
}

.img-2 {
  grid-area: c;
}

.img-3 {
  grid-area: d;
}

.img-4 {
  grid-area: e;
}

.img-5 {
  grid-area: f;
}

.img-6 {
  grid-area: g;
}

.img-7 {
  grid-area: h;
}

.img-8 {
  grid-area: i;
}

.img-9 {
  grid-area: j;
}

.img-10 {
  grid-area: k;
}

.img-11 {
  grid-area: l;
}

.img-12 {
  grid-area: m;
}
</style>
