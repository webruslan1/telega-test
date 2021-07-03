<template name="component-name">
  <section>
    <h2 class="mb-15 tac">{{ this.title }}</h2>
    <div class="sorting__input">
      <input
        v-model="input"
        @input="sortItems"
        placeholder="Enter title name"
        type="text"
      />
      <div class="clear" @click="clearInput">X</div>
    </div>
    <transition-group
      name="mix"
      mode="out-in"
      v-if="sortingItems.length == 0 ? false : true"
      class="sorting__list"
    >
      <div
        v-for="(item, key) in sortingItems"
        :key="key"
        class="sorting__list-item"
      >
        <span>{{ item }}</span>
      </div>
    </transition-group>
    <p class="not-found tac" v-else>This number was not found.</p>
  </section>
</template>


<script>
export default {
  name: "Sorting",
  data() {
    return {
      Items: [1, 2, 3, 1, 2, 3, 7, 4, 6],
      sortingItems: null,
      input: null,
    };
  },
  props: {
    title: String,
  },
  mounted() {
    this.sortingItems = this.Items;
  },
  methods: {
    sortItems() {
      if (this.input) {
        var newArr = this.Items.filter((item) => this.input == item);
        this.sortingItems = newArr;
      } else {
        this.sortingItems = this.Items;
      }
    },
    clearInput() {
      this.input = "";
      this.sortingItems = this.Items;
    },
  },
};
</script>

<style>
input {
  width: 88%;
  height: 30px;
  border: 2px solid #f4f4f4;
  box-sizing: border-box;
  border-radius: 5px;
  padding: 9px;
  margin-right: 10px;
}

input:focus {
  outline: none;
}

.sorting__input {
  display: flex;
  margin-bottom: 5px;
}
.clear {
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 30px;
  height: 30px;
  font-family: Roboto;
  font-weight: bold;
  font-size: 14px;
  line-height: 16px;
  color: #000000;
  border: 2px solid #f4f4f4;
  box-sizing: border-box;
  border-radius: 5px;
}

.sorting__list {
  display: flex;
  flex-wrap: wrap;
}

.sorting__list-item {
  background: #c4c4c4;
  width: 31%;
  height: 125px;
  margin-top: 10px;
  position: relative;
}

.sorting__list-item span {
  position: absolute;
  left: 15px;
  bottom: 15px;
  font-weight: bold;
  font-size: 14px;
  line-height: 16px;

  color: #000000;
}

.sorting__list-item:not(:nth-child(3n)) {
  margin-right: 10px;
}
.not-found {
  font-size: 15px;
}
.mix-enter {
  opacity: 0;
}

.mix-enter-active {
  transition: opacity 500ms;
  animation: mixing-in 600ms ease-in forwards;
}

.mix-leave-active {
  transition: opacity 1000ms;
  animation: mixing-out 0.4s ease-in forwards;
  opacity: 0;
}

@media (max-width: 360px) {
  .sorting__list-item {
    width: 30%;
  }
}

@keyframes mixing-in {
  from {
    transform: scale3d(-20px);
  }
  to {
    transform: scale3d(0px);
  }
}

@keyframes mixing-out {
  from {
    transform: scale3d(0px);
  }
  to {
    transform: scale3d(-20px);
  }
}
</style>