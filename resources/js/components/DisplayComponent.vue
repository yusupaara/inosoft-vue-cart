<template>
    <div class="container">
        <product-com :listdata="list" @emit-add="addCart"/>
    </div>
</template>
<script>
import ProductComponent from './ProductComponent.vue'
export default{
  components: { ProductComponent },
    data:function(){
        return{
            list: [
                {
                    name:"Indomie Goreng Rendang",
                    desc:"Masakan instan terenak di dunia",
                    stock:10,
                    price:3900,
                },
                {
                    name:"Mie Gelas Rendang",
                    desc:"Mie instan khusus anak kosan",
                    stock:5,
                    price:1500,
                },
                {
                    name:"Bakmi Mewah",
                    desc:"Kalau anak kosan jangan macam2 deh",
                    stock:80,
                    price:10000,
                },
            ],input: "",
        }
    },
    methods:{
        addCart(datalist){
            let newList = {
                title : datalist,
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