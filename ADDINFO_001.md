# [追加情報] Swift Playgroundsになでしこ３の文法エラーを表示する方法
1. index.htmlファイルの65行目を下記のとおりに変更する。
```
65行目  c.display = "block"  →  c.style.display = "block"
```

**下記は「コンソール表示」命令を使用する場合の変更点(文法エラーも表示される)**

2. index.htmlファイルの38行目に以下のscriptタグを追加することにより表示されます。
```
<script src="https://iwb.jp/s/js/tiny-console.js"></script>
```
- 黄色文字が見えにくいので、tiny-console.jsをダウンロードして黄色文字を赤色などに変更することをお勧めします。

## 参考文献

- [ipadでjavascriptのconsoleを見たいよう（涙） #JavaScript - Qiita](https://qiita.com/KabosuTravel/items/3848d8ea7033bcb9df6e)

- [tiny-console.js](https://gist.github.com/developit/60b810cbcb55e1da198a634218adcc90#file-tiny-console-js)