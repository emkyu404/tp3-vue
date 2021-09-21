<template>
    <button :style="style" @mouseover="mouseOver()" @mouseleave="mouseOver()" :disabled="this.disabled">
        <slot></slot>
    </button>
</template>

<script>
    const colorPalette = {
        primary: { bg: '#42b983', hoverBg: '#4cce93', focusBorder: '#47d696' },
        warn: { bg: '#ff5722', hoverBg: '#ff7043', focusBorder: '#ff8a65' },
        danger: { bg: '#e53935', hoverBg: '#ef5350', focusBorder: '#e57373' },
        disabled : {bg : '#D9F1E6'}
    }
    export default {
        name: 'BaseButton',
        components: {

        },
        data: function(){
            return{
                hovering: false
            }
        },
        props:{
            color : String,
            disabled : Boolean
        },
        computed: {
            style(){
                if(this.disabled === true){
                    return 'background-color : ' + colorPalette.disabled.bg
                }
                
                if(this.hovering === false){
                    if(this.color === "warning"){
                        return 'background-color : ' + colorPalette.warn.bg + '; border-color : ' + colorPalette.warn.focusBorder
                    }else if(this.color === "danger"){
                        return 'background-color : ' + colorPalette.danger.bg + '; border-color : ' + colorPalette.danger.focusBorder
                    }
                    else{
                        return 'background-color : ' + colorPalette.primary.bg + '; border-color : ' + colorPalette.primary.focusBorder
                    }
                }else{
                    if(this.color === "warning"){
                        return 'background-color : ' + colorPalette.warn.hoverBg + '; border-color : ' + colorPalette.warn.focusBorder
                    }else if(this.color === "danger"){
                        return 'background-color : ' + colorPalette.danger.hoverBg  + '; border-color : ' + colorPalette.danger.focusBorder
                    }
                    else{
                        return 'background-color : ' + colorPalette.primary.hoverBg + '; border-color : ' + colorPalette.primary.focusBorder
                    }
                }
            }
        },
        methods: {
            mouseOver(){
                this.hovering = !this.hovering
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