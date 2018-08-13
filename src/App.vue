<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css");

  body,
  html {
    padding: 0 10px;
    margin: 0;
    background: #0e0f11;
    color: #ecf0f1;
    font-family: 'Open Sans', sans-serif;
    min-height: 100vh;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
        -ms-flex-direction: row;
            flex-direction: row;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    width: 100%;
  }
  * {
    box-sizing: border-box;
  }

  h1,
  p {
    text-align: center;
  }
  p {
    width: 100%;
    max-width: 500px;
    margin: auto;
  }
  a:link,
  a:hover,
  a:active,
  a:visited {
    -webkit-transition: color 150ms;
    transition: color 150ms;
    color: #95a5a6;
    text-decoration: none;
  }
  a:hover {
    color: #7f8c8d;
    text-decoration: underline;
  }
  .contain {
    width: 100%;
  }
#app {
  width: 100%;
}
</style>
