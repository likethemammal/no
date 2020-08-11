
### Docs

- [`getStaticProps`][docs_getStaticProps]


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
