<template>
  <div>
    <form class="form" @submit.prevent="onSubmit">

      <div class="input-group">
        <!-- <InputText :inputText="inputText" /> -->
          <!-- <p>Parent something: {{ innertext }}</p>
  <hr>
  Child:  -->
        <FormInput 
          :value="value"
          label="Text" 
          type="text"
          placeholder="Your Text Here"
        />

        <FormInput 
          :value="value"
          label="Email" 
          type="email"
          placeholder="Your Email Here"
        />
        <!-- <input class="form-input" type="text"> -->
        <!-- <input class="form-input" type="email"> -->
      </div>

      <currency-input 
        label="Price" 
        v-model="price"      
      ></currency-input>

      <div class="input-group">
        <FormInput 
          :value="value"
          label="Phone" 
          type="tel"
          placeholder="Your Phone Here"
        />

        <FormInput 
          :value="value"
          label="Url" 
          type="url"
          placeholder="Your Url Here"
        />
        <!-- <input class="form-input" type="tel">
        <input class="form-input" type="url"> -->
      </div>

      <div class="input-group">
        <FormInput 
          :value="value"
          label="Number" 
          type="number"
          placeholder="Your Number Here"
        />

        <FormInput 
          :value="value"
          label="Date" 
          type="date"
          placeholder="Your Date Here"
        />
        <!-- <input class="form-input" type="number">
        <input class="form-input" type="date"> -->
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
import FormInput from './form_components/FormInput.vue'
import CurrencyInput from './form_components/CurrencyInput.vue'

export default {
  name: 'Form',

  components: {
    FormInput,
    CurrencyInput
  },

  data: () => ({
    value: '',

    // fields: [],
    // inputType: '',


    price: 0,
    shipping: 0,
    handling: 0,
    discount: 0
  }),

  //   data: {

  // },
  computed: {
    total: function () {
      return ((
        this.price * 100 + 
        this.shipping * 100 + 
        this.handling * 100 - 
        this.discount * 100
      ) / 100).toFixed(2)
    }
  }
}

</script>