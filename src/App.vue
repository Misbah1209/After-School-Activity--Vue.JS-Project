<template>
  <div>

    <head>
      <link rel="shortcut icon" type="image/x-icon" href="#">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css">
      <link rel="stylesheet" href="style.css">
    </head>

    <div id="app">
      <header class="nav-section"   >
        <img src=logo.png alt="logo" class="logo">
        <div class="cart">  
          <button @click="showCheckout" class="cartbtn">
              <span class="fas fa-shopping-cart"></span> Checkout
              <span class="badge">{{this.cart.length }}</span>
          </button>
        </div>
      </header>

      <main>
        <div v-if="showLesson">
        <lesson-list @addlessons="addToCart"></lesson-list>
        </div>
        <div v-else>
        <checkout :cart="cart"></checkout>
        </div>
      </main>

    </div>
  </div>
</template>

<script>
import lessonList from "./components/LessonList.vue";
import checkout from "./components/Form.vue";

export default {

  name: "App",

  components: {
    lessonList,
    checkout,
  },
  data() {
    return {
      sitename: "After School Activities",
      cart: [],
      showLesson: true,
    };
  },

  methods: {
    showCheckout() {
      this.showLesson = this.showLesson ? false : true;
    },
    addToCart(lessons) {
      this.cart.push(lessons);
    },
  },
};
</script>