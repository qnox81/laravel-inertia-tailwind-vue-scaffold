# Laravel Scaffold

Scaffold for new laravel projects. In a nut shell, it's a basic laravel app, with added the following stack:

- Laravel (obviously) 7.x
- Inertia.js
- TailwindCSS
- TailwindUI
- Vue

## Installing

```bash
$ composer create-project --prefer-dist qnox81/laravel-scaffold app-name
```

## Packages

I've pre-installed a bunch of packages I end up installing on every project anyway. You can see a list of them in the
[composer.json](./composer.json) file.


## Docker

I've added docker for local development on mac with containers:
- app
- db
- nginx
- composer
- artisan

Details in [docker-composer.yml](./docker/docker-composer.yml) file.

## Front End Scaffolding

I'm using a fairly heavily modified version of [harmonic's inertia preset](https://github.com/Harmonic/laravel-preset).
At some point, I'll update this to make it more customised.

## Licence
MIT :)

## Attribution

Heavly based on atymic/laravel-scaffold: great job!
