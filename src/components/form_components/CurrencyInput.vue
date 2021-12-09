<template>
    <div>
        <label v-if="label">{{ label }}</label>
        <input
            ref="input"
            :value="value"
            @input="updateValue($event.target.value)"
             class="form-input" 
        >
    </div>
</template>

<script>

export default {
    name:"CurrencyInput",

  props: {
    value: {
      type: Number,
      default: 0
    },
    label: {
      type: String,
      default: ''
    }
  },

    methods: {
        // Вместо того, чтобы обновлять значение напрямую,
        // в этом методе мы выполняем нормализацию и форматирование
        // введённого значения, а затем порождаем событие,
        // уведомляющее родительский компонент об изменениях

        updateValue: function (value) {
        var formattedValue = value
            // Удалить пробелы с обеих сторон
            .trim()
            // Сократить до 2 знаков после запятой
            .slice(
            0,
            value.indexOf('.') === -1
                ? value.length
                : value.indexOf('.') + 3
            )
        // Если значение не нормализовано — нормализуем вручную
        if (formattedValue !== value) {
            this.$refs.input.value = formattedValue
        }
        // Порождаем событие с обновлённым значением поля ввода
        this.$emit('input', Number(formattedValue))
        }
    }

}
</script>
