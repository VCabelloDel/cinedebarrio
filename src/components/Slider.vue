<script>
export default {
  props: ["ArrayMovies"],
  data() {
    return {
      arraySlider: this.ArrayMovies,
      index: 0,
    };
  },
  computed: {
    getURL() {
      return `url("../../public/${this.arraySlider[this.index]}")`;
    },
  },
  methods: {
    SwitchImage(value) {
      this.index = value;
    },
  },
  watch: {
    arraySlider: {
      handler() {
        this.index = this.arraySlider.length - 1;
      },
      deep: true,
    },
  },
};
</script>
 
<template>
  <div class="slider">
    <div :style="{ backgroundImage: getURL }" class="movie">
      <div class="main-div">
        <nav>
          <ul class="menu">
            <li
              class="slide-fwd-center"
              v-for="(_, index) in arraySlider"
              :key="index"
              @click="SwitchImage(index)"
              href=""
            >
              <span class="indexmovie">{{ index + 1 }}</span>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </div>
</template>
 
<style scoped>
.movie {
  background-repeat: no-repeat;
  background-size: cover;
  height: 600px;
  min-width: 80vw;
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
.flex {
  display: flex;
  justify-content: space-between;
}
.menu {
  display: flex;
  justify-content: center;
}
.indexmovie {
  color: red;
  font-size: 18px;
  font-weight: 700;
}
.menu li:hover {
  cursor: pointer;
  border: 3px solid #570000;
}

.menu li {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 3px solid red;
  text-decoration: none;
  background-color: rgba(255, 72, 0, 0);
  padding: 15px;
  margin-right: 2rem;
  width: 10px;
  height: 10px;
  border-radius: 100%;
  margin-bottom: 1.5rem;
}
</style>

// Hacer que el indice del array por defecto sea .length-1

