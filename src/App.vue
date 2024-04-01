  <template>
  <header class="sticky top-0">
    <div class="wrapper flex justify-between bg-blue-950 p-8 text-white flex-wrap">
      <div class="nav-logo">
        <router-link to="/" class="text-2xl">
            2Sure
        </router-link>
      </div>
      <div class="nav-toggle md:hidden" @click="toggleNav">
        <svg class="w-6 h-6 cursor-pointer" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
        </svg>
      </div>
      <nav :class="{ 'hidden': !isNavOpen }" class="flex justify-center gap-5 flex-wrap md:flex" @click.away="!isNavOpen">
        <RouterLink to="/">Tips store</RouterLink>
        <RouterLink to="/about">Rollover</RouterLink>
        <RouterLink to="/about">50 Odds</RouterLink>
        <RouterLink to="/about">10 Odds</RouterLink>
        <RouterLink to="/about">5 Odds</RouterLink>
        <RouterLink to="/about">2 Odds</RouterLink>
      <div class="nav-button flex gap-5 pl-10">
        <router-link to="/login">Login</router-link>
        <router-link to="/register">Register</router-link>
      </div>
    </nav>
    </div>
  </header>
  <RouterView />

</template>

<script>
import { RouterLink, RouterView } from 'vue-router'
export default {

  data() {
    return {
      isNavOpen: false
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    }
  }
};
</script>

