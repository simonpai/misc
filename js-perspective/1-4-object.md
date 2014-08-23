##物件 (Object)

* Property 名字可以使用關鍵字

```js
// 空物件
var obj = {};
var obj = new Object();

// Property
obj.name = "Mike";
obj["name"] = "Mike";
console.log(obj.name); // Mike
console.log(obj.["name"]); // Mike

// 中括號裡可以是任何表達式
var propertyName = "name";
console.log(obj[propertyName]); // Mike
console.log(obj["na" + "me"]); // Mike

// 無點直接使用點號旳狀況
obj["old-name"] = "Moo";
obj["old name"] = "Moo";
obj[1] = "Moo" ;

// delete

// for .. in
// Object.keys(o)
// TODO

// object literal
// TODO
```

###`this`

###建構子 (Constructor)

###型別、Prototype 與繼承

###參考資料

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Predefined_Core_Objects
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_Revisited
