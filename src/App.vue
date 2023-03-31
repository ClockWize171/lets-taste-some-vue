<template>
  <title>Counter App</title>
  <main>
    <section>
      <h4>Let's count something.</h4>
      <h5>Skip: {{ currentSkip }}</h5>
      <div class="counter">
        <button class="btn" @click="setSkip(1)">
          1
        </button>
        <button class="btn" @click="setSkip(10)">
          10
        </button>
        <button class="btn" @click="setSkip(20)">
          20
        </button>
      </div>
      <div class="counter">
        <button class="btn btn1" @click="decreaseCount()">
          -
        </button>
        <h1>{{ count }}</h1>
        <button class="btn btn1" @click="increaseCount()">
          +
        </button>
      </div>
      <button class="btn reset" @click="reset()">Reset to (0)</button>
    </section>
  </main>
</template>

<script setup>

import { ref } from 'vue';

const count = ref(0);
const currentSkip = ref(1)

function increaseCount() {
  count.value = count.value + currentSkip.value;
}
function decreaseCount() {
  count.value = count.value - currentSkip.value;
}

function setSkip(value) {
  currentSkip.value = value
}

function reset() {
  count.value = 0
}

</script>

<style scoped>
main {
  display: flex;
  background-color: rgb(187, 222, 253);
  min-width: 100vw;
  min-height: 100vh;
  justify-content: center;
  align-items: center;
  text-align: center;
}

section {
  display: flex;
  flex-direction: column;
}

.counter {
  align-items: center;
  justify-content: space-between;
  display: flex;
  flex: 1;
}

.btn {
  position: relative;
  display: block;
  color: rgb(0, 74, 233);
  font-size: 20px;
  font-family: 'Anonymous Pro';
  text-decoration: none;
  margin: 10px 20px;
  border: 1px solid rgb(45, 139, 233);
  padding: 10px 30px;
  overflow: hidden;
}

.btn1 {
  color: aliceblue !important;
  border: 0 !important;
  background-color: rgb(15, 72, 130);
}

.reset{
  color: aliceblue !important;
  border: 0 !important;
  background-color: rgb(241, 109, 124);
}

</style>