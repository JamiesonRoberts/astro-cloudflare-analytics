# Astro Cloudflare Analytics &middot;

Simple Integration for Astro (https://astro.build/) and Cloudflare Web
Analytics (https://www.cloudflare.com/web-analytics). Cloudflare Web Analytics is a simple and lightweight privacy-first
analytics and performance metrics service.

[Cloudflare Web Analytics Overview](https://developers.cloudflare.com/analytics/web-analytics/)

> Cloudflare Web Analytics provides free, privacy-first analytics for your website... All you need to enable
> Cloudflare Web Analytics is a Cloudflare account and a JavaScript snippet on your page to start getting information
> on page views and visitors.

## Usage

### Installation

`npm install astro-cloudflare-analytics --save`

### Implementation

Include the following wherever in your project you are handling the websites `<head>` tag and any related content. The following is an example with a site layout file.

```astro
// src/layourts/Layout.astro

---
import { CloudflareAnalytics } from 'astro-cloudflare-analytics'
---

<!doctype html>
<html lang='en-CA'>
  <head>
    ...
    <CloudflareAnalytics token='XXXXXXXXXXXXXXXXXX' />
  </head>
  <body>
  ...
  </body>
</html>
```

### Props for `CloudflareAnalytics`

| Name          | Type     | Description                                                                                                                                                                                         |
|---------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| token         | string   | The token provided by Cloudflare Web Analytics of the site you want to monitor. **Required**                                                                                                        |
| spaIsDisabled | boolean? | Set this to `true` to disable Cloudflare Web Analytics [Single Page Application measurements](https://developers.cloudflare.com/analytics/web-analytics/getting-started/web-analytics-spa/).        |
| partytown     | boolean? | Set this to `true` to enable the script to be flagged to load via Partytown and Astro's web worker framework. [Partytown Details](https://docs.astro.build/en/guides/integrations-guide/partytown/) |
