---
title: "2023-02-28 argocd image updater・かつや"
date: 2023-03-01T03:12:40+09:00
draft: false
---

とりあえず何書けばいいかわからんから適当に。

## argocd image updaterと格闘
昨日この[diary.homi.run](https://diary.homi.run)をkubernetesに載せてhugoのimage buildまでは自動化していたが、このままだと記事更新のたびに`k rollout restart deployment/diary`みたいなことをしなければならず、めちゃシンドイのでargocd image updaterを自宅のクラスタにも導入したりしていた。

細かい話はblog.の方に書くが、image updaterの2023-03-01時点のstableであるv0.12.0において、ghcr.ioのイメージを使おうとすると以下のようなエラーが帰ってくる。

```bash
ERRO[0001] Error fetching metadata for homirun/diary:latest - neither V1 or V2 or OCI manifest returned by registry: manifest unknown: OCI index found, but Accept header does not support OCI indexes  application=test image_alias= image_name=ghcr.io/homirun/diary registry_url=ghcr.io
```

これについては[issueが立っていて](https://github.com/argoproj-labs/argocd-image-updater/issues/522)、v0.12.2にすれば動くみたいなことが書いてあった。

## かつやのカツ丼・松
昼に近所のかつやに行ってカツ丼・松を注文したら米が以前の2/3以下になっていてすごい顔をしてしまった。
店員さんがデブの健康を気を使ってくれたのかもしれないので、ごめんなさいという気持ちに今はなっている。

