### 変数と宣言
- const
→再代入できない変数（定数とは限らない）
- let
→変数、初期値を指定しない変数も定義できる（undefinedになる）
- var
→letと似ているが、定数も再代入できてしまう

### データ型とリテラル
- テンプレートリテラル
「``」
いろいろ加工できる文字列

### 演算子
- NaN(Not-a-Number)は数値でないNumber型を表す
Number.isNaNで判定できる
- 分割代入
→詳しく下記
- Nullish coalescing演算子（??）
左辺がnullishかどうかで値を決める
その値があるか分からないときに使う
```javascript
console.log(undefined ?? "右辺の値"); // => "右辺の値"
```

### 暗黙的な型変換
- Symbol(" ")は暗黙的に型変換できない
明示的でしか変換できないようにしたいときに使う？

### 関数と宣言
- デフォルト引数
??でも代用可能
```javascript
function echo(x = "デフォルト値") {
    return x;
}

console.log(echo(1)); // => 1
console.log(echo()); // => "デフォルト値"
```

- Rest parameters
仮引数の先頭に「...」をつけた仮引数
配列として代入される
他の引数と組み合わせるときは末尾に
「...array」を引数に渡すと関数内に展開できる
```javascript
function fn(arg1, ...restArgs) {
    console.log(arg1); // => "a"
    console.log(restArgs); // => ["b", "c"]
}
fn("a", "b", "c");
```
- spread構文
配列の前に...をつけた構文

- Arrow Function
```javascript
// Arrow Functionを使った関数定義
const 関数名 = () => {
    // 関数を呼び出したときの処理
    // ...
    return 関数の返す値;
};
```

- メソッドの短縮記法
```javascript
const obj = {
    method() {
        return "this is method";
    }
};
console.log(obj.method()); // => "this is method"
```

### ループと反復処理
- someメソッド
配列の各要素をテストする関数を受け取る
```javascript
function isEven(num) {
    return num % 2 === 0;
}
const numbers = [1, 5, 10, 15, 20];
console.log(numbers.some(isEven)); // => true
```

- filterメソッド
配列の特定の値で新しい配列を作成
```javascript
function isEven(num) {
    return num % 2 === 0;
}

const array = [1, 5, 10, 15, 20];
console.log(array.filter(isEven)); // => [10, 20]
```

### オブジェクト
- プロパティ名と値が同じ場合の省略記法
{name}のようになっているもの
- オブジェクトのアクセス方法
ドット記法（.）とブラケット記法（['']）がある
プロパティ名に変数を指定したい場合などはブラケット記法を使う
- オブジェクトの分割代入
モジュールのimportとかに出てきた
```javascript
const languages = {
    ja: "日本語",
    en: "英語"
};
const { ja, en } = languages;
console.log(ja); // => "日本語"
console.log(en); // => "英語"
```
- Optional chaining演算子(?.)
左辺がnullish(null か undefined)ならundefinedを返す
```javascript
const obj = {
    a: {
        b: "objのaプロパティのbプロパティ"
    }
};
// obj.a.b は存在するので、その評価結果を返す
console.log(obj?.a?.b); // => "objのaプロパティのbプロパティ"
// 存在しないプロパティのネストも`undefined`を返す
// ドット記法の場合は例外が発生してしまう
console.log(obj?.notFound?.notFound); // => undefined
// undefinedやnullはnullishなので、`undefined`を返す
console.log(undefined?.notFound?.notFound); // => undefined
console.log(null?.notFound?.notFound); // => undefined
```
- 静的メソッド＋配列のforEachなどを組み合わせるとプロパティに反復処理できる
```javascript
const obj = {
    "one": 1,
    "two": 2,
    "three": 3
};
const keys = Object.keys(obj);
keys.forEach(key => {
    console.log(key);
});
// 次の値が順番に出力される
// "one"
// "two"
// "three"
```
- オブジェクトにspread構文（...）をプロパティ名に指定できる

### 配列
- Array.prototype.at
array.at(-1)で最後の値を指定できる

- Spread構文で配列の任意の場所に配列を展開できる
- メソッドチェーンと高階関数
記述を簡潔にできる

### 文字列
- 正規表現、URL、パスなど特徴的な分野が含まれる

### 文字列とUnicode
- Code Unitや絵文字を扱う場合について書かれている

### 関数とthis
- 様々な関数の書き方が載っている
- メソッドにthisを使う
- call、apply、bind

### クラス
？？