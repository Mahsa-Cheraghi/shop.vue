<template>
   
        <div class="roww" v-for="(order, index) in orders" :key="index">
            <img  class="img" :src=order.src />
            <div class="p">{{ order.title }}</div>
            <div>{{ order.price }}</div>
            <div>
                <span >
                   Quantity({{order.Quantity}})
                  <button @click="order.Quantity--" class="min">- </button>
                
                 <button @click="order.Quantity++" class="plass">+ </button>
                  
                </span>
                <button class="remove" @click="del(index)" data-id="index">Remove</button>
            
        </div>
</div>
</template>
<script>
export default {
    props: { orders: Array },
 
    methods: {
      
        del(id) {
     
      {
        this.orders.splice(id, 1);
      }

    }
    },
    // methods: {
    // del(id) {
    //   console.log(id);
      
    //     this.todos.splice(id, 1);
    //   }

    // }
  }


</script>
<style scoped>
.roww {
    width: 1000px;
    border: 1px solid #444;
    display: flex;
    justify-content: space-around;
    place-items: center;
    margin: 10px;
}

.remove {
    background-color: red;
    border: none;
    padding: 8px;
    margin: 8px;
    border-radius: 4px;
}

.plass,
.min {
    background-color: rgb(38, 161, 199);
    padding:8px 8px;
    margin:2px 2px;
    border: none;
}
.img{
    width: 120px;
}
</style>