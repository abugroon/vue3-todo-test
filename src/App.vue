<template>
    <ul class="nav w-100 bg-dark justify-content-center">
      <li class="nav-item">
        <router-link active-class="active" class="nav-link" to="/"
          >Home</router-link
        >
      </li>
      <li class="nav-item">
        <router-link active-class="active" class="nav-link" to="/about"
          >About</router-link
        >
      </li>
    </ul>
  <div class="container mt-4">
    <div class="row">
      <router-view />
    </div>
  </div>
</template>
<style lang="scss">
</style>
