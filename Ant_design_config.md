# Ant design 配置

https://antdv.com/docs/vue/introduce-cn

## 1. 安裝 ant-design-vue@next

```
npm install ant-design-vue --save
```

## 2. 安裝 unplugin-vue-components/vite

```
npm i unplugin-vue-components
```

## 2. 修改 vite.config.js

```
import Components from 'unplugin-vue-components/vite';
import { AntDesignVueResolver } from 'unplugin-vue-components/resolvers';

export default {
  plugins: [
    /* ... */
    Components({
      resolvers: [AntDesignVueResolver()],
    }),
  ],
};
```

