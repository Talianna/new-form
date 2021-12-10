<template>
    <div>
        <label v-if="label">{{ label }}</label>

        <select 
            v-model="inputVal"
            :type="type"
            :label="label"
            :name="name"
            :placeholder="placeholder"
            class="form-input"
        >
            <option>5</option>
            <option>4</option>
            <option>3</option>
            <option>2</option>
            <option>1</option>
        </select>
    </div>
</template>

<script>

export default {
    name: "FormSelect",

        data: () => ({
        inputVal: ''
    }),

    watch:{
        value: function(newValue){
            this.$emit('update:value', newValue)
        }
    },

    props: {
        type: {
            type: String,
            default: 'text'
        },

        label: {
            type: String,
            default: ''
        },

        name: {
            type: String,
            default: ''
        },

        placeholder: {
            type: String,
            default: ''
        },
    },
}

</script>
