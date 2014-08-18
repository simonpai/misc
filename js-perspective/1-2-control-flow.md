##流程控制 (control flow)

* JS 中的流程控制都是句型，沒有表達式。

###If / Else

* `if` 括號內是一個表達式。
* 表達式的布林判定為 `true` 則執行後面的內容，否則去下一個 `else if` 判斷，或執行 `else` 後面的內容。
* 會被判定成 `false` 的有 `false`、`undefined`、`null`、`0`、`NaN`、以及空字串。
* 其他都算 `true`。

```js
// 基本型態
if (exp) {
	// ...
}

// 可以搭配 else
if (exp) {
	// ...
} else {
	// ...
}

// 可以用 else if 連續判定
if (exp) {
	// ...
} else if (exp2) {
	// ...
} else if (exp3) {
	// ...
} else {
	// ...
}

// 也可以只有 if 與 else if
if (exp) {
	// ...
} else if (exp2) {
	// ...
}

// 單行時可以省略括號
if (exp)
	console.log("abc");
else
	console.log("def");
```

###Switch / Case

* 類似連續的 `if` 與 `else if`。
* `switch` 括號後面是個表達式。
* 表達式算出來的值，拿去依序和每個 `case` 比對，相同的話，就執行後面的內容，直到 `break` (或 `return`) 或 `switch` 結束為止。
* 如果都沒有中任何 `case`，執行 `default` 後面的內容 (如果有的話)。

```js
switch (exp) {
	case 1: // 如果 exp == 1 => 印出 1
		console.log("1");
		break;
	case 2: // 如果 exp == 2 => 印出 2, 3 兩行
		console.log("2");
	case 3: // 如果 exp == 3 => 印出 3
		console.log("3");
		break;
	default: // 如果都不是 => 印出 other
		console.log("other");
}
```

###While 迴圈

```js
var i = 0;
while (i < 10) {
	console.log(i);
	i++;
}
```

// break, continue

###For 迴圈

* `break` 與 `continue` 也適用。

```js
for (var i = 0; i < 10; i++) {
	console.log(i);
}
```

### Do 迴圈

* 很少見。
* 因為判定在第一次執行後面，比較少有這種需要。
* 並且條定式寫在尾巴，對人類讀起來比較不友善。
* `break` 與 `continue` 也適用。

```js
var i = 0;
do {
	console.log(i);
	i++;
} while (i < 10)
```

###標籤 (Label)

* 用來標示一個 statement，通常是 `switch` 或迴圈。
* `break` 或 `continue` 搭配 label，可以跳脫或繼續指定的 `switch` 或迴圈。
* 所以通常是用在多層 `switch` 與迴圈的狀況。

```js
var chars = ['a', 'a', 'b', 'a', 'b'];

muhaha:
for (var i = 0; i < 5; i++) {
	switch (chars[i]) {
		case "a":
			console.log("a");
			break;
		case "b":
			console.log("b");
			break muhaha;
	}
}
```

###Block

* Block 就是用 `{` 與 `}` 包起來，裡面放了很多 statements 的單位。
* 大括號裡面如果放的不是 statements，不算 block。 (例如：物件表達式、switch)
* 文法上來說，整個 Block 可以視為一個 statement。

```js
if (x) { // 這個是 block
	console.log("1");
	console.log("2");
	console.log("3");
}

var obj = { // 這個不是
	x: 1,
	y: 2
};

switch (c) { // 這個也不是
	case "A":
		console.log("Hi, A");
		break;
	case "B":
		console.log("Hi, B");
		break;
}
```

* 實際上，`if` 的文法定義是

```js
if (expression)
	statement
```

* 大括號的情況，其實是利用 block 包成一個 statement。
* `else`、`else if`、`for`、`while`、`do` 也是相同的原理。

###參考資料

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Statements
