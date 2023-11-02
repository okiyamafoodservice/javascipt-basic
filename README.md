# 2023 年「JavaScript 課題」

## 授業内コード

### 授業

1. 10 月 5 日（木曜日）はじめの一歩
2. 10 月 5 日（木曜日）GitHub リポジトリ作成
3. 10 月 12 日 (木曜日)　代入と複合演算子
4. 10 月 19 日(木曜日)配列と for 文
5. 10 月 26 日（木曜日）ID 取得と要素の追加 Event の追加

## 11/2

- classList

```js
btnRed.addEventListener("click", () => {
  jsText.classList.toggle("redText");
  btnRed.textContent = "もとにもどす";
  jsText.classList.remove("bigText");
});

btnBig.addEventListener("click", () => {
  jsText.classList.toggle("bigText");
  btnBig.textContent = "もとにもどす";
  jsText.classList.remove("redText");
});

// if文で切り替える

btnRed.addEventListener("click", () => {
  if (btnRed.textContent === "赤くなる") {
    jsText.classList.toggle("redText");
    btnRed.textContent = "もとに戻る";
  } else {
    jsText.classList.remove("redText");
    btnRed.textContent = "赤くなる";
  }
});
```

- 課題

```js
// setAttribute
dancingBtn.addEventListener("click", function () {
  dancer.setAttribute("class", "dance");
});
// removeAttribute
stopBtn.addEventListener("click", function () {
  dancer.removeAttribute("class");
});
// 画像の差し替え
changeBtn.addEventListener("click", function () {
  dancer.setAttribute("src", "./images/ballet_woman.png");
});
```

## 10 月 26 日

- ID 取得

```js
// toparisというID名（getElementByIDのID取得なので#は必要ない)
const id_element = document.getElementById("toparis");
console.dir(id_element.children[3]);
// liという要素を取得(getElementByTagName)
const tag_element = document.getElementsByTagName("li");
console.log(tag_element);
// pool_bというクラス名を取得　HTML collection
const class_name = document.getElementsByClassName("pool_b");
console.log(class_name);
```

- innerHTML を用いた要素の追加

```js
// 挿入したい要素の親となる要素
const sweetpotatos = document.querySelector(".imo");
// 複合代入演算子を用いることで.innerHTMLで要素内に追加できる
sweetpotatos.innerHTML += "<li>べにはるか</li>";
// さらにテンプレートリテラルを用いることで、複数の要素を挿入できる
sweetpotatos.innerHTML += `<li>べにはるか</li><li>シルクスイート</li>`;

appendChildを用いると;
//   定数名.appendChild(挿入する定数);
const shibacard = document.querySelector(".card1");
shibacard.appendChild(pochi);

const hachikocard = document.querySelector(".card2");
hachikocard.appendChild(hachiko);
```

-event の発生

```js
// 赤色
const redBtn = document.querySelector(".red");

// 文字を取得する
const text = document.querySelector(".text");
console.dir(text);
const textSpan = document.querySelector(".text span");

// redBtnにクリックイベントを設定する
redBtn.addEventListener("click", function () {
  // ディレクトリ内のstyleの中のcolorを変更することで,textの色が変更される
  text.style.color = "#ff0000";
  // fontsizeの変更
  text.style.fontSize = "60px";
  // textSpan内のtextを変更
  textSpan.innerText = "赤";
});

//  属性の変更
redder.addEventListener("click", function () {
  // 変更する定数名.setAttribute（"属性","再設定するクラス名")
  text.setAttribute("class", "redText");
});
```

## 10 月 19 日

- 配列と for 文

