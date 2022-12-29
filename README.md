<p align="center">
  <a href="https://faable.com">
    <img src="https://www.faable.com/logo/Emblem.png" height="96">
    <h3 align="center">Faable</h3>
  </a>
</p>

<p align="center">
  Your React, Node.js or Python apps, up to the cloud in seconds.
</p>

## About this Docker Image

PHP8 image to run wordpress in `arm64` clusters

To run php with Nginx in Alpine

```Dockerfile
FROM boyander/php8-wordpress:nginx
```

To run php with Apache in Ubuntu

```Dockerfile
FROM boyander/php8-wordpress:apache
```

## Faable

Faable is a platform to build modern architectures that scale precisely to meet demand. We handle the hard stuff so you can focus on building cloud ready apps. Make your business cloud driven and join those awesome companies.

## References

- https://hub.docker.com/layers/alpine/k8s/1.23.15/images/sha256-a3a73b14c5cf3a8e11b5eaf5c0e79730f8d7dfcd7a951e7e8b8bd62df1a9996c?context=explore

- https://levelup.gitconnected.com/containerizing-nginx-php-fpm-on-alpine-linux-953430ea6dbc
