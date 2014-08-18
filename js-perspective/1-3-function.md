##函數 (Function)

```js
function squareSum(x, y) {
	return x * x + y * y;
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

* 函數宣告的時候可以定義零到任意多個參數

```js
// TODO
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

###`arguments`

###邪惡的 Eval



###參考資料

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions
