<template>
  <div class="vertical-center">
    <div class="container">
      <div id="notfound" class="text-center ">
        <h1>😮</h1>
        <h2>Oops! Page Not Be Found</h2>
        <p>Sorry but the page you are looking for does not exist.</p>
        <router-link to="/">Back to homepage</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NotFound',
};
</script>

<style>

.vertical-center {
  min-height: 100%;
  min-height: 100vh;
  color: rgba(150, 5, 5, 0.582);
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f1f1f1;
}
</style>