<template>
  <span />
</template>

<script>
export default {
  props: {
    title: { type: String, required: true },
    description: { type: String, required: true },
    imageSrc: { type: String, required: true },
    imageAlt: { type: String, required: true }
  },
  head () {
    return {
      meta: [
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.title
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.description
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content: this.imageSrc
        },
        {
          hid: 'twitter:image:alt',
          name: 'twitter:image:alt',
          content: this.imageAlt
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.title
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.description
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: this.imageSrc
        },
        {
          hid: 'og:image:secure_url',
          property: 'og:image:secure_url',
          content: this.imageSrc
        },
        {
          hid: 'og:image:alt',
          property: 'og:image:alt',
          content: this.imageAlt
        }
      ]
    }
  }
}
</script>

<style>
</style>
