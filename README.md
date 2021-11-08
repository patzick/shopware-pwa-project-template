# shopware-pwa

You have a running shopware-pwa project now, ready for your commands!

If you are not familiar with the project, visit [official documentation](https://shopware-pwa-docs.vuestorefront.io/) to get the details.

## Live customization

Feel free to customize the application by using standard CLI commands in the codesandbox's terminal - **open the new one next to the dev terminal with the nuxt output**.

```bash
yarn shopware-pwa -h

shopware-pwa version

  version (v)     Output the version number
  build           Build your project for production
  build-theme     Build your theme for Shopware PWA projects.
  create-theme    Create new theme for Shopware PWA projects.
  dev             Run the initialised project for development.
  dev-theme       Develop your theme for Shopware PWA projects.
  init (i)        Create new Shopware PWA project inside the current directory. Can be invoked multiple times for actualisations.
  override (o)    Allows you to override theme component. Component will appear in project ready to be edited.
  snippets        Provides snippets support for Shopware PWA
```

### An example of component customization

1. use the `override` command to override the specific cms block (vue component)

```bash
$ yarn shopware-pwa override

✔ Type or select component to override · /SwLogo.vue
Component overrided. You can edit it in src/components/SwLogo.vue
```

2. Edit component

```bash
$ vim src/components/SwLogo.vue

<template>
  <nuxt-link
    :to="$i18n.path('/')"
    class="sf-header__logo"
    data-cy="header-logo"
  >
    <SfImage src="/img/logo.svg" :alt="$t('page.title')" />
  </nuxt-link>
</template>

<script>
import { SfImage } from "@storefront-ui/vue"

export default {
  components: {
    SfImage,
  },
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables";

.sf-header__logo {
  height: 2rem;
}
</style>

```

3. Save and that's all. The application is being reloaded on the fly. Now you have your own logo component in shopware-pwa!
