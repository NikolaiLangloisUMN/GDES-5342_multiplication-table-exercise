<script setup>
/* All js lives here */

import {ref} from "vue";

const name = ref('Nikolai')
const numOfRows = ref(10)
const numOfCols = ref(10)
</script>


<template>
  <section class="container">

    <h1>My multiplication table playground</h1>

    <h2 v-if="name">Welcome {{ name }}!</h2>
    <h2 v-else>Please tell us your name</h2>

    <div class="inputs">
      <label>
        Name:
        <input type="text" v-model="name"/>
      </label>

      <label>
        How many rows do you want?
        <input type="number" v-model.number="numOfRows"/>
      </label>

      <label>
        How many columns do you want?
        <input type="number" v-model.number="numOfCols"/>
      </label>
    </div>


    <table>
      <tr v-for="row in numOfRows">
        <td v-for="col in numOfCols">
          {{ row * col }}
        </td>
      </tr>
    </table>

  </section>

</template>


<style scoped>
section.container {
  border: 10px solid black;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;

  h1, h2, h3, h4, h5, h6 {
    margin: 0;
  }

  div.inputs {
    border: 2px solid red;
    gap: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;

    label {
      display: flex;
      justify-content: space-between;
      border: 1px solid black;
      width: 100%;
    }
  }
}


table {
  border: 4px solid black;

  tr {
    td {
      border: 1px dotted red;
    }
  }
}
</style>