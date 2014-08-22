##函數 (Function)

```js
function squareSum(x, y) {
	return x * x + y * y;
}
var z = squareSum(x, y);

// 函數內再呼叫別的函數
function square(x) {
	return x * x;
}
function squareSum(x, y) {
	return square(x) + square(y);
}
var z = squareSum(x, y);
```

###函數宣告

* 函數的宣告方式有兩種。

```js
// 標準的函數宣告句型，注意結尾沒有逗號
function render(x, y) {
  // ...
}

// 這其實是一個 assignment，把右邊的函數表達式賦值給左邊的變數
var render = function (x, y) {
  // ...
};

// 函數表達式也會被用在賦值以外的地方，例如被當作參數傳入別的函數
function execute(f) {
	f();
}
execute(function () {
	console.log("Executed me!");
});

// 或者 IIFE
(function (x) {
  // ...
})(x);
```

###參數 (Parameter)

* 函數宣告的時候可以定義零到任意多個參數。
* 多傳入的參數沒有差別，少傳入的參數視為 `undefined`。
* 參數可以是任何類別，包括函數本身。
* 使用 `arguments` 可以找到所有傳入的參數，適用於不定數量參數的情況。

```js
function render(x, y) {
	console.log(y);
}
render(1, 2); // 印出 2
render(1, 2, 3); // 還是印出 2
render(1); // 印出 undefined

// 參數也可以是函數
function callThreeTimes(data, f) {
	f(data);
	f(data);
	f(data);
}
function f1(x) {
	alert(x);
}
callThreeTimes("Hello!", f1);
// 或者直接傳入一個函數表達式
callThreeTimes("Hello!", function (x) {
	alert(x);
});
// alert 也是一個函數
callThreeTimes("Hello!", alert);

// TODO: arguments
```

###回傳值

```js
// TODO
```

###呼叫 (Call)

* 使用一個函數的行為稱為呼叫。

```js
function render(x, y) {
	// ...
}
render(0, 1);

// TODO: return value
```

###Scope

```js
// TODO
```

###邪惡的 Eval



###參考資料

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions
