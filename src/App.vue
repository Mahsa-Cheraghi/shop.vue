<template>
  <div class="row">
    <itemshop :myObject="this.myObject" />
  </div>
 
</template>
<script>
import itemshop from "./components/itemshop.vue";

export default {
  components: { itemshop },
  data() {
    return {
      myObject: [
        {
          title: "Pomegranate",
          src: "../1-strawberry-png-images-thumb.png",
          price: '54$',
          likesCount:3,
          likeflage:true,
          Quantity:0

        },
        {
          title: "Orange",
          src: "../5-2-fruit-free-png-image-thumb.png",
          price: '50$',
          likesCount:2,
          likeflage:false,
          Quantity:0

        },
        {
          title: "Strawberry",
          src: "../5-pomegranate-png-image-thumb.png",
          price: '45$',
          likesCount:1,
          likeflage:false,
          Quantity:0
        },
      ],
    };
  },

};
</script>
<style>
.row {

  margin: 0px auto;
  display: flex;
  flex-wrap: wrap;

}
</style>
