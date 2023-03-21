<template>
  <div class="testview">
    <h1>{{ title }}</h1>
    <div v-html="htmlTag"></div>
    <div class="content">
      <figure class="imgBox" v-for="(v, k) in data" :key="k">
        <img :src="v.url" alt="" />
        <p>{{ v.id }}</p>
      </figure>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "Photo List",
      htmlTag: "존나어렵다!!!!!!!주르륵",
      data: [
        { id: "이미지1", url: "../img1.jpg" },
        { id: "이미지2", url: "../img2.jpg" },
        { id: "이미지3", url: "../img3.jpg" },
        { id: "이미지4", url: "../img4.jpg" },
        { id: "이미지5", url: "../img5.jpg" },
        { id: "이미지6", url: "../img6.jpg" },
      ],
    };
  },
};
</script>
<style lang="scss">
.testview {
  max-width: 1400px;
  margin: 0 auto;
}
.content {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-content: center;
  .imgBox {
    width: 300px;
    height: 400px;
    img {
      width: 100%;
      height: 280px;
    }
  }
}
</style>
