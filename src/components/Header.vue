<template>
  <!-- Header -->
  <div id="header-wrapper">
    <div class="container">
      <!-- Header -->
      <header id="header">
        <div class="inner">
          <!-- Logo -->
          <h1><router-link id="logo" :to="{ name: 'home' }">Magic</router-link></h1>

          <!-- Nav -->
          <nav id="nav">
            <ul>
              <li class="current_page_item"><router-link :to="{ name: 'home' }">Home</router-link></li>
              <li><router-link :to="{ name: 'Collection' }">Ma Collection</router-link></li>
            </ul>
          </nav>
        </div>
      </header>

      <!-- Banner -->
      <div id="banner">
        <h2><strong>Magic Card:</strong> Ma collection</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderComponent"


};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
