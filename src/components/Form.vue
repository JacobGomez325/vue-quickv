<script setup>
  import {reactive} from 'vue'
  import QuickvForm from '@/components/QuickvForm.vue'
  import QuickvInput from '@/components/QuickvInput.vue'

  const formData = reactive({
    firstName:'',
    lastName:'',
    email:'',
    phoneNumber:'',
    age:'',
    password:''
  })
  


</script>
<template>
  <div>
    <quickv-form formId="authForm" name="myAuthForm">
      <div class="grid grid-cols-2 gap-4 container mx-auto my-4">
        <QuickvInput
          inputId="firstName"
          inputName="myInputFirstName"
          fieldPlaceholder="firstName" 
          label="firstName"
          qvRules='required|minlength:3|maxlength:20'
          qvMessages='The firstname is required | The name should be at least 3 characters | The field size should not exceed 20 characters'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.firstName"
        />
        <QuickvInput
          inputId="lastName"
          inputName="myInputLastName"
          fieldPlaceholder="lastName" 
          label="lastName"
          qvRules='required|minlength:3|maxlength:20'
          qvMessages='The lastname is required | The name should be at least 3 characters | The field size should not exceed 20 characters'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.lastName"
        />
        <QuickvInput
          inputId="email"
          inputName="myInputEmail"
          type="email"
          fieldPlaceholder="Email" 
          label="email"
          qvRules='required|email'
          qvMessages='The email is required | invalid email'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.email"
        />
        <QuickvInput
          inputId="phoneNumber"
          inputName="myInputPhone"
          type="number"
          fieldPlaceholder="PhoneNumber" 
          label="phoneNumber"
          qvRules='required|number'
          qvMessages='The phoneNumber is required | invalid number'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.phoneNumber"
        />
        <QuickvInput
          inputId="age"
          inputName="myInputAge"
          type="number"
          fieldPlaceholder="Age" 
          label="Age"
          qvRules='required|number|between:18,35'
          qvMessages='age is required | invalid number| number between 18 and 35'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.age"
        />
        <QuickvInput
          inputId="password"
          inputName="myInputPassword"
          type="password"
          fieldPlaceholder="Password" 
          label="password"
          qvRules='required|password'
          qvMessages='password is required |invalide password ,password contain  !@#$%^&*(),.?":{}|<>'
          qvInvalidClass='border border-red-500'
          qvValidClass='border border-green-500'
          v-model="formData.password"
        />
      </div>


    </quickv-form>

  </div>
</template>

<style  scoped>

</style>