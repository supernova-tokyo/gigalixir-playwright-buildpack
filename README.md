# Gigalixir Playwright Buildpack

This buildpack installs all the needed dependencies to use Playwright with Chromium and Firefox on Gigalixir.

## Usage

## Examples

### Chromium

For using Chromium, it's **necessary** to use `chromiumSandbox: false` in the launch options, since is no support for the Chromium sandbox.

```javascript
const { chromium } = require("playwright-chromium");

(async () => {
  const browser = await chromium.launch({ chromiumSandbox: false });
  const context = await browser.newContext();
  const page = await context.newPage();
  await page.goto("http://whatsmyuseragent.org/");
  await page.screenshot({ path: `chromium.png` });
  await browser.close();
})();
```

### Firefox

For Firefox, you can refer to the official examples, no need to adjust any configurations.

```javascript
const { firefox } = require("playwright-firefox");

(async () => {
  const browser = await chromium.launch();
  const context = await browser.newContext();
  const page = await context.newPage();
  await page.goto("http://whatsmyuseragent.org/");
  await page.screenshot({ path: `firefox.png` });
  await browser.close();
})();
```
