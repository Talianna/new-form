<template>
  <div>
    <form class="form" @submit.prevent="onSubmit">

      <div class="input-group">
        <!-- <InputText :inputText="inputText" /> -->
          <!-- <p>Parent something: {{ innertext }}</p>
  <hr>
  Child:  -->
        <InputText 
        v-model="innertext"
        />
        <InputEmail />
        <!-- <input class="form-input" type="text"> -->
        <!-- <input class="form-input" type="email"> -->
      </div>

      <div class="input-group">
        <input class="form-input" type="tel">
        <input class="form-input" type="url">
      </div>

      <div class="input-group">
        <input class="form-input" type="number">
        <input class="form-input" type="date">
      </div>

      <div class="input-group">
        <select class="form-input">
          <option>5</option>
          <option>4</option>
          <option>3</option>
          <option>2</option>
          <option>1</option>
        </select>
      </div>

      <textarea class="form-input form-textarea" name="" id="" cols="30" rows="10"></textarea>

      <button type="submit" class="form-btn">Submit</button>
    </form>
  </div>
</template>

<script>
import InputText from './form_components/InputText.vue'
import InputEmail from './form_components/InputEmail.vue'

export default {
  name: 'Form',

  components: {
    InputText,
    InputEmail
  },

  data: () => ({
    innertext: "text"
  }),
}

</script>