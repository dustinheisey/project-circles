<template>
  <div id="app">
    <h1 class="heading" id="heading">{{heading}}</h1>
      <button class="btn btn-1" @click="showMore()">Show More</button>
      <button class="btn btn-2" @click="showLess()">Show Less</button>
      <button class="btn btn-3" @click="showAll()">Show All</button>
      <button class="btn btn-4" @click="randomOrder()">Random Order</button>
    <div v-for="(item, index) in art" :key="index" class="item" :class="'img-' + (index + 1)" v-if="index < numShown">
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
      ],
      numShown: 0
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
  },
  methods: {
    showMore() {
      if (this.numShown < 12) {
        this.numShown++;
      }
    },

    showLess() {
      if (this.numShown > 0) {
        this.numShown--;
      }
    },

    showAll() {
      this.numShown = 12;
    },

    randomOrder() {
      this.art.sort((a, b) => {
        return 0.5 - Math.random();
      });
    }
  }
};
</script>

<style lang="scss">
:root {
  --primary: #00d8d6;
  --primary-dark: #03c2bf;
  --secondary: #ffffff;
  --tertiary: #323232;
  --tertiary-dark: #232323;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "lato", sans-serif;
  font-size: 10px;
  background-color: #fff;
  color: var(--primary);
  padding: 2%;
}

#app {
  max-width: 100%;
  display: grid;

  grid-template-rows: repeat(24, 12vmin);
  grid-template-columns: repeat(8, 12vmin);

  grid-template-areas:
    "a a a a a a a a"
    "n n o o p p q q"
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
  border: 1rem solid var(--primary);
  -webkit-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
  -moz-box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
  box-shadow: 6px 17px 23px -7px rgba(0, 0, 0, 0.25);
  transition: all 0.5s;
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
  border-color: var(--primary-dark);
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

.btn {
  background-color: var(--tertiary);
  color: var(--secondary);
  border: none;
  word-wrap: none;
  height: 50%;
  width: 100%;
  border-radius: 1vh;
  justify-self: center;
  align-self: center;
  text-transform: uppercase;
  cursor: pointer;
  transition: 0.3s all;

  &:focus {
    outline: none;
  }

  &:hover {
    background-color: var(--tertiary-dark);
  }

  &-1 {
    grid-area: n;
  }

  &-2 {
    grid-area: o;
  }

  &-3 {
    grid-area: p;
  }

  &-4 {
    grid-area: q;
  }
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
