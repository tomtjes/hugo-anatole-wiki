# 🛡️ Security
## Content Security Policy

The theme is compliant with the most strict CSP policies out of the box. A sample CSP for an Anatole-based site would look something like this:

```text
Content-Security-Policy "
  base-uri 'self';
  connect-src 'self';
  default-src 'self';
  frame-ancestors 'none';
  font-src 'self' cdnjs.cloudflare.com;
  img-src 'self';
  object-src 'none';
  script-src 'self';
  style-src 'self' cdnjs.cloudflare.com;
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
  Content-Security-Policy:  base-uri 'self'; connect-src 'self'; default-src 'self'; frame-ancestors 'none'; font-src 'self' cdnjs.cloudflare.com; img-src 'self'; object-src 'none'; script-src 'self'; style-src 'self' cdnjs.cloudflare.com;
  Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```