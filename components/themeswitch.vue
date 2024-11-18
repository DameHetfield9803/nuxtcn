<script>
import '../assets/css/tailwind.css'
export default {
  name: 'themeswitch',
  data: () => {
    return {
      isDarkTheme: localStorage.getItem('class') === 'dark'
    };
  },
  watch: {
    isDarkTheme: {
      handler(val) {
        const theme = val ? 'dark' : 'light';
        document.documentElement.setAttribute('class', theme);
        localStorage.setItem('class', theme);
      },
      immediate: true
    }
  },
  methods: {
    toggleTheme() {
      this.isDarkTheme = !this.isDarkTheme;
    }
  }
}
</script>

<template class="mx-auto">
  <label @click="toggleTheme">
    <svg v-if="!isDarkTheme" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="28" height="40" fill="orange"
      viewBox="0 0 32 32">
      <!-- Sun Icon -->
      <path
        d="M 15 3 L 15 8 L 17 8 L 17 3 Z M 7.5 6.09375 L 6.09375 7.5 L 9.625 11.0625 L 11.0625 9.625 Z M 24.5 6.09375 L 20.9375 9.625 L 22.375 11.0625 L 25.90625 7.5 Z M 16 9 C 12.144531 9 9 12.144531 9 16 C 9 19.855469 12.144531 23 16 23 C 19.855469 23 23 19.855469 23 16 C 23 12.144531 19.855469 9 16 9 Z M 16 11 C 18.773438 11 21 13.226563 21 16 C 21 18.773438 18.773438 21 16 21 C 13.226563 21 11 18.773438 11 16 C 11 13.226563 13.226563 11 16 11 Z M 3 15 L 3 17 L 8 17 L 8 15 Z M 24 15 L 24 17 L 29 17 L 29 15 Z M 9.625 20.9375 L 6.09375 24.5 L 7.5 25.90625 L 11.0625 22.375 Z M 22.375 20.9375 L 20.9375 22.375 L 24.5 25.90625 L 25.90625 24.5 Z M 15 24 L 15 29 L 17 29 L 17 24 Z">
      </path>
    </svg>

    <svg v-if="isDarkTheme" x="0" y="0" width="26" height="40" viewBox="0 0 24 24" fill="yellow"
      xmlns="http://www.w3.org/2000/svg">
      <!-- Moon Icon -->
      <path
        d="M22 15.8442C20.6866 16.4382 19.2286 16.7688 17.6935 16.7688C11.9153 16.7688 7.23116 12.0847 7.23116 6.30654C7.23116 4.77135 7.5618 3.3134 8.15577 2C4.52576 3.64163 2 7.2947 2 11.5377C2 17.3159 6.68414 22 12.4623 22C16.7053 22 20.3584 19.4742 22 15.8442Z"
        stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
    </svg>
  </label>
</template>
