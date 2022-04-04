<template>
<div>
 <div>
      <h1 style="text-align: center ;" >Lessons Catalogue</h1>
  </div>
  <br>
    <div class="cards"  v-for="lessons in lessons" :key="lessons.id">
      <h2 v-text="lessons.subject"></h2>
      <figure>
          <img class="lessonImg" v-bind:src="lessons.image">
      </figure>
      <p><b>Location: </b> {{lessons.location}}</p>
      <p><b>Price:</b>${{lessons.price}}.00</p>
      <p><b>Available spaces:</b> {{lessons.spaces}}</p>

      <button @click="add(lessons)">
              <i class="fas fa-cart-plus"></i>
              Add to cart
      </button>
      <span>Buy now!</span>
  </div>
</div>
</template>

<script>
export default {
  name: "lessonList",
  data() {
    return {
      lessons: [
        {
          id: 1001,
          subject: "Singing Lessons",
          price: 50.00,
          location: "California",
          image: "sing.jpg",
          spaces: 5,
        },
        {
          id: 1002,
          subject: "Art Lessons",
          price: 50.00,
          location: "Texas",
          image: "paint.jpg",
          spaces: 5,
        },
        {
          id: 1003,
          subject: "Dance Lessons",
          price: 75.00,
          location: "Florida",
          image: "dance.jpg",
          spaces: 5,
        },
        {
          id: 1004,
          subject: "Football Lessons",
          price: 40.00,
          location: "Michigan",
          image: "football.jpg",
          spaces: 5,
        },
        {
          id: 1005,
          subject: "Piano Lessons",
          price: 55.00,
          location: "Ohio",
          image: "piano.jpg",
          spaces: 5,
        },
        {
          id: 1006,
          subject: "Guitar Lessons",
          price: 65.00,
          location: "New York",
          image: "guitar.jpg",
          spaces: 5,
        },
        {
          id: 1007,
          subject: "Cooking Lessons",
          price: 50.00,
          location: "Alabama",
          image: "cook.jpg",
          spaces: 5,
        },
        {
          id: 1008,
          subject: "Basketball Lessons",
          price: 40.00,
          location: "Atlanta",
          image: "basketball.jpg",
          spaces: 5,
        },
        {
          id: 1009,
          subject: "Swimming Lessons",
          price: 60.00,
          location: "Chicago",
          image: "swim.jpg",
          spaces: 5,
        },
        {
          id: 1010,
          subject: "Yoga Lessons",
          price: 45.00,
          location: "Georgia",
          image: "yoga.jpg",
          spaces: 5,
        },
      ],
    };
  },
  methods: {
    add(lessons) {
      this.$emit('addlessons',lessons);
      console.log(lessons.spaces--);
    }
  },
};
</script>