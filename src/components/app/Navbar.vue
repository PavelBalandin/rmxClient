<template>
  <nav class="navbar">
    <div class="nav-wrapper">
      <div class="navbar-left">
        <a href="/">RMX</a>
      </div>
      <ul class="right hide-on-small-and-down">
        <li>
          <a class="dropdown-trigger white-text"
             href="#"
             data-target="dropdown"
             ref="dropdown">{{ username }}<i class="material-icons right">arrow_drop_down</i>
          </a>
          <ul id='dropdown' class='dropdown-content'>
            <li class="divider" tabindex="-1"></li>
            <li>
              <a href="#" class="black-text" @click.prevent="logout">
                <i class="material-icons">assignment_return</i>Exit
              </a>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      username: localStorage.getItem('username')
    }
  },
  methods: {
    logout() {
      localStorage.clear()
      this.$router.push('login?message=logout')
    }
  },
  mounted() {
    M.Dropdown.init(this.$refs.dropdown, {
      constraint: true
    })
  }
}
</script>

<style scoped>
.dropdown-content {
  top: 50px !important;
}
</style>