```js
// 配列
// リストにメロンを加えたい
// ul要素を取り入れる
const element = document.querySelector("ul");
console.log(element);

// selectorはcssのセレクターなので
const element2 = document.querySelector("#fruitslist");
console.log(element2);

const element3 = document.querySelector(".listbox__list");
console.log(element3);

// 新しい要素を作る
const lilast = document.createElement("li");
console.dir(lilast);

lilast.textContent = "メロン";
console.log(lilast);

// リストの最後に追加する。<li>メロン</li>を変数elementないの<ul></ul>に追加する

element.appendChild(lilast);

// いちごを追加したい

const lilast2 = document.createElement("li");
lilast2.textContent = "いちご";
element.appendChild(lilast2);

// for文
// 基本系
for (let i = 0; i < 4; i++) {
  // 繰り返しの処理
  // ０〜3を表示したい
  console.log(i);
}
// 7の段
for (let i = 0; i < 9; i++) {
  console.log((i + 1) * 7);
}

for (let i = 0; i < 9; i++) {
  console.log("7" + "×" + (i + 1) + "=" + (i + 1) * 7);
}

// テンプレートリテラル
for (let i = 0; i < 9; i++) {
  console.log(`7×${i + 1}=${7 * (i + 1)}`);
}

for文を用いてリストを追加;
// ul class =boxFooterLink
const element = document.querySelector(".boxFooterLink");
// menusという配列を設定
const menus = ["カリキュラム", "就職実績"];
// menusの配列数内でループ
for (let i = 0; i < menus.length; i++) {
  // elementlistという名前のliを作成
  const elementlist = document.createElement("li");
  //elementlitsをmenuという配列に設定
  elementlist.textContent = menus[i];
  //     element(boxFooterLink)内の子要素にelementlistを追加
  element.appendChild(elementlist);
}
```

## 10 月 12 日

- リテラルと演算子

### 文字列の計算

```js
// 文字列リテラル=文字列型
console.log("トライデント");
// 数値型リテラル＝数値型
console.log(567);
console.log("123");

// 改行する
console.log("トライデント\nWebデザイン学科");

// テンプレートリテラルの改行＝文字列型
console.log(`トライデント
        Webデザイン学科`);

// 文字列の連結
// 文字列+文字列
console.log("abc" + "def");

// 文字列+数字
console.log("円周率は" + 3.14 + "です");

// 文字列+数値の計算 最初に文字列が含まれた時点で文字列となる
console.log("計算結果:" + 123 + 456);

// 先に計算をする
console.log(123 + 456 + "となりました");

// 文字列+(数値の計算(足し算）))
console.log("計算結果:" + (123 + 456));

// 文字列-数値 減法であれば数値型に変換して計算される
console.log("2" - 1);

console.log("2" * 3);

console.log("2" / 2);

console.log("5-1" - 1);

//
```

### 複合演算子

```js
// 変数の宣言・代入
// 変数の宣言
let a;
// 値の代入(数値型となる)
a = 10;
console.log(a);
// 最代入　文字列型
a = "Hello";

console.log(a);
// 変数の宣言と代入を同時に行なっています。さらに再宣言なのでエラーとなります。
// let a = "world";

// 定数の宣言
const PI = 3.14;
console.log(PI);

// 再代入
// PI = 3.1414926455;
// 再宣言
// const PI = z;

// 複合演算子
let n = 5;
n = n + 2;
console.log(n);

// 足し算
let n2 = 5;
n2 += 2;
console.log(n2);

// 掛け算
n2 *= 3;
console.log(n2);

// あまりを計算
let n4 = 5;
n4 %= 2;
console.log(n4);

// インクリメント　n+1
let n3 = 5;
n3++;
console.log(n3);
```

### document オブジェクト

document.querySelector()　()内の要素を取得する<br>
document.createElement() ()内の要素を作成する

```js
// リストにメロンを加えたい
// ul要素を取り入れる
const element = document.querySelector("ul");
console.log(element);

// selectorはcssのセレクターなので
const element2 = document.querySelector("#fruitslist");
console.log(element2);

const element3 = document.querySelector(".listbox__list");
console.log(element3);

// 新しい要素を作る
const lilast = document.createElement("ul");
console.dir(lilast);

lilast.textContent = "メロン";
console.log(lilast);
```

## 10 月 5 日

- インターネットの基本について理解する。
- Web の基本的な仕組みを理解する。
- Web サーバーの役割について理解する。
- 開発環境の構築
- JavaScript を書く場所

### JavaScript を書く場所

1. HTML ファイルの中
1. 外部 JS ファイルの中
1. ブラウザのコンソール

基本は、外部 JS ファイルを読み込むが、HTML 内に各場合は、`</body>`の上に書く。

```html
<!doctype html>
<html lang=ja>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>演習</title>
</head>
<body>
</script>
</body>
</html>
```

### フロントエンドロードマップ

フロントエンドエンジニアに必要なスキルの[ロードマップ](https://roadmap.sh/frontend)がある。
