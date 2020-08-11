

### Reference

#### Docs

- [`getStaticProps`][docs_getStaticProps]

#### Articles

- [Image optimaztion in Next <sup>(Code Conqueror)</sup>][article_imageOptimization]

#### Frameworks

- Handling plugins:
  - [`next-compose-plugins`][lib_next_compose_plugins]
- Easy webpack-like relative image import
  - [`next-images`][lib_next_images]
- Webpack-like static asset optimization
  - [`next-optimized-images`][lib_next_optimized_images]


### Cons

Unclear documentation about hidden functionality with pages dir, public dir,  _app, etc.

#### Cant use `getStaticProps` with `_app`

https://github.com/vercel/next.js/discussions/11334

#### pages cant use fs unless in a `getStaticProps` or `getServerSideProps`

https://github.com/vercel/next.js/issues/8251

https://github.com/vercel/next.js/issues/7755#issuecomment-624544303

#### `_app` cant use fs unless its used in `getInitialProps`

https://github.com/vercel/next.js/issues/7755


[docs_getStaticProps]: https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation
[article_imageOptimization]: https://codeconqueror.com/blog/image-optimization-with-next-js

[lib_next_optimized_images]: https://github.com/cyrilwanner/next-optimized-images
[lib_next_images]: https://github.com/twopluszero/next-images
[lib_next_compose_plugins]: https://github.com/cyrilwanner/next-compose-plugins
