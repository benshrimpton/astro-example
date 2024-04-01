<script setup>
import { ref, onMounted } from 'vue';
const data = ref(null);
function foo() {
  alert('Foo');
}
onMounted(() => {
  fetch('https://jsonplaceholder.typicode.com/todos')
    .then((response) => response.json())
    .then((json) => (data.value = json));
});
</script>

<template>
  <div>
    <div v-if="data">
      <div v-for="i in data" :key="i.id" style="border : solid 1px:">
        {{ i.title }}
      </div>
    </div>
    <button @click="foo">buttton</button>
  </div>
</template>
