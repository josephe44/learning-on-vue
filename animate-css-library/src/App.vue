<template>
  <!-- List animation and transition -->
  <button @click="addItem">Add</button>

  <ul>
    <transition-group
      name="fade"
      enter-active-class="animate__animated animate__flipInX"
      leave-active-class="animate__animated animate__flipOutX"
    >
      <li v-for="(num, index) in numbers" :key="num" @click="deleteItem(index)">
        {{ num }}
      </li>
    </transition-group>
  </ul>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      flag: true,
      numbers: [1, 2, 3, 4, 5],
    };
  },
  methods: {
    addItem() {
      // random number between 1 and 100
      const num = Math.floor(Math.random() * 100 + 1);

      // random select an index inside the array
      const index = Math.floor(Math.random() * this.numbers.length);

      // insert the number at the random index
      this.numbers.splice(index, 0, num);
    },

    // delete item
    deleteItem(index) {
      this.numbers.splice(index, 1);
    },
  },
};
</script>

<style>
body {
  display: flex;
  justify-content: center;
  align-items: center;
}

.animate__flipOutX {
  position: absolute;
}

.animate__animated {
  animation-duration: 1.5s;
}

ul {
  list-style: none;
  padding: 0;
}

li,
button {
  font-size: 22px;
  margin: 10px;
  padding: 10px;
  background-color: #ccc;
  border-radius: 5px;
  cursor: pointer;
}

h2 {
  width: 400px;
  padding: 20px;
  margin: 20px;
}

.fade-enter-from {
  opacity: 0;
}

.fade-enter-active {
  transition: all 0.5s linear;
}

.fade-leave-to {
  transition: all 0.5s linear;
  opacity: 0;
}

.fade-move {
  transition: all 0.7s linear;
}

.fade-leave-active {
  position: absolute;
}
</style>
