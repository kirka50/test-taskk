<template>
  <MainPage/>
</template>

<script>

import MainPage from "@/components/MainPage";
export default {
  name: 'App',
  components: {
    MainPage
  }
}
</script>

<style>
#app {

}
@font-face {
  font-family: "SF UI Text";
  src: local("SF UI  Text"),
  url("./assets/sf-ui-text-regular.ttf");
}
@font-face {
  font-family: "SF UI Text light";
  src: local("SF UI  Text light"),
  url("./assets/sf-ui-text-light.ttf");
}
html, body {
  margin: 0;
}
</style>
