## Content Security Policy

The theme is compliant with the most strict CSP policies out of the box. A sample CSP for an Anatole-based site would look something like this:

```text
Content-Security-Policy "
  base-uri 'self';
  connect-src 'self';
  default-src 'self';
  frame-ancestors 'none';
  font-src 'self';
  img-src 'self';
  object-src 'none';
  script-src 'self';
  style-src 'self';
"
```

If you want to configure the security headers for a site running on Netlify, you want to make sure you create a special `_headers` file in your site's static folder. The content might look like the following:

```text
/*
  X-Frame-Options: DENY
  X-Clacks-Overhead: "GNU Terry Pratchett"
  X-XSS-Protection: 1; mode=block
  X-Content-Type-Options: nosniff
  Referrer-Policy: same-origin
  Content-Security-Policy:  base-uri 'self'; connect-src 'self'; default-src 'self'; frame-ancestors 'none'; font-src 'self'; img-src 'self'; object-src 'none'; script-src 'self'; style-src 'self';
  Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```

For configuring a CSP for Azure Static Web Apps, you will have to create a file named staticwebapp.config.json file in the root of your project with the following content:

```text
{
"globalHeaders": {
"X-Frame-Options": "DENY",
"X-XSS-Protection": "1; mode=block",
"X-Content-Type-Options": "nosniff",
"Referrer-Policy": "same-origin",
"Content-Security-Policy": "base-uri 'self'; connect-src 'self'; default-src 'self'; frame-ancestors 'none'; font-src 'self' cdnjs.cloudflare.com; img-src 'self'; object-src 'none'; script-src 'self'; style-src 'self' cdnjs.cloudflare.com;",
"Permissions-Policy": "accelerometer=(), ambient-light-sensor=(), autoplay=(), battery=(), camera=(), cross-origin-isolated=(), display-capture=(), document-domain=(), encrypted-media=(), execution-while-not-rendered=(), execution-while-out-of-viewport=(), fullscreen=(self), geolocation=(), gyroscope=(), keyboard-map=(), magnetometer=(), microphone=(), midi=(), navigation-override=(), payment=(), picture-in-picture=(), publickey-credentials-get=(), screen-wake-lock=(), sync-xhr=(), usb=(), web-share=(), xr-spatial-tracking=()",
"Strict-Transport-Security": "max-age=63072000; includeSubDomains; preload"
}
}
```