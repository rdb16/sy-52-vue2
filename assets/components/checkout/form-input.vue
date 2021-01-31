<template>
  <div class="form-group">
    <label :for="id" class="col-form-label">
      {{ label }}
    </label>
    <input :type="type" 
            :id="id" 
            :name="id"
            :value="value"
            :class="{
              'is-invalid': !isValid,
              'form-control': true,
            }" 
            @input="$emit('input', $event.target.value)"
    />
    <span
      v-show="!isValid"
      class="invalid-feedback"
    >
        {{ errorMessage }}
    </span>
  </div>
</template>


<script>
export default {
  name: 'FormInput',
  props: {
    id: {
      type: String,
      reaquired: true
    },
    label: {
      type: String,
      reaquired: true
    },
    errorMessage: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text'
    },
    value: {
      type: String,
      default: ''
    },
    
  },
  computed: {
    isValid() {
      return !this.errorMessage
    }    
  },
  
}
</script>