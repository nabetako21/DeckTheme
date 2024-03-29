# DeckTheme
[MarinDeck](https://hisubway.online/marindeck/)に提供しているTweetDeck用カスタムCSSです。<br>
自分がTweetDeck用に使っているCSSも公開します。StylusやBTDなどのカスタムCSSで使えます。<br>

### MarinDeckとは
PC向け公式Twitterクライアントである**TweetDeck**を、スマホで使いやすいようにレイアウトの最適化を行ったアプリです。中身はWebのTweetDeckなので**JSとCSSで見た目を好き勝手いじれます**。

## Viper
緑をアクセントカラーとする毒蛇なテーマです。<br>
[詳細](https://github.com/nabetako21/DeckTheme/blob/main/Viper/Viper.md)

## Stripe
ツイートの背景色がストライプなテーマです。<br>
[詳細](https://github.com/nabetako21/DeckTheme/blob/main/Stripe/Stripe.md)

## Metro
ツイートの位置を少し変えたりしたシンプルオシャレ?なテーマです。<br>
[詳細](https://github.com/nabetako21/DeckTheme/blob/main/Metro/Metro.md)

## 拡張CSS（Viper, Stripe, Metro用）
カスタムCSSの欄に追記すると楽しい(?)設定<br>

* **背景の変更**
```CSS
html .js-app-columns-container {
  background: hoge;
  /* background-image: url(hoge.png); */
  /* background-color: green !important; */
}
html.dark .js-app-columns-container {
  background: hogeDark;
  /* background-image: url(hogeDark.jpg); */
  /* background-color: red !important; */
}
```
```CSS
/* 背景をぼかす */
:root { --blur: 5px }
```

## 拡張CSS（他でも使える）
その他自分がMarinDeck用に使っているカスタムCSS<br>

* **ツイートアクションボタンを消す**<br>
リプライ・リツイート・いいねのボタンらを消して情報量の増加と誤爆防止。<br>
```CSS
html .tweet-actions {
  display:none !important;
}
/* アイコン分の高さを維持する（Viper, Stripe, Metroには記述済み） */
html .tweet-body {
 min-height: 20px;
}
```

* **右上にいいねボタン**<br>
基本的にツイートアクションボタンを隠し、対象ツイートに触れたときだけいいねボタンがやってくる。<br>
```CSS
html .tweet-action:not([rel=favorite]) {
  display: none !important;
}
html .like-count {
  display: none;
}
html .stream-item:hover .tweet-footer {
  opacity: 0.5;
  position: absolute;
  transform: translate(17px, 0);
  transition: 0.4s;
}
html .tweet-footer {
  opacity: 0;
  top: 0;
  right: 0;
  position: absolute;
  transform: translate(45px, 0);
  transition: 0.4s;
}
```

* **TLの画像の高さを半分にする**<br>
全体は自分で開いて確認するからTLを圧迫してほしくないというとき向け。<br>
```CSS
html .media-preview:not(.detail-preview), html .media-preview:not(.detail-preview) > .media-preview-container {
  height: calc(153px / 2) !important;
  min-height: 0 !important;
}
html .media-sensitive {
  font-size: smaller !important;
}
```
