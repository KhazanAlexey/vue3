<template>
<button class="btn">
<slot>

</slot>
</button>
</template>

<script>
export default {
  name: "MyButton"
}
</script>

<style scoped>
.btn{
  margin-top: 10px;
  padding: 10px 15px;
  color: green;
  border: 1px solid green;
}
</style>