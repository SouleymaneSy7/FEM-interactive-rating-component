<template>
  <!-- Thank you state start -->

  <section class="success-container" v-if="ratingSuccess">
    <div class="success__img">
      <img
        src="./assets/illustration-thank-you.svg"
        alt="SVG Thank you Illustration"
      />
    </div>

    <div class="selected__text">
      <p class="rating__paragraph">
        You selected
        {{ selectedNumber }}
        out of 5
      </p>
    </div>

    <h2 class="rating__title">Thank you!</h2>

    <p class="rating__paragraph">
      We appreciate you taking the time to give a rating. If you ever need more
      support, don’t hesitate to get in touch!
    </p>
  </section>

  <!-- Thank you state end -->

  <!-- Rating state start -->

  <main class="rating-container" v-else>
    <div class="rating__img">
      <img src="./assets/icon-star.svg" alt="Star Icon" />
    </div>

    <h1 class="rating__title">How did we do?</h1>

    <p class="rating__paragraph">
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </p>

    <ul class="rating__number">
      <li>
        <button
          type="button"
          class="rating__number--btn"
          @click="selectNumber(1)"
        >
          1
        </button>
      </li>

      <li>
        <button
          type="button"
          class="rating__number--btn"
          @click="selectNumber(2)"
        >
          2
        </button>
      </li>

      <li>
        <button
          type="button"
          class="rating__number--btn"
          @click="selectNumber(3)"
        >
          3
        </button>
      </li>

      <li>
        <button
          type="button"
          class="rating__number--btn"
          @click="selectNumber(4)"
        >
          4
        </button>
      </li>

      <li>
        <button
          type="button"
          class="rating__number--btn"
          @click="selectNumber(5)"
        >
          5
        </button>
      </li>
    </ul>

    <button class="rating--btn" type="button" @click="ratingSubmit">
      Submit
    </button>
  </main>

  <!-- Rating state end -->

  <footer class="attribution">
    <p>
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >
    </p>

    <p>
      Coded <span>&hearts;</span> by
      <a href="https://github.com/SouleymaneSy7" target="_blank"
        >Souleymane Sy</a
      >
    </p>
  </footer>
</template>

<script setup>
// Imports
import { ref } from "vue";

// Variables
const selectedNumber = ref(null);
const ratingSuccess = ref(false);

// Functions
const selectNumber = (number) => {
  selectedNumber.value = number;
};

const ratingSubmit = () => {
  if (selectedNumber.value === null) {
    ratingSuccess.value = false;
  } else {
    ratingSuccess.value = true;
  }
};
</script>
