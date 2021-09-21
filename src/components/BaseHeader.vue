<template>
    <div id="menu">
        <p style="color : white;"><a href=""> Homepage </a></p>
        <p style="color : white;"> Username </p>
    </div>
</template>

<script>
    export default {
        name: 'BaseHeader',
        components: {

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