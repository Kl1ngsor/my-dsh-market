# my-dsh-market

DeepSeek Harness 插件市场索引，供 DSH 的「插件 → 发现」页面读取。

## 安装步骤

打开 DSH，进入「插件」→「发现」标签，点击「添加索引源」，填入：

```
https://kl1ngsor.github.io/my-dsh-market/index.json
```

## 更新插件列表

编辑 `index.json` 的 `plugins` 数组，然后：

```bash
git add index.json && git commit -m "update index" && git push
```

GitHub Pages 大约 1 分钟后生效，在「发现」页点右上角「刷新」即可看到变化。

## 校验

推送前可以用官方校验器确认格式正确：

```bash
node -e "
const { parseMarketIndex } = require('@deepseek-ai/dsh-plugin-market-index')
const raw = require('./index.json')
console.log(parseMarketIndex(raw, 'https://kl1ngsor.github.io/my-dsh-market/index.json'))
"
```
