<template>
<div class="text-container">
  <div class="blog">
    <router-view />
    <router-link to="/" tag="a" class="back">&laquo; Back</router-link>
  </div>
</div>
</template>
<style lang="scss" scoped>

.text-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  border: 2px solid #fff;
  border-radius: 10px;
  background-color: rgba(0, 0, 0, 0);
}

.blog {


  .back {
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    margin-top: 0.25rem;
    text-decoration: none;
    padding: 10px 15px;
    border: 1px solid currentColor;
    border-radius: .5rem;
    display: inline-block;
    transition: all .3s ease;
    &:hover {
      background-color: transparent;
      color: #BF616A;
    }
  }
  ::v-deep {
    h1 {
      font-size: 3rem;
      margin-bottom: .2rem;
      color: #fff;
    }
    h4 {
      margin-bottom: 3rem;
      color: #fff;
    }
    pre {
      overflow-x: auto;
      background-color: rgba(0, 0, 0, 0.5);
      color: white;
      border-radius: .3rem;
      padding: 1rem;
    }
    img {
      max-width: 100%;
    }
  }
}
</style>

