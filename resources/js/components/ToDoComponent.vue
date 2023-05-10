<template>
    <div>
        <h1>To-Do</h1>
        <form>
            <input type="text" v-model="input">
            <button type="button" @click="addList">Submit</button>
        </form>
        <ul>
            <li v-for="(item, index) in list" :key="index">
                {{ item.title }} <span class="delete" @click="deleteList(index)">Hapus</span>
            </li>
        </ul>
    </div>
</template>
<script>
export default{
    data:function(){
        return{
            list: [
                {
                    title:"menyapu"
                },
                {
                    title:"cuci piring"
                },
                {
                    title:"pel"
                },
            ],input: "",
        }
    },
    methods:{
        addList(){
            let newList = {
                title : this.input
            }
            this.list.push(newList)
            this.input =""
        },
        deleteList(index){
            this.list.splice(index,1)
        }
    },
    mounted() {
        console.log('Component mounted.')
    }
}
</script>