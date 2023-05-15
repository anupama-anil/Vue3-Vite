<template>
  <div>
    <h1>{{ msg }}</h1>

    <div class="card">
      <button type="button" @click="count++">count is {{ count }}</button>
    </div>

     <div class="card">
      <button type="button" @click="count = 0">Reset Counter</button>
    </div>

    <div class="card">
      <input type="text" placeholder="Type something" v-model="dataEntered" />
      <p>Typed text: {{ filteredValues }}</p>
    </div>
  </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
  props: {
    msg: String,
  },
  setup(props) {
    const count = ref(0);
    const dataEntered = ref(" ");
    const filteredValues = computed(() => {
      return dataEntered ? dataEntered : "";
    });

    return {
      count,
      dataEntered,
      filteredValues,
    };
  },
};
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
