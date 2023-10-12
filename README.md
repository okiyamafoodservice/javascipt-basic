# 2023年「JavaScript課題」
## 授業内コード
### 授業


1. 10月5日（木曜日）はじめの一歩
2. 10月5日（木曜日）GitHubリポジトリ作成

## 10月12日
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
