<template>
    <div class="one" v-for="(item, id) in myObject" :key="id">
        <img class="image" :src="item.src" />
        <p class="p">{{ item.title }}</p>
        <br />
        <div class="div">
            <div class="price">
                {{ item.price }}
<button class="hearts"   :class="{red:item.likeflage}" ref="myButton"
 @click="Like(item.likeflage,item.likesCount)"> &#9829;{{item.likesCount}} </button>
            </div>
            
            <button class="add" @click="add(item)">add</button>
            <div class="count">{{ item.count }} </div>
        </div>
<div class="Quantity">{{item.Quantity}}</div>
    </div>
    <div class="roww">
        <Cards :orders="this.orders" />
    </div>
    
</template>
<script>
import Cards from "./Cards.vue";
export default {
    components: { Cards },
    props: ['myObject'],
    data() {
        return {
         
            orders: [],
        };
    },


    methods: {
       
        add(item) {
            console.log(item)


            this.orders.push(item)
        },

      
       
  
    Like(id,count) {
        if (this.id) {
           this.id = false
            this.count =count--;
        }
        else {
           this.id = true;
            this.count++;

        }
        console.log(this.$refs.myButton.innerText)
        console.log(this.id)
        console.log(count)
    },
    
}}

    ;

</script>
<style>
.image {
    width: 150px;
}

.p {
    text-align: center;
}

.one {
    border: 1px solid #444;
    margin: 25px;
    padding: 50px;
    padding-top: 20px;
}

.price {
    float: right;
}

.hearts {
    position: relative;
    left: 5px;
    cursor: pointer;
    font-size: 1.3em;
    float: right;
}

.add {
    float: left;
    background-color: green;
    border: none;
    padding: 10px 30px;
    border-radius: 5px;
}

.roww {
    display: inline;

}



.count {
    opacity: 0;
}
.red{
   color: red;
}
.Quantity{
    display: none;
}
</style>
