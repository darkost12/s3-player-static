# Custom S3 Music Player

A lightweight, browser-based music player for songs hosted on S3.

### Demo
Check it out here: [Live Demo](https://darkost12.github.io/s3-player-static/)

![Demonstration](https://github.com/darkost12/s3-player-static/blob/main/demonstration.png)

> Demo songs are either in the public domain or licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

### Setup

Edit `scripts/config.js` to point at your bucket:

```js
window.APP_CONFIG = {
  FORCE_PATH_STYLE: true,        // set to false for AWS S3
  BUCKET: 'your-bucket',
  ENDPOINT: 'your-endpoint',     // without protocol, e.g. s3.amazonaws.com
  SUBPATH: 'music/',             // path inside the bucket where audio files live
  METADATA: 'metadata/',         // path for .yml lyrics/metadata files (optional)
  ACCESS_KEY: '',                // leave empty for a public bucket
  SECRET_KEY: '',
}
```

For local development you can override config without touching `config.js` - copy it to `scripts/.local.config.js` and set your values there. The local file is loaded after `config.js` and overwrites it.

Make sure your bucket has CORS configured to allow requests from your domain.

### Private Buckets

Set `ACCESS_KEY` and `SECRET_KEY` in your config. The player will use the AWS SDK to sign requests client-side.

### S3 Key Encoding

S3 doesn't support some special characters in object keys. The player escapes them as `__{urlEncodedHex}__`. For example, `/` becomes `__2F__` and `:` becomes `__3A__`.

---
