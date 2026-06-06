# Custom S3 Music Player

A lightweight, browser-based music player for songs hosted on S3.

### Demo
Check it out here: [Live Demo](https://darkost12.github.io/s3-player-static/)

![Demonstration](https://github.com/darkost12/s3-player-static/blob/main/demonstration.png)

> Demo songs are either in the public domain or licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

### Using with Private Buckets
If you want to play songs from a private S3 bucket, you can provide your secret keys in any way you prefer. Make sure to handle your credentials securely and avoid exposing them in client-side code.

Don't forget to set the appropriate CORS configuration on your S3 bucket to allow access from your browser.

S3 doesn't support some special characters in object keys. Symbols are escaped in the format `__{urlEncodedHex}__`. For example, `/` becomes `__2F__` and `:` becomes `__3A__`.

---
