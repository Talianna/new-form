<template>
  <div>
    <form class="form" @submit.prevent="onSubmit">

      <!-- <p>{{ text }} {{ email }} {{ phone }} {{ url }} {{ number }} {{ date }} {{ select }}</p> -->

      <div class="input-group">

        <div>
          <p>{{ text }}</p>
          <FormInput 
            v-model="text"
            label="Text" 
            type="text"
            placeholder="Your Text Here"
          />
        </div>

        <div>
          <p>{{ email }}</p>
          <FormInput 
            v-model="email"
            label="Email" 
            type="email"
            placeholder="Your Email Here"
          />
        </div>
      </div>

      <!-- <currency-input 
        label="Price" 
        v-model="price"      
      ></currency-input> -->

      <div class="input-group">
        <div>
          <p>{{ phone }}</p>
          <FormInput 
            v-model="phone"
            label="Phone" 
            type="tel"
            placeholder="Your Phone Here"
          />
        </div>

        <div>
          <p>{{ date }}</p>
          <FormInput 
            v-model="date"
            label="Date" 
            type="date"
            placeholder="Your Date Here"
          />
        </div>
      </div>

      <div class="input-group">
        <div>
          <p>{{ number }}</p>
          <FormInput 
            v-model="number"
            label="Number" 
            type="number"
            placeholder="Your Number Here"
          />
        </div>

        <div>
          <p>{{ select }}</p>
          <FormSelect 
            v-model="select"
            label="Select" 
            type="select"
            placeholder="Select smth"
          />
        </div>
      </div>

      <div class="input-group">

        <div>
          <p>{{  }}</p>
          <div class="input-group"> 
            <div>
              <input type="radio" id="contactChoice1" name="contact" value="email">
              <label for="contactChoice1">Email</label>
            </div>

            <div>
              <input type="radio" id="contactChoice2" name="contact" value="phone">
              <label for="contactChoice2">Phone</label>
            </div>

            <div>
              <input type="radio" id="contactChoice3" name="contact" value="mail">
              <label for="contactChoice3">Mail</label>
            </div>
          </div>
        </div>

        <div>
          <p>{{  }}</p>
          <div class="input-group"> 
            <div>
              <input type="checkbox" id="subscribeNews1" name="subscribe" value="newsletter">
              <label for="subscribeNews">Subscribe to newsletter?</label>
            </div>

            <div>
              <input type="checkbox" id="subscribeNews2" name="subscribe" value="newsletter">
              <label for="subscribeNews">Subscribe to?</label>
            </div>

            <div>
              <input type="checkbox" id="subscribeNews3" name="subscribe" value="newsletter">
              <label for="subscribeNews">Subscribe?</label>
            </div>
          </div>
        </div>
      </div>

      <textarea class="form-input form-textarea" name="" id="" cols="30" rows="10"></textarea>

      <button type="submit" class="form-btn">Submit</button>
    </form>
  </div>
</template>

<script>
import FormInput from './form_components/FormInput.vue'
import CurrencyInput from './form_components/CurrencyInput.vue'
import FormSelect from './form_components/FormSelect.vue'

export default {
  name: 'Form',

  components: {
    FormInput,
    CurrencyInput,
    FormSelect
  },

  data: () => ({
    text: '',
    email: '',
    phone: '',
    url: '',
    number: '',
    date: '',
    select: '',

    price: 0,
    shipping: 0,
    handling: 0,
    discount: 0
  }),

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