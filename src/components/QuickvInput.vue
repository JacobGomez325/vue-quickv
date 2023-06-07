<script setup>
  import { computed } from 'vue'
  const emits = defineEmits(['update:modelValue'])
  const props = defineProps({
    modelValue:{
      required:true
    },
    inputName:{
      type:String,
      default:'text'
    },
    inputId:{
      type:String,
      default:'text'
    },
    type:{
      type:String,
      default:'text'
    },
    label: {
      type:String,
      required: false,
    },
    
    fieldPlaceholder: {
      type:String,
      required: false,
      default:''
    },
    qvValidClass: {
      type:String,
      required: false,
      default:''
    },
    qvInvalidClass: {
      type:String,
      required: false,
      default:''
    },
    qvMessages: {
      type:String,
      required: true,
      default:''
    },
    qvRules: {
      type:String,
      required: true,
      default:''
    },
    feedbackClass: {
      type:String,
      required: false,
      default:'text-red-500 font-semibold text-sm'
    }
  },
  )

  const value = computed({
  get() {
    return props.modelValue
  },
  set(value) {
    emits('update:modelValue', value)
  }
})
</script>
<template>
  <div>
    <label :for="props.inputName" > {{ props.label }} </label>
    <input
      v-model="value"
      :type='props.type'
      :id="props.inputId"
      :name="props.inputName"
      :data-qv-rules="props.qvRules"
      :data-qv-messages="props.qvMessages"
      :data-qv-invalid-class="props.qvInvalidClass"
      :data-qv-valid-class="props.qvValidClass"
      :placeholder="props.fieldPlaceholder"
      class="px-4 py-2 mt-1 border-2 rounded-md border-gray-300 text-sm outile-none focus:outline-none focus:ring-2 w-full focus:ring-blue-500/50 focus:border-transparent"
    />
    <div :data-qv-feedback="props.inputName" :class="props.feedbackClass"></div>
  </div>
</template>
<style  scoped>

</style>