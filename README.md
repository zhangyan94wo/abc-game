# 字母闯关乐园

一年级 26 个字母课堂互动游戏。整个游戏是一个 HTML 文件（`public/index.html`），不依赖任何框架，双击就能在浏览器里打开，也可以拷到 U 盘带去教室。

在线版：https://abc-game.zhangyan-abc.workers.dev/

## 玩法

| 玩法 | 内容 |
| --- | --- |
| 大小写连连看 | 大写找小写，配成一对一对 |
| 补全大小写 | Aa 到 Oo 连续字母里，找出缺的大写或小写 |
| 单词找字母 | 看图听音找首字母、按字母找图片、把图卡分到字母篮子 |
| 笔顺小能手 | 这个字母要写几笔 |
| 四线三格 | 字母占哪几格 |
| 字母大乱斗 | 以上题型随机出 |

每答对一题，从三张卡牌里抽一张：+3、+10、−1，三张牌每次重新洗牌。

「设置」里可以调学习范围（A 到 F…Z）、每轮题数和是否朗读单词。

## 内容来源

- 字母字体：书写体（Playwrite NZ，SIL 开放字体许可），已内置在文件里，离线也能显示；小写 i 加了起笔，和课堂书写范例一致。
- 单词：A–J 用课堂图卡上的 40 个常见词和原图；K–Z 暂用 Phonics Song 里的单词。
- 笔画数和占格：按照课堂书写范例（f 占三格）。E、M、m 的笔画在范例上不清晰，暂不出笔顺题。

## 部署到 Cloudflare Workers

需要 Node.js。在仓库根目录运行：

```bash
export CLOUDFLARE_API_TOKEN=你的令牌   # Windows 用 set
npx wrangler deploy
```

`wrangler.toml` 会把 `public/` 目录作为静态资源发布。更新游戏时，替换 `public/index.html` 后重新运行 `npx wrangler deploy`。

不要把令牌写进仓库里的任何文件。
