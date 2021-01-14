<template>
  <div id="app">
    <div class="container">
      <div class="center">
        <List />
      </div>
    </div>
  </div>
</template>

<script>
import List from "./components/List";
export default {
  name: "App",
  components: {
    List
  }
};
</script>

<style scope>
.container {
  width: 100%;
  max-width: 700px;
  margin: auto;
  align-items: center;
  height: 100vh;
  display: flex;
  justify-content: center;
}
</style>
