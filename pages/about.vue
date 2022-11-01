<template>

  <div class="container">
    <nuxt-link to="/"> Back </nuxt-link>
        <br />
    <h1>About NUXT JS</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque eligendi praesentium sed dolore, ab sint earum ad accusantium error dignissimos! Magnam facilis ea natus excepturi quod culpa earum aut voluptates.</p>
  </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'About Nuxt',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'This is the content'
                }
            ]
        }
    }
}
</script>

<style>

</style>