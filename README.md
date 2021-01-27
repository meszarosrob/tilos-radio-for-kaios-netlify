# Companion site for the [Tilos Radio for KaiOS](https://github.com/meszarosrob/tilos-radio-for-kaios)

## Proxy

The app uses [`tilos-radio-for-kaios.netlify.app`](https://tilos-radio-for-kaios.netlify.app/) instead [`stream.tilos.hu`](http://stream.tilos.hu/)  for audio streaming. KaiOS requires the URL to be under `HTTPS`, and currently, it is not.

Setting up a [proxy](https://docs.netlify.com/routing/redirects/rewrites-proxies/#proxy-to-another-service) is a workaround, and hopefully, I can remove it once a certificate is added.

## Daily schedule

The Tilos Radio API rightfully blocks any AJAX requests that are not initialized from their domain.

Because I wanted to display the current show in the app, I'm saving and updating the data file locally and making it available [from the proxy site](https://tilos-radio-for-kaios.netlify.app/daily-schedule.json).
The data is updated every four hours using [GitHub Actions](https://github.com/meszarosrob/tilos-radio-for-kaios-netlify/blob/main/.github/workflows/update-daily-schedule.yml).
