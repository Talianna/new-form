<template>
    <div>
        <label v-if="label">{{ label }}</label>
        <input 
            @input="$emit('input', $event.target.value)"
            :value="value"
            :type="type"
            :label="label"
            :name="name"
            :placeholder="placeholder"
            class="form-input"             
        />
    </div>
</template>

<script>

export default {
    name: 'FormInput',

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

        value: {}                            
    },
}

</script>