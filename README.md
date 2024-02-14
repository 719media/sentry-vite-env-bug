# test-env-vite-sentry

This is an example repo of a problem with vite and vue env parsing when @sentry/vite-plugin is installed


## Repository Setup (these have all been committed into the repo already in steps in commits, skip to Bug Reproduction to see the bug)

```sh
npm create vue@latest
vi .env
#VITE_testerson=TestDev
vi .env.production
#VITE_testerson=TestProd
vi index.html
#<meta name="testerson" content="%VITE_testerson%">
npm install
npm install @sentry/vite-plugin
vi vite.config.js
#add in appropriate sentry config, comment out SentryPlugin
```

### Bug Reproduction

```sh
npm run build
#check out dist/index.html, note value of line: <meta name="testerson" content="TestProd">
vi vite.config.js
#remove sentry comment
#check out dist/index.html, note value of line: 
```
