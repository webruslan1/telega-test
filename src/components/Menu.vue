<template name="component-name">
  <header class="menu">
    <div class="menu-logo">
      <div class="menu-logo__img"></div>
      <div class="menu-logo__title">Logo</div>
    </div>
    <div
      class="menu-burger"
      @click="isOpen = isOpen ? false : true"
      :class="{ open: isOpen }"
    >
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div :class="{ 'vsb-h': isOpen }" class="menu__list">
      <ul>
        <li class="menu__list-item">Link 1</li>
        <li class="menu__list-item">Link 1</li>
        <li class="menu__list-item">Link 1</li>
        <li class="menu__list-item">Link 1</li>
        <li class="menu__list-item">Link 1</li>
        <li class="menu__list-item">Link 1</li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>

<style>
.menu__list {
  position: absolute;
  border-top: 1px solid #c4c4c4;
  border-bottom: 1px solid #c4c4c4;
  top: 45px;
  width: 100%;
  right: 0;
  background: #fff;
  padding: 15px 0;
  transform: translateX(100%);
  opacity: 0;
  transition: 1s;
}
.vsb-h {
  transform: translateX(0);
  opacity: 1;
  transition: 1s;
}
.menu__list ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  padding-right: 20px;
  text-align: right;
}

.menu__list-item {
  font-family: Roboto;
  font-size: 25px;
  line-height: 29px;
  color: #000000;
}
.menu__list-item:not(:last-child) {
  margin-bottom: 25px;
}
.menu {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 45px;
  width: 100%;
  margin: 0 auto;
  background: #fff;
  padding: 0 20px;
  box-sizing: border-box;
}
.menu-logo {
  display: flex;
  align-items: center;
}
.menu-logo__img {
  width: 25px;
  height: 25px;
  background: #c4c4c4;
  margin-right: 10px;
}
.menu-logo__title {
  font-weight: bold;
  font-size: 11px;
  line-height: 13px;
  color: #000000;
}

.menu-burger {
  cursor: pointer;
}

.menu-burger span {
  display: block;
  width: 25px;
  height: 3px;
  transition: 800ms;

  background: #c4c4c4;
}
.menu-burger span:not(:last-child) {
  margin-bottom: 3px;
}

.menu-burger.open {
  position: relative;
  width: 30px;
}
.menu-burger.open span {
  width: 29px;
  transition: 800ms;
  margin-bottom: 0;
}
.menu-burger.open span:nth-child(1) {
  position: absolute;
  transform: rotate(405deg);
  top: 0;
  left: 0;
}
.menu-burger.open span:nth-child(2) {
  position: absolute;
  transform: rotate(-405deg);
  top: 0;
  left: 0;
}
.menu-burger.open span:nth-child(3) {
  display: none;
}
</style>