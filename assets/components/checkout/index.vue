<template>
  <div class="row p-3">
    <div class="col-12">
    <form >
    <div class="form-row">
        <form-input
          id="customerName"
          v-model="form.customerName"
          class="col"
          v-bind="getFieldProps('customerName', 'Name :')"
        />
        <form-input
          id="customerEmail"         
          class="col"
          type="email"
          v-model="form.customerEmail"
          v-bind="getFieldProps('customerEmail', 'Email :')"
        />
  </div>
      <form-input
        v-bind="getFieldProps('customerAddress', 'Address :')"
        v-model="form.customerAddress"
        id="customerAdress"
      />
   <div class="form-row">
      <form-input
        id="customerCity"
        class="col"
        v-model="form.customerCity"
        v-bind="getFieldProps('customerCity', 'City :')"
      />
      <form-input
        id="customerZip"
        class="col"
        v-model="form.customerZip"
        v-bind="getFieldProps('customerZip', 'Zip Code :')"
      />
      <form-input
        id="customerPhone"
        class="col"
        type="tel"
        v-model="form.customerPhone"
        v-bind="getFieldProps('customerPhone', 'Phone Number :')"
      />
    </div> 
    </form>
    </div>
  </div>  
</template>

<script>
import FormInput from '@/components/checkout/form-input'

export default {
  name: 'CheckoutForm',
  components: { FormInput },
  data() {
    return {
      form: {
        customerName: '',
        customerEmail: '',
        customerAddress: '',
        customerZip: '',
        customerCity: '',
        customerPhone: '',
      },
      validationErrors: {},
    }
  },
  methods: {
    getFieldProps(id, label) {
      return {
        id,
        label,
        errorMessage: this.validationErrors[id],
      }
      
    },
  }
}
</script>