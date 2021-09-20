<template>
  <div id="nav">
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About</router-link></li>
    </ul>
  </div>
  <router-view />
</template>

<script>
export default {};
</script>

<style lang="scss">
/** NAVIGATION BAR */
#nav {
  overflow: hidden;
  background-color: #333;
  position: fixed;
  top: 0;
  width: 100%;
  ul {
    text-align: center;
    list-style-type: none;
    list-style-type: none;
    margin: 0;
    padding: 15px;
  }

  li {
    display: inline;
    font-family: 'Lato';
    font-size: 17px;
  }
  a {
    /*router-link*/
    color: #f2f2f2;
    text-decoration: none;
    padding: 14px;
    &:hover {
      background-color: #111;
    }
  }
}
</style>
