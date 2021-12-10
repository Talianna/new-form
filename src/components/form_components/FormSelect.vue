<template>
    <div>
        <label v-if="label">{{ label }}</label>

        <select
            @input="$emit('input', $event.target.value)"
            :value="value"
            :type="type"
            :label="label"
            :name="name"
            :placeholder="placeholder"
            class="form-input"
        >
            <option v-for="(option, index) in options" :value="option.value" :key="index">
                {{ option.text }}
            </option>
        </select>
    </div>
</template>

<script>
export default {
  name: "FormSelect",

  data: () => ({
    inputVal: "",

    selected: "",
    options: [
      { text: "Один", value: "1" },
      { text: "Два", value: "2" },
      { text: "Три", value: "3" },
    ],
  }),

  watch: {
    value: function (newValue) {
      this.$emit("update:value", newValue);
    },
  },

  props: {
    type: {
      type: String,
      default: "text",
    },

    label: {
      type: String,
      default: "",
    },

    name: {
      type: String,
      default: "",
    },

    placeholder: {
      type: String,
      default: "",
    },

    value: {},
  }
};
</script>
