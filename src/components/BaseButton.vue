<template>
    <button>
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'BaseButton',
        components: {

        },
        props:{

        }
    }
</script>

<style>
button{
    padding : 0px 20px 0px 20px;
    border-radius : 10px;
    color : white;
    background-color : #73D718;
    border : 5px solid #73D718;
    transition : 0.2s;
}

button:hover{
    background-color : #abe774;
    cursor : pointer;
}

button:focus{
    border : 6px solid #abe774;
}
</style>