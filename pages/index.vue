<template>
  <h1>Index {{ this.text }}</h1>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      text: ''
    }
  },
  mounted() {
    this.getText()
  },
  methods: {
    async getText() {
      let msg = await fetch('https://localhost:7032/API/Test/Testing/')
      const data = await msg.json()
      console.log(data)
      console.log(data.message)
      this.text = data.message
    }
  }
}
</script>
