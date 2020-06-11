# SG Rain Radar Scribbler

> An experimental web app to load rain radar images from weather.gov.sg and allow scribbling of the images at 5-minute intervals while generating a JSON output of the radar with a "Download" button.

**✨✨ Intro tweet: https://twitter.com/cheeaun/status/1270361974258335750 ✨✨**

- Uses [Rethumb](https://rethumb.com/) as proxy for the image to solve the cross-origin problem so that pixel data can be read from the image.
- On first load, it will load the latest radar image, which might not be available.
  - 🐛 Known bug: if image fails, Rethumb will still cache it.
    - Fix it by appending a URL e.g. `?1` to the image path via DevTools.
  - 🐛 Known bug: the input has `max` set to "latest" time from first load.
    - The `max` will not update as time passes, so just reload the page.
- Weather.gov.sg seems to only save the radar images for the past week or few days. Anything older will return `404`.

Steps to run this:

- [`Node.js`](https://nodejs.org/) is required
- Run `npx serve` to start a local server

## Copyright & license

- Data
  - © [Data.gov.sg](https://data.gov.sg/privacy-and-website-terms#site-terms)
  - © [Meteorological Service Singapore](http://www.weather.gov.sg/terms-of-use)
  - © [National Environment Agency](http://www.nea.gov.sg/open-data-licence/)
- Code licensed under [MIT](https://cheeaun.mit-license.org/)
