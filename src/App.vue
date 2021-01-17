<template>
  <div id="app">
    <Header></Header>
    <Body></Body>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header/Menu";
import Body from "./components/Body/Body";
import Footer from './components/Footer/Footer'
export default {
  name: "app",
  components: {
    Header: Header,
    Body: Body,
    Footer:Footer
  }
};
</script>

<style>

</style>
