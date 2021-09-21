<template>
  <base-button
    :disabled="isPending"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <font-awesome-icon 
      v-if="isPending"
      :icon="['fas', 'circle-notch']"
      pulse
    />
    <p v-if="isPending">
        Bouton désactivé
    </p>
    <slot />
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue'

async function asyncCall(){
        console.log('called')
        const result = await resolveAfter2Seconds()
        console.log(result)  
 
}

function resolveAfter2Seconds(){
    return new Promise(resolve => {
        setTimeout(() => {
            resolve('resolved')
        }, 2000)
    })
}

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },

  data () {
    return {
      isPending: false
    }
  },

  methods: {
    async handleClick () {
        this.isPending = true;
        await asyncCall(this.isPending)
        this.isPending = false;
    }

    
  }
}
</script>

<style>
button{
    padding : 0px 20px 0px 20px;
    border-radius : 10px;
    color : white;
    transition : 0.2s;
    border:none;
}

button:hover{
    cursor : pointer;
}

button:focus{
    border : 5px solid;
}

button:disabled{
    cursor : not-allowed;
}
</style>