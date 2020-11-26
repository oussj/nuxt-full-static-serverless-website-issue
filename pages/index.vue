<template>
  <div class="container">
    <div>
      <h1 class="title">Primary page</h1>
      <div class="links">
        <div>{{ message }}</div>
        <br />
        <nuxt-link to="test" class="button--grey"
          >Go to secondary page</nuxt-link
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const response = await $axios.$get(
      'https://dummyapi.io/data/api/user/0F8JIqi4zwvb77FGz6Wt',
      { headers: { 'app-id': '5fc022fd4b8d1f42ca9c3822' } }
    )

    return {
      message: response.email,
    }
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: block;
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
