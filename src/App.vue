<script lang="ts" setup></script>

<template>
  <router-view />
</template>

<style lang="scss">
#app {
  padding: 32px;
}

#nav {
  padding: 30px 0;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
