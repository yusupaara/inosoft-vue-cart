<template>
    <button type="button" @click="functionClick" :class="color">{{ text }}</button>
</template>

<script>
export default {
    emits:["emit-click"],
    props:{
        text:{
            type:String,
            default:""
        },
        color:{
            type:String,
            default:""
        },
    },
    methods:{
        functionClick(){
            this.$emit("emit-click")
        }
    }
}
</script>

<style scoped>
.blue{
    background:lightskyblue;
    border: 1px solid;
}
.red{
    background:lightcoral;
    border: 1px solid;
}
.green{
    background:lightseagreen;
    border: 1px solid;
}
</style>