<template>
  <div class="v-main-wrapper">
    <v-menu-left/>
    <v-inventory/>
  </div>
  <footer class="footer">ever since the 1500s, when an unknown printer took a galley of type and scrambled</footer>
</template>

<script>
import vMenuLeft from './v-menu-left.vue'
import vInventory from './v-inventory.vue'
export default {
  name: 'vMainWrapper',
  components: {
    vMenuLeft,
    vInventory
  },
  props: {
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.v-main-wrapper{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 90%;
  margin: 20px auto;
  gap: 20px;
}
footer{
  border: 1px solid #4D4D4D;
    border-radius: 20px;
    background: #292929;
  height: 72px;
  width: 90%;
  margin: 20px auto;
  display: flex;
  align-items: center;
  justify-content: center;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
