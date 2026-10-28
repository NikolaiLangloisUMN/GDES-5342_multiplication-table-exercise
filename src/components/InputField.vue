<script setup>
const props = defineProps({
  labelText: {
    type: String,
    required: true,
  }
})
</script>

<template>
  <section class="input-field">
    <strong>{{ props.labelText }}</strong>
    <input type="text" />
  </section>
</template>

<style scoped>
section.input-field {
  display: flex;
  gap: 20px;
  justify-content: space-between;
  width: 100%;
  flex-direction: column;

  div {
    border: 1px solid black;
  }

  @media screen and (width > 600px) {
    flex-direction: row
  }
}
</style>