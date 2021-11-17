<template>
  <div class="home">
    <p>메시지: {{msg}} </p>
    <p v-once>다시는 변경하지 않습니다:{{msg}} </p>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>
