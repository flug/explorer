<template>
  <header
    v-click-outside="closeHeader"
    class="header min-h-50px md:min-h-80px z-50 max-w-2xl mx-auto flex bg-theme-nav-background shadow-theme xl:rounded-md mb-5 sm:mb-10"
  >
    <router-link
      :to="{ name: 'home' }"
      class="logo-container w-50px md:w-80px h-50px md:h-80px flex-none text-2xl xl:rounded-l-md flex justify-center items-center bg-blue"
      style="background: #ffffff;"
    >
      <img
        class="logo max-w-25px md:max-w-38px"
        src="@/assets/images/logo.png"
      >
    </router-link>
    <div class="w-full relative hidden xl:flex">
      <HeaderSearch v-if="headerType === 'search'" />

      <HeaderDesktopCurrencies v-else-if="headerType === 'currencies'" />

      <HeaderDesktopLanguages v-else-if="headerType === 'languages'" />

      <HeaderDefault v-else />

      <HeaderDesktopMenu v-if="menuVisible" />
    </div>
    <div class="w-full relative flex xl:hidden">
      <HeaderSearch v-if="headerType === 'search'" />

      <HeaderDefault v-else />
    </div>
    <HeaderMobileMenu v-if="menuVisible" />

    <HeaderMobileCurrencies v-else-if="headerType === 'currencies'" />

    <HeaderMobileLanguages v-else-if="headerType === 'languages'" />
  </header>
</template>

<script type="text/ecmascript-6">
import HeaderDefault from '@/components/header/Default'
import HeaderSearch from '@/components/header/Search'
import HeaderDesktopCurrencies from '@/components/header/currencies/Desktop'
import HeaderMobileCurrencies from '@/components/header/currencies/Mobile'
import HeaderDesktopLanguages from '@/components/header/languages/Desktop'
import HeaderMobileLanguages from '@/components/header/languages/Mobile'
import HeaderDesktopMenu from '@/components/header/menu/Desktop'
import HeaderMobileMenu from '@/components/header/menu/Mobile'
import { mapGetters } from 'vuex'

export default {
  components: {
    HeaderDefault,
    HeaderSearch,
    HeaderDesktopCurrencies,
    HeaderMobileCurrencies,
    HeaderDesktopLanguages,
    HeaderMobileLanguages,
    HeaderDesktopMenu,
    HeaderMobileMenu
  },

  computed: {
    ...mapGetters('ui', ['headerType', 'menuVisible'])
  },

  methods: {
    closeHeader () {
      this.$store.dispatch('ui/setHeaderType', null)
    }
  }
}
</script>

<style scoped>
.header {
  position: sticky;
  top: 0;
}
</style>
