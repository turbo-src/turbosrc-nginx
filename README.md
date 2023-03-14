# tubosrc-nginx

A reverse proxy for a turbosrc api endpoint.

## nginx.conf

Follow instructions (e.g. edits) per `nginx-example.conf`.

## Needed files

You'll need the following files (names could be different) on your nginx server,

`/etc/nginx/nginx.conf`

and in a relative path (you'll have to define in you're `.conf` where asked in the `.conf`).

```
turbosrc-nginx-ssl-info/
  turbosrc-marialis.dev.key
  turbosrc-marialis_dev.ca-bundle
  turbosrc-marialis_dev_chain.crt
  turbosrc-marialis_dev.crt
  turbosrc-marialis_dev.csr
  turbosrc-marialis.dev.key
```

The `..dev.key` is the private key (need to verify) used to sign the info contained in the `.csr` file.

## nginx launch

To check for syntax errors in you `nginx.conf`

```
nginx -t
```

To start the nginx server

```
sudo systemctl restart nginx
```

To reload (e.g. after a config change)

```
sudo nginx -s reload
```

