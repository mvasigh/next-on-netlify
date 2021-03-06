# Changelog

## 2.1.0 (2020-06-14)

- Add support for [NextJS optional catch-all routes](https://nextjs.org/docs/api-routes/dynamic-api-routes#optional-catch-all-api-routes) ([#15](https://github.com/FinnWoelm/next-on-netlify/pull/15))
- Fix: An `index.js` page with `getStaticProps` no longer causes `next-on-netlify` to fail ([#18](https://github.com/FinnWoelm/next-on-netlify/pull/18))
- Fix: Catch-all routes now correctly require that at least one URL parameter is present (unlike optional catch-all routes) ([479b7e7](https://github.com/FinnWoelm/next-on-netlify/commit/479b7e73f1a11778eb5ef66ded02aa1c17e38697))
- Fix: Data routes now correctly work for pages with catch-all routing ([0412b45](https://github.com/FinnWoelm/next-on-netlify/commit/0412b45fe3917a082be563c1720e85cf3affd4e1))

## 2.0.0 (2020-06-02)

- **Breaking: You must change your `netlify.toml` configuration for next-on-netlify v2.0.0.** Please [look at the README](https://github.com/FinnWoelm/next-on-netlify#3-configure-netlify) for the latest configuration.  
`next-on-netlify` now builds pre-rendered pages and static assets in `out_publish`. Netlify Functions for SSR pages are built to `out_functions`.
- Add support for `getStaticProps` ([#7](https://github.com/FinnWoelm/next-on-netlify/issues/7))
- Add support for `getStaticPaths` with and without fallback ([#7](https://github.com/FinnWoelm/next-on-netlify/issues/7))
- Add support for `getServerSideProps` ([#7](https://github.com/FinnWoelm/next-on-netlify/issues/7))
- Query string parameters are now correctly passed to Next Pages and API endpoints ([#9](https://github.com/FinnWoelm/next-on-netlify/issues/9))
- Response headers are now correctly set ([#9](https://github.com/FinnWoelm/next-on-netlify/issues/9#issuecomment-633288179))
- When a user encounters a 404, `next-on-netlify` now display the NextJS 404 page rather than Netlify's default 404 page. You can [customize the NextJS 404 page](https://nextjs.org/docs/advanced-features/custom-error-page#customizing-the-404-page).
 ([#2](https://github.com/FinnWoelm/next-on-netlify/issues/2))
- Every page with server-side rendering is now converted to a stand-alone Netlify Function. Previously, all SSR pages were bundled in a single Netlify Function.
- `next-on-netlify` now prints out which pages are being converted to Netlify Functions for SSR, which pages are served as pre-rendered HTML, and the redirects that are being generated.
- Adding custom redirects via a `_redirects` file in the project root is no longer supported. Let me know if you want this back. Or define your redirects in `netlify.toml`.

## 1.2.0 (2020-04-26)

- Add support for custom NextJS build directory: If `distDir` is specified in
  `next.config.js`, next-on-netlify will use that directory. If no `distDir` is
  specified, it will look for the default directory (`.next`).

## 1.1.0 (2020-04-19)

- Add support for catch-all routes ([#1](https://github.com/FinnWoelm/next-on-netlify/pull/1), [#5](https://github.com/FinnWoelm/next-on-netlify/pull/5))
- README: Fix instructions for local preview

## 1.0.1 (2020-01-27)

- Add README
- Add CHANGELOG

## 1.0.0 (2020-01-26)

Initial release of next-on-netlify
