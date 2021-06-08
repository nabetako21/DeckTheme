# DeckTheme
[MarinDeck](https://hisubway.online/marindeck/)に提供しているTweetDeck用カスタムCSSです。<br>
自分がTweetDeck用に使っているCSSも公開します。StylusやBTDなどのカスタムCSSで使えます。<br>

### MarinDeckとは
PC向け公式Twitterクライアントである**TweetDeck**を、スマホで使いやすいようにレイアウトの最適化を行ったアプリです。中身はWebのTweetDeckなので**JSとCSSで見た目を好き勝手いじれます**。

## Stripe
ツイートの背景色がストライプなテーマです。<br>
[詳細](https://github.com/nabetako21/DeckTheme/blob/main/Stripe/Stripe.md)

## Viper
緑をアクセントカラーとする毒蛇なテーマです。<br>
[詳細](https://github.com/nabetako21/DeckTheme/blob/main/Viper/Viper.md)

## 拡張CSS
カスタムCSSの欄に追記すると楽しい(?)設定（Stripe, Viper共通）<br>

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

* **ツイートアクションボタンを消す**<br>
リプライ・リツイート・いいねのボタンらを消して情報量の増加と誤爆防止。<br>
```CSS
html .tweet-actions {
  display:none !important;
}
/* アイコン分の高さを維持する（Stripe, Viperには記述済み） */
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
