<template>
  <section>
    <h2 class="mb-20 tac">{{ this.title }}</h2>
    <transition-group name="header" mode="out-in" class="header__list">
      <div
        v-for="(item, key) in sortItems"
        :key="key"
        class="header__list-item"
      >
        <p class="header__list-text">{{ item.text }}</p>
        <div class="header__list-img"></div>
      </div>
    </transition-group>
    <div class="tac">
      <button @click="showAll">{{ button }}</button>
    </div>
  </section>
</template>


<script>
export default {
  name: "Header",
  data() {
    return {
      button: "show more",
      headerItems: [
        {
          text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
        },
        {
          text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
        },
        {
          text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
        },
        {
          text: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters,",
        },
      ],
      sortItems: null,
    };
  },
  mounted() {
    console.log(this.headerItems.slice(2));
    this.sortItems = this.headerItems.slice(2);
  },
  props: {
    title: String,
  },
  methods: {
    showAll() {
      this.sortItems =
        this.button == "hide" ? this.headerItems.slice(2) : this.headerItems;
      this.button = this.button == "hide" ? "show more" : "hide";
    },
  },
};
</script>

<style scoped>
.header__list-item {
  margin: 0 auto;
  display: flex;
  margin-bottom: 20px;
  justify-content: center;
  align-items: center;
}
.header__list-item:nth-child(even) .header__list-img {
  order: 0;
}
.header__list-item:nth-child(even) .header__list-text {
  order: 1;
  margin-right: 0;
  margin-left: 20px;
}

.header__list-text {
  width: 200px;
  margin-right: 20px;
}
.header__list-img {
  width: 31%;
  height: 100px;
  background: #c4c4c4;
}

.header-enter {
  opacity: 0;
}

.header-enter-active {
  transition: opacity 500ms;
  animation: header-in 600ms ease-in forwards;
}

.header-leave-active {
  transition: opacity 500ms;
  animation: header-out 0.4s ease-in forwards;
  opacity: 0;
}

@media (max-width: 360px) {
  .header__list-item {
    flex-direction: column;
  }

  .header__list-item .header__list-img {
    order: 0;
    margin: 0;
    margin-bottom: 10px;
  }
  .header__list-item .header__list-text {
    order: 1;
    margin: 0;
  }
  .header__list-item:nth-child(even) .header__list-text {
    margin: 0;
  }
}

@keyframes header-in {
  from {
    transform: scale3d(-20px);
  }
  to {
    transform: scale3d(0px);
  }
}

@keyframes header-out {
  from {
    transform: scale3d(0px);
  }
  to {
    transform: scale3d(-20px);
  }
}
</style>