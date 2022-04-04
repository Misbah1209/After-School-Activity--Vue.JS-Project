<template>
  <div>
    <div class="cards"> 
      <h2>Checkout</h2>
      <p>
          <strong> Name:</strong>
          <input class="field"  v-model="name"  />
      </p>
      <p>
          <strong>Address:</strong>
          <input class="field" v-model="address"/>
      </p>
      
      <button @click="submit()">Place Order</button>

    </div>
    <div style="float:right"><p style="font-size:400%"><b>Thank you for shopping:)</b></p></div>
    <h2>Lessons Added</h2>

    <div class="cards" v-for='(lessons,index) in cart' :key="index">
      <h2 v-text="lessons.subject"></h2>
      <figure>
          <img class="lessonImg" v-bind:src="lessons.image">
      </figure>
      <p><b>Location: </b> {{lessons.location}}</p>
      <p><b>Price:</b> ${{lessons.price}}.00 </p>

      <button style="margin-left:70%;" @click="cart.splice(index,1)">
          <i class="fas fa-times"></i>
          Remove
      </button>

    </div> 

  </div>
</template>

<script>
export default {
  name: "Form",
  props: ['cart'],
  data() {
    return {
      name: "",
      address: "",
    };
  },
  methods:{
    submit(){
      alert('Order submitted!')
    }
  }
};
</script>