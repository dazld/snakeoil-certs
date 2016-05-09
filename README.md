# Development HTTPS certificates

* DO NOT USE OUTSIDE OF LOCALHOST *

Certificates created by `pem` module and saved into a module for import by other scripts (eg. livereload) and consistency.

## Exports

`csr` - cert signing request

`clientKey` - certificate key

`certificate` - the https cert itself

`serviceKey` - service key

## Usage

```

const https = require('https');
const snakeoil = require('@dazld/snakeoil-certs');
const someExpressApp = require('your-express-app-or-whatever');


const server = https.createServer({
    key: snakeoil.serviceKey,
    cert: keys.certificate
},someExpressApp).listen(3030);

// in gulp livereload

const livereload = require('gulp-livereload');

livereload.listen({
    key: snakeoil.serviceKey,
    cert: keys.certificate
});

// etc - now both the livereload and main server are using same keys
```




