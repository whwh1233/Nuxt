<style scoped></style>

<template>
  <div>
    <h1>子组件展示</h1>
    <br />
    <p>{{ message }}</p>
    <br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '子组件展示'
    }
  }
}
</script>
