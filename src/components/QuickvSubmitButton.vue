<script setup>
  
</script>

<template>
  <button data-qv-submit  class="px-4  py-2 text-white ">
    <slot></slot>
  </button>
</template>

<style  scoped>
[data-qv-submit]:disabled {
  background:#ccc
}

button {
  background:blue
}


</style>