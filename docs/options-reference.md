# Options

Here are all the options available when configuring the module and their default values:

```js
{
  // vue-i18n configuration
  vueI18n: {},

  // If true, vue-i18n-loader is added to Nuxt's Webpack config
  vueI18nLoader: false,

  // List of locales supported by your app
  // This can either be an array of codes: ['en', 'fr', 'es']
  // Or an array of objects for more complex configurations:
  // [
  //   { code: 'en', iso: 'en-US', file: 'en.js' },
  //   { code: 'fr', iso: 'fr-FR', file: 'fr.js' },
  //   { code: 'es', iso: 'es-ES', file: 'es.js' }
  // ]
  //   `iso` value should have either:
  //   - code of ISO 639-1 (e.g. 'en')
  //   - code of ISO 639-1 and code of ISO 3166-1 alpha-2, with a hyphen (e.g. 'en-US')
  locales: [],

  // The app's default locale, URLs for this locale won't have a prefix if
  // strategy is prefix_except_default
  defaultLocale: null,

  // Separator used to generated routes name for each locale, you shouldn't
  // need to change this
  routesNameSeparator: '___',

  // Suffix added to generated routes name for default locale if strategy is prefix_and_default,
  // you shouldn't need to change this
  defaultLocaleRouteNameSuffix: 'default',

  // Routes generation strategy, can be set to one of the following:
  // - 'no_prefix': routes won't be prefixed
  // - 'prefix_except_default': add locale prefix for every locale except default
  // - 'prefix': add locale prefix for every locale
  // - 'prefix_and_default': add locale prefix for every locale and default
  strategy: 'prefix_except_default',

  // Wether or not the translations should be lazy-loaded, if this is enabled,
  // you MUST configure langDir option, and locales must be an array of objects,
  // each containing a file key
  lazy: false,

  // Directory that contains translations files when lazy-loading messages,
  // this CAN NOT be empty if lazy-loading is enabled
  langDir: null,

  // Set this to a path to which you want to redirect users accessing root URL (/)
  rootRedirect: null,

  // Enable browser language detection to automatically redirect user
  // to their preferred language as they visit your app for the first time
  // Set to false to disable
  detectBrowserLanguage: {
    // If enabled, a cookie is set once a user has been redirected to his
    // preferred language to prevent subsequent redirections
    // Set to false to redirect every time
    useCookie: true,
    // Set to override the default domain of the cookie. Defaults to host of the site.
    cookieDomain: null
    // Cookie name
    cookieKey: 'i18n_redirected',
    // Set to always redirect to value stored in the cookie, not just once
    alwaysRedirect: false,
    // If no locale for the browsers locale is a match, use this one as a fallback
    fallbackLocale: null
  },

  // Set this to true if you're using different domains for each language
  // If enabled, no prefix is added to your routes and you MUST configure locales
  // as an array of objects, each containing a domain key
  differentDomains: false,

  // If using different domains, set this to true to get hostname from X-Forwared-Host
  // HTTP header instead of window.location
  forwardedHost: false,

  // If true, SEO metadata is generated for routes that have i18n enabled.
  // Note that performance can suffer with this enabled and there might be compatibility
  // issues with some plugins. Recommended way is to set up SEO as described in:
  // https://nuxt-community.github.io/nuxt-i18n/seo.html#improving-performance
  seo: false,

  // Fallback base URL to use as prefix for alternate URLs in hreflang tags.
  // By default VueRouter's base URL will be used and only if that is not available,
  // fallback URL will be used.
  baseUrl: '',

  // By default a store module is registered and kept in sync with the
  // app's i18n current state
  // Set to false to disable
  vuex: {
    // Module namespace
    moduleName: 'i18n',

    // If enabled, current app's locale is synced with nuxt-i18n store module
    syncLocale: false,

    // If enabled, current translation messages are synced with nuxt-i18n store module
    syncMessages: false,

    // Mutation to commit to set route parameters translations
    syncRouteParams: true
  },

  // By default, custom routes are extracted from page files using babel parser,
  // set this to false to disable this
  parsePages: true,

  // If parsePages option is disabled, the module will look for custom routes in
  // the pages option, refer to the "Routing" section for usage
  pages: {},

  // By default, custom paths will be encoded using encodeURI method.
  // This does not work with regexp: "/foo/:slug-:id(\\d+)". If you want to use
  // regexp in the path, then set this option to false, and make sure you process
  // path encoding yourself.
  encodePaths: true,

  // Called right before app's locale changes
  beforeLanguageSwitch: (oldLocale, newLocale) => null,

  // Called after app's locale has changed
  onLanguageSwitched: (oldLocale, newLocale) => null
}
```
