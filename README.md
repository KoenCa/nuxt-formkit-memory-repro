# Nuxt 3 with Formkit memory leak reproduction

Basic Nuxt 3 app to reproduce the memory leak caused by Formkit

### Setup

Install dependencies and make a build. Run the build with the inspect flag so
that the node process can be debugged.

```
npm install
npm run build
node --inspect .output/server/index.mjs
```

In chrome go to `chrome://inspect` and click on the 'inspect' link below the remote
target for `.output/server/index.mjs`. A new DevTools window opens up, go to the
Memory tab to see the current memory usage of Node/Nuxt. Now when you start refreshing
the home page you will see the memory going up and it never goes back down.
