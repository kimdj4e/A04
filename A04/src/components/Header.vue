<template>
  <nav
    style="
      background: linear-gradient(
        90deg,
        rgba(131, 58, 180, 1) 0%,
        rgba(253, 29, 29, 1) 50%,
        rgba(252, 176, 69, 1) 100%
      );
    "
    class="navbar navbar-expand-md bg-dark navbar-dark mt-2"
  >
    <span class="navbar-brand dis">비전공 4조</span>
    <button class="navbar-toggler" type="button" @click="changeIsNavShow">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div :class="navClass">
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" :to="{ name: 'home' }"> 홈</router-link>
        </li>
        <!-- <li class="nav-item">
          <router-link class="nav-link" :to="{ name: 'about' }"
            >소개</router-link
          >
        </li>
        <li class="nav-item">
          <router-link class="nav-link" :to="{ name: 'members' }"
            >멤버</router-link
          >
        </li> -->
      </ul>
    </div>
  </nav>
</template>

<script>
import { reactive, computed } from 'vue';
export default {
  setup() {
    const state = reactive({ isNavShow: false });
    const navClass = computed(() =>
      state.isNavShow
        ? 'collapse navbar-collapse show'
        : 'collapse navbar-collapse'
    );
    const changeIsNavShow = () => {
      state.isNavShow = !state.isNavShow;
    };
    return { state, changeIsNavShow, navClass };
  },
};
</script>

<style lang="scss" scoped></style>
