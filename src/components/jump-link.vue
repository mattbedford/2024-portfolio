<template>
  <a :href="`/#${link}`">{{ text }}<span></span></a>
</template>

<script>
export default {
props: ['link', 'text']    
}
</script>

<style>

</style>