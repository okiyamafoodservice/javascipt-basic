# 2023 年「JavaScript 課題」

## 授業内コード

### 授業

1. 10 月 5 日（木曜日）はじめの一歩
2. 10 月 5 日（木曜日）GitHub リポジトリ作成
3. 10 月 12 日 (木曜日)　代入と複合演算子
4. 10 月 19 日(木曜日)配列と for 文
5. 10 月 26 日（木曜日）ID 取得と要素の追加 Event の追加
6. 11 月 09 日（木曜日）if 文
7. 11 月 16 日（木曜日）演算子
8. 12 月 07 日(木曜日)戻り値
9. 12 月 14 日(木曜日)callback 関数

10. 1 月 18 日(木曜日) for in 文　 for of 文　 object
11. 1 月 25 日(木曜日) json/date

## 1/25

```js
//json
//JavaScript Object Notation
JavaScriptをもとにつくられたデータフォーマット;
// 日時取得
const now = new Date();
console.log(now);

const day = ["日", "月", "火", "水", "木", "金", "土"];
console.log(now.getDay());

console.log(day[now.getDay()]);

const promotionDay = new Date("2024-2-8");
console.log(promotionDay - now);
const difference = promotionDay - now;

const seconds = difference / 1000;
console.log(seconds);

const minutes = seconds / 60;
console.log(minutes);

const hours = minutes / 60;
console.log(hours);

const days = hours / 24;
console.log(days);
```

## 1/18

```js

  const animals = ["dog", "cat", "bird"]; animals[2] = "lion";
  console.log(animals); // tigerを追加する
  animals.push("tiger");
  console.log(animals[4]); // animalsの最初にelephantを追加する
  animals.unshift("elephant"); console.log(animals); const fruits =
  // document.querySelectorAll("li");
  // console.log(fruits);
  //  fruit.push("
  // <li>いちご</li>");
  //nodelistと配列は似ているが別物なのでpushは使えない。appendchildやcreateElementなどを使うしかない



      const countries = {
        Japan: "日本",
        USA: "アメリカ",
        China: "中国",
        Korea: "韓国",
      };

      console.log("countries.USA");

      console.log(countries["USA"]);

      //   for...in 文

      for (let country in countries) {
        console.log(country + ": " + countries[country]);
      }

      //受験者名簿(オブジェクトの配列)
      const meibo_obj = [
        { id: "20224", name: "新井太郎" },
        { id: "20031", name: "井上次郎" },
        { id: "20193", name: "山本花子" },
      ];

      //   オブジェクトが３つ入っているオブジェクト
      // 配列の要素が全て欲しい場合、
      for (let i = 0; i < meibo_obj.length; i++) {
        console.log(meibo_obj[i]);
        for (let key in meibo_obj[i]) {
          console.log(meibo_obj[i][key]);
        }
      }

      let npbCentral_list = [
        { team: "東京ヤクルトスワローズ", home: "東京" },
        { team: "阪神タイガース", home: "大阪" },
        { team: "読売ジャイアンツ", home: "東京" },
        { team: "広島東洋カープ", home: "広島" },
        { team: "中日ドラゴンズ", home: "名古屋" },
        { team: "横浜DeNAベイスターズ", home: "横浜" },
      ];


homeの場所を取得する
      for (let i = 0; i < npbCentral_list.length; i++) {
        console.log(npbCentral_list[i]);
        for (let key in npbCentral_list[i]) {
          console.log(npbCentral_list[i]["home"]);
        }
      }


 const table = document.querySelector(".table_nam");

      const numbers = [
        ["0", "ZERO"],
        ["1", "ONE"],
        ["2", "TWO"],
        ["3", "THREE"],
        ["4", "FOUR"],
        ["5", "FIVE"],
      ];

      for (let tb of numbers) {
        const tr = document.createElement("tr");

        for (let tb_d of tb) {
          const td = document.createElement("td");
          td.textContent = tb_d;
          tr.appendChild(td);
        }

        table.appendChild(tr);
      }


```

## 12/14

