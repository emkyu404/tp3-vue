<template>
    <div id="menu">
        <base-button> HomePage </base-button>
        <p style="color : white;"> Username </p>
    </div>
</template>

<script>
import BaseButton from './BaseButton.vue'
    export default {
        name: 'BaseHeader',
        components: {
            BaseButton
        }
    }
</script>

<style>
#menu {
  padding : 20px;
  background-color: #2c3e50;
  display : flex;
  flex-direction : row;
  justify-content : space-evenly;
  width : 100%;
}
</style>