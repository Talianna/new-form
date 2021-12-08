<template>
  <div>
    <p>form</p>
    <form class="form" @submit.prevent="onSubmit">

      <input class="form-input" type="text">
      <input class="form-input" type="email">
      <input class="form-input" type="tel">
      <input class="form-input" type="url">
      <input class="form-input" type="number">
      <input class="form-input" type="date">

      <select class="form-input">
        <option>5</option>
        <option>4</option>
        <option>3</option>
        <option>2</option>
        <option>1</option>
      </select>

      <textarea class="form-input" name="" id="" cols="30" rows="10"></textarea>

      <button type="submit" class="form-btn">Submit</button>

    </form>
  </div>
</template>

<script>
  export default {
    name: 'Form'
  }

</script>