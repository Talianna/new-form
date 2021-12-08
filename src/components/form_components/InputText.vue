<template>
    <div>
        <label>Text</label>
        <input 
        @input="$emit('input', $event.target.value)"
        :type="type"
        :label="label"
        :value="value"
        class="form-input"             
        />

    </div>
</template>

<script>

export default {
    name: 'InputText',

    props: {
        type: {
            type: String,
            default: 'text'
        },

        label: {
            type: String,
            default: ''
        },

        value: {}                            
    },
}

</script>