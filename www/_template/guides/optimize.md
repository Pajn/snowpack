---
layout: layouts/content.njk
title: Optimize for production
---

There are several plugins available to optimize your final build with popular bundlers like Webpack, Parcel, and (more recently) Rollup. Third-party bundlers are well-tested and well-supported, making them a great choice for production builds.

**[@snowpack/plugin-webpack](/guides/webpack) is currently our recommended stable bundler for production websites.**

Snowpack recently released an optimization pipeline powered by [esbuild](https://esbuild.github.io/). While this built-in pipeline can optimize your build 10x faster than Webpack or Rollup, esbuild is still young and [not yet production-ready](https://esbuild.github.io/faq/#production-readiness). Therefore, we currently only recommended this for smaller projects.

## Recommended: Optimize your build with Webpack

Connect the `"@snowpack/plugin-webpack"` plugin in your Snowpack configuration file and then run `snowpack build` to see your optimized, _bundled_ build.

```js
// snowpack.config.js
// [npm install @snowpack/plugin-webpack]
{
  "plugins": [["@snowpack/plugin-webpack", {/* ... */}]]
}
```

You can extend the default webpack configuration to customize your bundled output:

```js
// snowpack.config.js
// [npm install @snowpack/plugin-webpack]
{
  "plugins": [["@snowpack/plugin-webpack", {
    extendConfig: (webpackConfig) {
      /* ... */
      return webpackConfig;
    }
  }]]
}
```

## Future: Optimize your build with esbuild (built-in)

TODO
