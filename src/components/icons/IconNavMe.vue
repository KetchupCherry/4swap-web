<template>
  <svg
    class="icon"
    width="24"
    height="24"
    viewBox="0 0 24 24"
    xmlns="http://www.w3.org/2000/svg"
  >
    <circle
      cx="12"
      cy="6.5"
      r="5"
      :stroke="colors[0]"
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
    <path
      fill-rule="evenodd"
      clip-rule="evenodd"
      d="M3.00002 18.9969C2.99849 18.6075 3.08775 18.2228 3.26104 17.8719C3.80484 16.8107 5.33834 16.2482 6.61082 15.9935C7.52853 15.8024 8.45892 15.6747 9.39506 15.6114C11.1282 15.4629 12.8714 15.4629 14.6046 15.6114C15.5407 15.6754 16.471 15.8031 17.3889 15.9935C18.6613 16.2482 20.1948 16.7576 20.7386 17.8719C21.0871 18.5871 21.0871 19.4173 20.7386 20.1325C20.1948 21.2468 18.6613 21.7562 17.3889 22.0003C16.4722 22.1993 15.5415 22.3306 14.6046 22.393C13.1939 22.5097 11.7767 22.531 10.363 22.4567C10.0367 22.4567 9.72133 22.4567 9.39506 22.393C8.46169 22.3314 7.53452 22.2001 6.6217 22.0003C5.33834 21.7562 3.81571 21.2468 3.26104 20.1325C3.08864 19.7776 2.99947 19.3897 3.00002 18.9969Z"
      :stroke="colors[0]"
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
  </svg>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
class IconNavMe extends Vue {
  isDark = this.$vuetify.theme.dark;

  get active() {
    return this.$parent.$attrs.active ?? false;
  }

  get colors() {
    const activeColor = this.$vuetify.theme.currentTheme.primary;
    const inactiveColor = this.$vuetify.theme.currentTheme.greyscale_4;

    return this.active ? [activeColor] : [inactiveColor];
  }
}
export default IconNavMe;
</script>

<style lang="scss" scoped>
.icon {
  fill: none;
}
</style>
