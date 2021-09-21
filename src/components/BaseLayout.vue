<template>
    <base-header />
    <slot></slot>
    <base-footer />
</template>

<script>

    import BaseHeader from './BaseHeader.vue'
    import BaseFooter from './BaseFooter.vue'

    export default {
        name: 'BaseLayout',
        components: {
            BaseHeader,
            BaseFooter
        }
    }
</script>

<style>
#footer {
  padding : 20px;
  background-color: #2c3e50;
  bottom : 0;
  position : fixed;
  width : 100%;
}
</style>