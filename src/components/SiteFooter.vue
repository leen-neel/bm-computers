<template>
  <footer class="site-footer absolute-bottom q-pa-sm bg-primary text-center">
    <div :class="{ 'q-mb-sm': $q.screen.lt.md }">
      &copy; BM Computers all rights reserved | Created by
      <a target="_blank" href="https://and249.netlify.app/"
        >Anindo Neel Dutta</a
      >
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.site-footer {
  color: black;

  a {
    color: black;

    &:hover {
      text-decoration: none;
    }
  }
}
</style>
