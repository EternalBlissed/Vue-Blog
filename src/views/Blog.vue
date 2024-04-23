<template>
<div class="text-container">
  <div class="blog">
    <router-view />
    <router-link to="/" tag="a" class="back">&laquo; Back</router-link>
  </div>
</div>
</template>
<style scoped>

.blog {
  background-color: transparent;
}

.blog .back {
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  margin-top: 0.5rem;
  text-decoration: none;
  padding: 10px 15px;
  border: 1px solid currentColor;
  border-radius: 0.5rem;
  display: inline-block;
  transition: all 0.3s ease;
}

.text-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  border: 2px solid #fff;
  border-radius: 10px;
  background-color: rgba(0, 0, 0, 0);
}

.blog .back:hover {
  background-color: transparent;
  color: #ffaaff;
}

.blog h1 {
  font-size: 3rem;
  margin-bottom: 0.2rem;
  color: #fff;
}

.blog h4 {
  margin-bottom: 3rem;
  color: #fff;
}

.blog pre {
  overflow-x: auto;
  background-color: #fff;
  color: white;
  border-radius: 0.3rem;
  padding: 1rem;
}

.blog img {
  max-width: 100%;
}

</style>
