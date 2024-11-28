<template>
  <section class="comparison">
    <div class="slider-container">
    <label for="user-slider">Número de Usuarios: {{ numUsers }}</label>
        <input
        type="range"
        id="user-slider"
        :min="minUsers"
        :max="maxUsers"
        :step="1"
        v-model="numUsers"
        @change="onSliderChange"
        class="styled-slider"
        />
    </div>
    <div class="pricing">
      <div class="pricing-plan">
        <h2>Ketza Enterprise</h2>
        <p class="price">${{ ketzaPrice.toLocaleString() }} USD</p>
        <p>Aprox. Costo Anual</p>
      </div>
      <div class="pricing-plan">
        <h2>ChatGPT, Gemini o Claude</h2>
        <p class="price">${{ officialPrice.toLocaleString() }} USD</p>
        <p>Aprox. Costo Anual</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Comparison',
  data() {
    return {
      numUsers: 10,
      minUsers: 10,
      maxUsers: 300,
    };
  },
  computed: {
    ketzaPrice() {
      return this.numUsers * 120;
    },
    officialPrice() {
      return this.numUsers * 360;
    },
  },
  methods: {
    onSliderChange() {
      this.numUsers = this.getClosestStop(this.numUsers);
    },
    getClosestStop(value) {
      return this.userStops.reduce((prev, curr) =>
        Math.abs(curr - value) < Math.abs(prev - value) ? curr : prev
      );
    },
  },
};
</script>

<style scoped>
.comparison {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem 1rem;
}

.pricing {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
}

.pricing-plan {
  background: #D4D4D4;
  padding: 1.5rem;
  border: 2px solid #253743;
  width: 60vh;
  border-radius: 10px;
  text-align: center;
  min-width: 250px;
}

.pricing-plan h2 {
  margin-bottom: 1rem;
}

.pricing-plan .price {
  font-size: 2rem;
  font-weight: bold;
  color: #253743;
  margin-bottom: 0.5rem;
}

.slider-container {
  width: 100%;
  max-width: 500px;
  text-align: center;
  margin-bottom: 1.5em;
}

.slider-container label {
  display: block;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
}

input[type="range"].styled-slider {
  -webkit-appearance: none; /* Remove default styling */
  width: 100%; /* Adjust slider width as needed */
  height: .4em; /* Height of the slider track */
  background: #a3a3a3; /* Color of the track */
  border-radius: 5px; /* Rounded corners of the track */
  outline: none; /* Remove outline on focus */
}

input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none; /* Remove default styling for the thumb */
  appearance: none; /* Remove default styling for the thumb in modern browsers */
  width: 15px; /* Set the width of the thumb */
  height: 15px; /* Set the height of the thumb */
  background: #253743; /* Color of the thumb */
  border-radius: 50%; /* Make the thumb circular */
  cursor: pointer; /* Pointer cursor on hover */
}

input[type="range"]::-moz-range-thumb {
  width: 15px; /* Set the width of the thumb for Firefox */
  height: 15px; /* Set the height of the thumb for Firefox */
  background: #253743; /* Color of the thumb for Firefox */
  border-radius: 50%; /* Make the thumb circular for Firefox */
  cursor: pointer; /* Pointer cursor on hover for Firefox */
}


#user-slider {
  width: 100%;
}

.user-count {
  margin-top: 0.5rem;
  font-size: 1.25rem;
  font-weight: bold;
}

/* Responsive */
@media (max-width: 768px) {
  .pricing {
    flex-direction: column;
    align-items: center;
  }

  .pricing-plan {
  width: auto;
 }

  .pricing-plan {
    margin-bottom: 1rem;
  }
}
</style>