```js
const animalsRun = function (list) {
  for (let i = 0; i < list.length; i++) {
    list[i].classList.add("run");
    list[i].style.transitionDuration = animalSpeed[i] + "s";
  }

  // 以下をfor文に変えると上になる
  // const dog = document.querySelector(".dog span");
  // dog.style.transitionDuration = animalSpeed[0] + "s";
  // dog.classList.add("run");

  // const cat = document.querySelector(".cat span");
  // cat.style.transitionDuration = animalSpeed[1] + "s";
  // cat.classList.add("run");

  // const horse = document.querySelector(".horse span");
  // horse.style.transitionDuration = animalSpeed[2] + "s";
  // horse.classList.add("run");

  // const pig = document.querySelector(".pig span");
  // pig.style.transitionDuration = animalSpeed[3] + "s";
  // pig.classList.add("run");

  // const gorilla = document.querySelector(".gorilla span");
  // gorilla.style.transitionDuration = animalSpeed[4] + "s";
  // gorilla.classList.add("run");
};

startBtn.addEventListener("click", function () {
  animalsRun(animals);
});

-callback関数;

// 関数1
const concatenateSpace = function (lastName, firstName) {
  return lastName + " " + firstName;
};
// 関数2
const useConcatenate = function (name, func) {
  let concatName = func(name[0], name[1]);
  console.log("結合結果：" + concatName);
};

//   関数2の実行(引数1 = 配列,引数2 =　関数名)

let nameParam = ["okiyama", "naoto"];
useConcatenate(nameParam, concatenateSpace);

// 関数式1
//   funcには関数式２が入っている
const testFunc = function (func) {
  console.log("testFuncが実行されました");
  // 2秒後に動く
  setTimeout(function () {
    func();
  }, 2000);
};

//   関数式2
const callback = function () {
  console.log("callbackが実行されました");
};
// 関数式1を実行している
//   callbackは関数式２の関数名
testFunc(callback);

-アロー関数;

// 従来の関数式

const dog = function () {
  return "わんわん";
};

//   関数の定義
function dog2() {
  return "バウワウ";
}

//   関数dogを実行している
console.log(dog());
console.log(dog2());

const cat = () => {
  return "ニャーニャー";
};
console.log(cat());

//   鳴き方を決めたい　アロー関数＋引数
const animal = (voice) => {
  return voice;
};

console.log(animal("ミャーミャー"));

// thisは予約語で使えないので、thisElmにする
const thisElm = document.querySelector("p");
console.log(thisElm);

//   thisElm.addEventListener("click", function () {
//     console.log(this.textContent);
//   });

// アロー関数を使ってthisを使用する時はtargetを使う
thisElm.addEventListener("click", (e) => {
  // console.log("クリック");
  // console.log(this.textContent);
  console.log(e.target.innerText);
});
```

## 12/07

```js
// 引数1と引数2を足す関数の定義（引数1=a 引数2=b)
const addition = function (a, b) {
  const c = a + b;
  console.log(c);
};

//   関数の実行
addition(30, "6");
//   consoleに306が表示される

//   戻り値のある関数の定義

const addition2 = function (a, b) {
  const c = a * b;
  return c;
  // 戻り値
};

//   関数の実行
const result = addition2(5, 5);
console.log(result);

const cake = 450;

const takeOut = document.querySelector(".takeOut");

const eatin = document.querySelector(".eatIn");

const result = document.querySelector(".taxIn");

const calculation = function (cake, tax) {
  const price = cake * tax;
  return price;
};

takeOut.addEventListener("click", function () {
  const totalprice = calculation(cake, 1.08);
  result.innerHTML = Math.round(totalprice);
});

eatin.addEventListener("click", function () {
  const totalprice = calculation(cake, 1.1);
  result.innerHTML = Math.round(totalprice);
});

// グローバル変数の初期化※再代入可能にするためletを使う。
let global = "グローバル変数";

// 関数funcの定義
const func = function () {
  //ローカル変数の初期化
  let local = "ローカル変数";
  //グローバル変数の表示
  console.log(global);
  //ローカル変数の表示
  console.log(local);
  global = "グローバル変数を再代入";

  // var global = "グローバル変数を再定義"; //varはこれができる。
  // console.log(global);
};

if (global) {
  var local2 = "varは関数スコープ";
  let local3 = "letはブロックスコープ";
}

//関数funcの呼び出し
func();
//グローバルはvar global = "グローバル変数を再定義";で再定義されているので、undefinedになる。

//グローバル変数の表示
console.log(global);
//ローカル変数の表示は、関数funcの中で定義されているので、呼び出せない。
//console.log(local);
//varは関数スコープなので、if文の外で呼び出せる。
console.log(local2);
//letはブロックスコープなので、if文の外で呼び出せない。
console.log(local3);
```

## 11/16

```js
const word = ["Java", "JavaScript", "Ruby", "Go", "PHP"];

const resultArea = document.querySelector(".result");

const resultBtn = document.querySelector("button");

resultBtn.addEventListener("click", function () {
  const num = Math.round(Math.random() * 4);

  if (num === 1) {
    resultArea.textContent = word[num];
  } else {
    resultArea.textContent = "違う言語です";
  }
});

let n1 = 1;
let n2 = 2;

// 論理和　AまたはBがtrueの場合
if (n1 === 1 || n2 === 1) {
  console.log(true);
} else {
  console.log(false);
}

// 論理積　AかつBがtureの場合

if (n1 === 1 && n2 === 2) {
  console.log(true);
} else {
  console.log(false);
}

if (n1 === 1 && n2 === 1) {
  console.log(true);
} else {
  console.log(false);
}
```

## 11/9

```js
          const widthsize = window.innerWidth; //現在のブラウザの横幅
          console.log(widthsize);
          //以下から記述していきます。
          const clickArea = document.querySelector(".clickArea");

          const leftZone = document.querySelector(".leftZone");
          const rightZone = document.querySelector(".rightZone");

          document.body.addEventListener("click", function (event) {
            console.log(event.clientX);

            if (event.clientX >= widthsize / 2) {
              const list = document.createElement("li");
              list.textContent = "右";
              rightZone.appendChild(list);
            } else {
              const list = document.createElement("li");
              list.textContent = "左";
              leftZone.appendChild(list);
            }
          });

          <!--
    document.body.insertAdjacentHTML("beforeEnd", "<p>numは100未満</p>");

    beforebegin … 指定した要素のタグの上に挿入
afterbegin … 指定した要素のタグの中の初めに挿入
beforeend … 指定した要素のタグの中の最後に挿入
afterend … 指定した要素のタグの下に挿入 -->



```

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
