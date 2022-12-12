# emoji-mart-demo-vue3

Demo Vue 3 app for [emoji-mart-vue-fast component](https://github.com/serebrov/emoji-mart-vue): https://serebrov.github.io/emoji-mart-vue3-demo/

App was generated using [vue-cli](https://cli.vuejs.org/).

The component works, one difference from Vue 2 is that component needs to be imported from the `/src` subfolder:

```
import data from "emoji-mart-vue-fast/data/all.json";

// Note: component needs to be imported from /src subfolder:
import { Picker, EmojiIndex } from "emoji-mart-vue-fast/src";

// While in Vue 2 it works like this:
// import { Picker, EmojiIndex } from "emoji-mart-vue-fast";
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

## Update live version

To update live version at https://serebrov.github.io/emoji-mart-vue3-demo/, run:

```shell
git checkout build
git merge master
npm run build

git add .
git commit -m "Rebuild live example."
git push
```
