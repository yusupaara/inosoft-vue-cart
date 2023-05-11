<template>
    <div class="container">
        <product-com :listdata="list" @emit-add="addCart"/>
        <cart-com :cartdata="cart" @emit-del="delCart"/>
    </div>
</template>
<script>
export default{
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
            ],
            cart:[],
        }
    },
    methods:{
        addCart(index){
            this.cart.push(this.list[index]),
            console.log('Component added.')
        },
        delCart(index){
            this.list.splice(index,1)
        }
    },
    mounted() {
        console.log('Component mounted.')
    }
}
</script>