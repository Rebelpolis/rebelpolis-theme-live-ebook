<template>
  <Component
    :is="$layout"
    :key="$page.path"
  />
</template>

<script>
import Home from '@theme/layouts/Home'
import Chapter from '@theme/layouts/Chapter'

export default {
  components: {
    /* eslint-disable vue/no-unused-components */
    Home,
    Chapter,
    /* eslint-enable vue/no-unused-components */
  },

  computed: {
    $layout () {
      const defaultLayout = 'chapter'
      const layout = this.$page.frontmatter.layout || defaultLayout
      return layout.toLowerCase()
    },
  },
}
</script>

<style lang="stylus" src="@theme/styles/app.styl" />
