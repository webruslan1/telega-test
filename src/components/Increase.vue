<template name="component-name">
  <section class="increase">
    <div class="increase-content">
      <h2 class="mb-15">{{ this.title }}</h2>
      <p :class="{ 'small-text': isBig }" class="increase-content__text">
        It is a long established fact that a reader will be distracted by the
        readable content of a page when looking at its layout. The point of
        using Lorem Ipsum is that it has a more-or-less normal distribution of
        letters,
      </p>
    </div>
    <div
      ref="increaseImg"
      :class="{ big: isBig }"
      @mouseover="isBig = true"
      @mouseleave="isBig = false"
      class="increase-img"
    ></div>
  </section>
</template>


<script>
export default {
  name: "Increase",
  data() {
    return {
      isBig: false,
    };
  },
  props: {
    title: String,
  },
  methods: {
    hoverImg() {
      console.log(this.$refs);
    },
    unHoverImg() {
      console.log("unhover");
    },
  },
};
</script>

<style>
.increase {
  display: flex;
  justify-content: center;
}
.increase-content {
  margin-right: 15px;
}
.increase-content__text {
  width: 174px;
  transition: 800ms;
}
.increase-img {
  width: 130px;
  height: 130px;
  background: #fff;
  transition: 800ms;
}
.small-text {
  transition: 800ms;
  width: 155px;
}

@media (max-width: 360px) {
  .increase {
    flex-direction: column;
    margin: 0 auto;
    text-align: center;
  }
  .increase-content {
    margin-right: 15px;
    order: 1;
  }
  .increase-img {
    order: 0;
    width: 130px;
    height: 130px;
    margin: 0 auto;
    margin-bottom: 20px;
    background: #fff;
    transition: 800ms;
  }
  .increase-content__text {
    margin: 0 auto;
    width: 220px;
  }
}

.big {
  width: 150px;
  transition: 800ms;
}
</style>