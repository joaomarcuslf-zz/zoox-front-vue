<template>
  <nav id="navbar" class="navbar is-fixed-top">
    <div class="container">
      <div class="navbar-brand">
        <a class="navbar-item has-dropdown is-hoverable">
          <h2 class="subtitle has-text-centered">
            {{ $t("message.hello") }} <a href="https://github.com/joaomarcuslf">@joaomarcuslf</a>
          </h2>
        </a>

        <div class="navbar-item">
          <LanguageChanger />
        </div>


        <span class="navbar-burger burger" data-target="navbarMenuHeroA" @click="showNav = !showNav" :class="{ 'is-active': showNav }">
          <span></span>
          <span></span>
          <span></span>
        </span>
      </div>

      <div id="navbarMenuHeroA" class="navbar-menu" :class="{ 'is-active': showNav }">
        <div class="navbar-end">
          <router-link class="navbar-item" to="/">{{ $t("message.states") }}</router-link>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import LanguageChanger from '@/components/LanguageChanger'

export default {
  name: 'Navbar',
  components: {
    LanguageChanger,
  },
  data() {
    return { showNav: false };
  },
};
</script>

<style scoped>
#navbar {
  background-color: #272727;
}
</style>
