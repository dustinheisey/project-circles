<template>
  <div id="app">
    <h1 class="heading" id="heading">{{heading}}</h1>
    <div class="item img-2"><img src="./assets/circle.jpg" class="img" id="1" alt="Circle"></div>
    <div class="item img-1"><img src="./assets/circles.jpg" class="img" id="2" alt="Circles"></div>
    <div class="item img-9"><img src="./assets/triangle.jpg" class="img" id="3" alt="Triangle"></div>
    <div class="item img-11"><img src="./assets/triangles.jpg" class="img" id="4" alt="Triangles"></div>
    <div class="item img-4"><img src="./assets/square.jpg" class="img" id="5" alt="Square"></div>
    <div class="item img-10"><img src="./assets/squares.jpg" class="img" id="6" alt="Squares"></div>
    <div class="item img-3"><img src="./assets/pentagon.jpg" class="img" id="7" alt="Pentagon"></div>
    <div class="item img-8"><img src="./assets/pentagons.jpg" class="img" id="8" alt="Pentagons"></div>
    <div class="item img-7"><img src="./assets/hexagon.jpg" class="img" id="9" alt="Hexagon"></div>
    <div class="item img-6"><img src="./assets/hexagons.jpg" class="img" id="10" alt="Hexagons"></div>
    <div class="item img-5"><img src="./assets/octagon.jpg" class="img" id="11" alt="Octagon"></div>
    <div class="item img-12"><img src="./assets/octagons.jpg" class="img" id="12" alt="Octagons"></div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      headings: [
        "Circle",
        "Circles",
        "Triangle",
        "Triangles",
        "Square",
        "Squares",
        "Pentagon",
        "Pentagons",
        "Hexagon",
        "Hexagons",
        "Octagon",
        "Octagons"
      ],
      heading: "Circles"
    };
  },
  created() {
    setInterval(() => {
      this.heading = this.headings[
        Math.floor(this.headings.length * Math.random())
      ];
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
    "f f f f f f c c"
    "f f f f f f c c"
    "f f f f f f d d"
    "f f f f f f d d"
    "f f f f f f e e"
    "f f f f f f e e"
    "l l l l m m m m"
    "l l l l m m m m"
    "l l l l m m m m"
    "l l l l m m m m"
    "g g h h h h k k"
    "g g h h h h k k"
    "j j h h h h i i"
    "j j h h h h i i";

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
