<template>
  <div class="container">
    <div>
      <h1 class="title">Secondary page</h1>
      <div class="links">
        <div>{{ message }}</div>
        <br />
        <nuxt-link to="/" class="button--grey">Go to home page</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const response = await $axios.$get(
      'https://dummyapi.io/data/api/post/SFAt3mJK0qu4QOd9LgSX/comment?limit=10',
      { headers: { 'app-id': '5fc022fd4b8d1f42ca9c3822' } }
    )

    return {
      message: response.data[0].message,
    }
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
