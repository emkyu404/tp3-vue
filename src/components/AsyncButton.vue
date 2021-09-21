<template>
  <base-button
    :class="{pending : isPending}"
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

async function add1sec(){
    const result = await resolveAfter1Seconds()
    console.log(result) 
}

function resolveAfter2Seconds(){
    return new Promise(resolve => {
        setTimeout(() => {
            resolve('resolved')
        }, 2000)
    })
}

function resolveAfter1Seconds(){
    return new Promise(resolve => {
        setTimeout(() => {
            resolve('1 sec added')
        }, 1000)
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
      isPending: false,
      clickWhilePending : 0
    }
  },

  methods: {
    async handleClick () {
        /* Exercice 9 */
        if(!this.isPending){
            this.isPending = true;
            await asyncCall(this.isPending)
            while(this.clickWhilePending){
                await add1sec()
                this.clickWhilePending--
            }
             this.isPending = false;
        }  else{
            console.log("Clicked While pending")
            this.clickWhilePending++
        }
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

button.pending{
    background-color : #D9F1E6 !important;
    border-color : #D9F1E6 !important;
    cursor : not-allowed;
}
</style>