<template>
  <div>
    <compHeader/>
    <compMainPage/>
  </div>
</template>

<script>
import compHeader from "./components/Header/header";
import compMainPage from "./components/Main/mainPage";

export default {
  name: "app",
  components: {
    compHeader,
    compMainPage
  }
};
</script>

<style>
@import "./assets/mainStyle.css";
</style>
