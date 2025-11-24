---
layout: ../../layouts/MarkdownPostLayout.astro
title: Astro Islandを使ってみる
author: Astro学習者
description: "Astro Islandを使ってみる"
image:
  url: "https://docs.astro.build/default-og-image.png"
  alt: "惑星と星のイラストの中にastroという単語があります。"
pubDate: 2025-11-24
tags: ["astro", "astro island"]
---
[Tutorial](https://docs.astro.build/ja/tutorial/6-islands/)をやってAstroアイランドを使ってみよう。早速新しいコマンドが出てきた。 `npx astro add preact` について調べてみる。

`npx astro` を見てみると、以下のように書いてある。

> add  Add an integration.

`npm install` しつつ、 `astro.config.mjs` 、 `tsconfig.json` 修正してくれる。

実際に小さいコードを書いていく。 `.jsx` でコンポーネントを書いたら、 `.astro` から普通に `import` してそのコンポーネントを使える。ここでHydrated Componentという概念の理解が必要となる。例えば、現時点の `index.astro`　は以下の通り。

```astro
<BaseLayout pageTitle={pageTitle}>
    <h2>ここは、私のAstroサイトのホームページです。</h2>
    <Greeting client:load messages={["どうも", "こんにちは", "ようこそ"]} />
</BaseLayout>
```
`client:load` という記載がHydrated Componentであることを示している。

