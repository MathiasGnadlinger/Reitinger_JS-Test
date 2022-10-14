<template>
  <div id="app">
    <h3>Example</h3>
    <form @submit.prevent="addNew">
      <label> Enter new subject:</label>
      <input v-model="newSubject" />
      <button>Add subject</button>
      <hr />
    </form>
    <ul>
      <li v-for="item in subjectArray">
        {{ item.content }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const newSubject = ref('');
    const subjectArray = ref([]);

    function addNew() {
      subjectArray.value.push({
        content: newSubject.value,
      });
      console.log('newSubject');
    }

    return {
      newSubject,
      subjectArray,
      addNew,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>