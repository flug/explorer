<template>
  <div class="absolute pin px-4 md:px-8 hidden sm:flex bg-theme-nav-background xl:rounded-r-md">
    <button
      class="px-4 py-3 md:py-6 flex-none flex items-center border-b-2 margin-t-2 mr-3 border-transparent genki-border-blue text-theme-text-secondary"
      @click="closeMenu"
    >
      <!-- Inline this SVG so we can change color dynamically -->
      <svg
        class="flex-none fill-current"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        width="15px"
        height="13px"
      >
        <path
          fill-rule="evenodd"
          fill="currentColor"
          d="M13.499,3.000 L1.499,3.000 C0.671,3.000 -0.001,2.328 -0.001,1.500 C-0.001,0.671 0.671,-0.000 1.499,-0.000 L13.499,-0.000 C14.328,-0.000 14.999,0.671 14.999,1.500 C14.999,2.328 14.328,3.000 13.499,3.000 ZM1.499,5.000 L7.499,5.000 C8.328,5.000 9.000,5.671 9.000,6.500 C9.000,7.328 8.328,8.000 7.499,8.000 L1.499,8.000 C0.671,8.000 -0.001,7.328 -0.001,6.500 C-0.001,5.671 0.671,5.000 1.499,5.000 ZM1.499,10.000 L9.499,10.000 C10.328,10.000 11.000,10.671 11.000,11.500 C11.000,12.328 10.328,13.000 9.499,13.000 L1.499,13.000 C0.671,13.000 -0.001,12.328 -0.001,11.500 C-0.001,10.671 0.671,10.000 1.499,10.000 Z"
        />
      </svg>
    </button>

    <!-- HEAD
    <router-link @click.native="closeMenu" :to="{ name: 'home' }" tag="button" class="menu-button genki-menu-button genki-border-blue">
      <img src="@/assets/images/icons/web-page-home.svg" class="genki-menu-button-img"/>
      {{ $t("Home") }}
    </router-link>
    <router-link @click.native="closeMenu" :to="{ name: 'top-wallets', params: { page: 1 } }" tag="button" class="menu-button genki-menu-button genki-border-blue">
      <img src="@/assets/images/icons/starred-badge.svg" class="genki-menu-button-img"/>
      {{ $t("Top Wallets") }}
    </router-link>
    <router-link @click.native="closeMenu" :to="{ name: 'delegate-monitor' }" tag="button" class="menu-button genki-menu-button genki-border-blue">
      <img src="@/assets/images/icons/monitoring.svg" class="genki-menu-button-img"/>
      {{ $t("Delegate Monitor") }}
    </router-link>
    <a href="https://wallet.ki" class="menu-button genki-menu-button genki-border-blue" target="_blank">
      <img src="@/assets/images/icons/wallet.svg" class="genki-menu-button-img"/>
      <span class="mr-2">Wallet</span>
    </a> -->

    <div class="flex-auto" />

    <RouterLink
      :to="{ name: 'home' }"
      tag="button"
      class="menu-button genki-menu-button genki-border-blue"
      @click.native="closeMenu"
    >
      <img
        src="@/assets/images/icons/web-page-home.svg"
        class="genki-menu-button-img"
      >
      {{ $t("Home") }}
    </RouterLink>

    <RouterLink
      :to="{ name: 'top-wallets', params: { page: 1 } }"
      tag="button"
      class="menu-button genki-menu-button genki-border-blue"
      @click.native="closeMenu"
    >
      <img
        src="@/assets/images/icons/starred-badge.svg"
        class="genki-menu-button-img"
      >
      {{ $t("Top Wallets") }}
    </RouterLink>

    <RouterLink
      :to="{ name: 'delegate-monitor' }"
      tag="button"
      class="menu-button genki-menu-button genki-border-blue"
      @click.native="closeMenu"
    >
      <img
        src="@/assets/images/icons/monitoring.svg"
        class="genki-menu-button-img"
      >
      {{ $t("Delegate Monitor") }}
    </RouterLink>

    <a
      href="https://wallet.ki"
      class="menu-button genki-menu-button genki-border-blue"
      target="_blank"
    >
      <img
        src="@/assets/images/icons/wallet.svg"
        class="genki-menu-button-img"
      >
      <span class="mr-2">Wallet</span>
    </a>

    <!-- <RouterLink :to="{ name: 'statistics' }" tag="button" class="menu-button">Statistics</RouterLink> -->

    <div class="flex-auto" />

    <!-- <a href="#" class="menu-button">
      <span class="mr-2">Snapshots</span>
      <img src="@/assets/images/icons/download.svg" />
    </a> -->
  </div>
</template>

<script type="text/ecmascript-6">

export default {
  name: 'HeaderMenuDesktop',

  methods: {
    closeMenu () {
      this.$store.dispatch('ui/setMenuVisible', false)
    }
  }
}
</script>
