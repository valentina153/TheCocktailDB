<template>
  <div id="app">
    <Navbar />
    <Naslovnica/>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Naslovnica from "./components/Naslovnica";
export default {
  name: "index",
  components: {
    Navbar,
    Naslovnica
  }
};
</script>

<style>
body {
  background-image: url("https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia.timeout.com%2Fimages%2F103708095%2Fimage.jpg&f=1&nofb=1");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
