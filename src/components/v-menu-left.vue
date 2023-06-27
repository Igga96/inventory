<template>
    <div class="v-menu-left">
      <img class="v-menu-left__img" src="../assets/Img-blur.png" alt="#">
      <div class="v-menu-left__description">
        <h2 class="v-menu-left__description_title">Lorem Ipsum</h2>
        <p class="v-menu-left__description_text1">is simply dummy text</p>
        <p class="v-menu-left__description_text2">of the printing and</p>
        <p class="v-menu-left__description_text3">typesetting industry</p>
        <p class="v-menu-left__description_text4">has been the</p>
        <p class="v-menu-left__description_text5">industry's standard</p>
        <span class="v-menu-left__description_text6">dummy text</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'vMenuLeft',
    props: {
    }
  }
  </script>
  
  <style lang="scss">
.v-menu-left{
    border: 1px solid #4D4D4D;
    border-radius: 20px;
    background: #292929;
    padding: 20px;
}
p{margin-bottom: 10px;
}
  </style>