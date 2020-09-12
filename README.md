# VuTube

VueTube is a youtube video player. You can search videos among the ones in youtube and play each one you want.

## Pre Requirements

* First of all you should go to the [Google's developer console](https://developers.google.com/) and obtain an API key 
for [Youtube Data API](https://developers.google.com/youtube/v3). 

* Then copy the `.env.example` file to `.env`.

```cp .env.example .env```

* Set your API key in front of `VUE_APP_GOOGLE_API_KEY`.

## Development notes

This application is developed with [vue/cli](https://cli.vuejs.org/) 4.4.6.

1. Install dependencies
```
npm install
```

2. Compiles and hot-reloads for development
```
npm run serve
```

3. Lints and fixes files
```
npm run lint
```

## Deployment notes

* Compiles and minifies for production
```
npm run build
```

## Customize configuration

For more configuration see [Configuration Reference](https://cli.vuejs.org/config/).
