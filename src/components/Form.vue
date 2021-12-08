<template>
  <div>
    <p>form</p>
    <form class="form" @submit.prevent="onSubmit">

      <input type="text">
      <input type="email">
      <input type="tel">
      <input type="url">
      <input type="number">
      <input type="date">

      <select>
        <option>5</option>
        <option>4</option>
        <option>3</option>
        <option>2</option>
        <option>1</option>
      </select>

      <textarea name="" id="" cols="30" rows="10"></textarea>

      <button></button>


    </form>

  </div>
</template>

<script>
  export default {
    name: 'Form'
  }

</script>

<style scoped>

</style>
