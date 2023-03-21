<template>
  <div class="home">
    <h1>hello, {{ title }}</h1>
    <div v-html="htmlTag"></div>
    <figure><img :src="imgUrl" /></figure>
    <div class="menu" :class="{ active: isActive }" @click="toggle">
      토글메뉴
    </div>
    <ul>
      <li v-for="(v, k) in data" :key="k">
        <!--name이 리액트만-->
        <!-- <p v-if="v.name == 'react'">{{ v.name }}</p> -->
        <!--name이 리액트만-->
        {{ v.name }}
      </li>
    </ul>
    <div class="ip">
      <input type="text" v-model="elInput[0]" />
      <input type="text" v-model="elInput[1]" />

      <button @click="result">확인</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data() {
    return {
      title: "world!",
      htmlTag: '<p style="color:red"> v-html </p>',
      imgUrl: require("../assets/img1.jpg"),
      isActive: true,
      data: [
        { id: 11, name: "react" },
        { id: 22, name: "vue" },
      ],

      elInput: ["", ""],
    };
  },
  methods: {
    result() {
      console.log(this.elInput);
    },
    toggle() {
      console.log(document.querySelector(".menu"));
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss">
/* #app{

} */
.menu {
  font-size: 3rem;
  &.active {
    color: red;
  }
}
img {
  width: 300px;
}
</style>
