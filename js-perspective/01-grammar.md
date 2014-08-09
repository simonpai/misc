###文法

* 和人類語言一樣，JS 的構成元素大致分成：字詞、片語、句子。
* 整篇 JS 程式就是由很多句子組成。
* 一個句子由樹狀結構 (parse/syntax tree) 的片語及字詞們組成。



###字詞類

變數名稱 (identifier)
* 自己定義的變數名稱。
* 可以由數字、英文字母、底線構成。
* 但第一個字元不可以是數字。

```js
var x = 1; // x 就是變數名稱

function f(x, y) { // f, x, y 是變數名稱
}
```

Literal (不會翻)
* 表達固定真假值、數字、字串的單位。
* `true`, `false`, `0`, `1`, `"hello"`...
* `null`
* array literal
* object literal

```js
var x = 1; // 1 就是 numeric literal
var y = "muhaha"; // "muhaha" 是 string literal
var a = [0, 1, 2]; // array literal
var b = { name: "Bob", age: 14 }; // object literal
```

關鍵字 (keyword)
* 在 JS 裡有特殊的意義，不可以拿來當變數名稱。
* 最常見的有 `var`, `this`, `if`, `for`, `function`, `return`, `new` 等等。
* [列表](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords)
* 有些字在現在的 JS 版本裡沒有用到，但是怕以後會用，所以先保留起來，稱為保留字 (reserved word)。

運算子 (operator)
* `+`, `-`, `*`, `/`, `&&`, `||`...
* `++`, `--`
* `=` (assignment)
* `?` 與 `:` (conditional)

###片語類

表達式 (expression)
* 由字詞類與更小的表達式組成。
* 與人類語言中片語 (phrase) 的概念一樣。
* 知道如何拆解片語的樹狀結構就能讀懂整個句子。

```js
var y = 10;
var x = 2 * (y + 5); // y + 5, (y + 5), 2 * (y + 5) 都是表達式
```

###句子類

陳述式 (statement) (什麼怪中文名字)
* 一個 statement 就如同一個 JS 的句子。
* 一般在書寫的時候會以分號 `;` 結尾，除非是 function/if/for 等。
* 其實分號在 JS 並不是必要的，但不寫的話人類反而自己看不太懂。

Block
* 被大刮號包起來、裡面放一堆 statement。
* 不包含 object literal 的情況。

```js
function f(x) {
	var y = 2 * x
	return y + 3;
}
// 這四行本身就是一個 statement (對外面來說)
// 但是 block 裡面的兩行也各自是一個 statement (對 function 裡面來說)
```

```js
if (x > 10) {
	var y = x * 2;
	console.log(y);
} else {
	console.log("x is too small.");
}
// if/else 也是同樣的方式
```

###註解

註解 (comment)
* 每行 `//` 之後的內容 VM 君會忽略，可以偷罵他；稱為 line comment。
* 夾在 `/*` 與 `*/` 之間的內容也是，稱為 block comment。
* 註解寫是給人類讀的。
* 但除此之外註解的功能常被拿來暫時性地略過一段程式碼。



###VM 君的行為模式
* 當被要求執行一段 JS 的時候，從第一個 statement 開始執行到最後一個。
* 對每個 statement 拆解成語法樹，按照順序運算。
* VM Queue (稍後再講)


