<script setup>
  import QuickvSubmitButton from '@/components/QuickvSubmitButton.vue'
  import { onMounted } from 'vue'
  import  *  as  quickv  from  "quickv"

  onMounted(() => {
    const qv = new quickv.Quickv()
    qv.init()
  })

  const props = defineProps({
    formId:{
      type:Number,
      required:true
    },
    formName:{
      type:String,
      required:true
    },
    submitButtonText: {
      type:String,
      required:false,
      default:'submit form'
    }
  })


  const handleSubmit = function() {
    console.log("handleSubmit")
  }
</script>
<template>
  <form :id="props.formId" :name="props.formName" @submit.prevent="handleSubmit">
    <slot></slot>
    <div class="text-center">
      <quickv-submit-button :submitButtonText='submitButtonText' > 
        {{ props.submitButtonText }}
       </quickv-submit-button > 
    </div>
   </form>
</template>

<style  scoped>

</style>