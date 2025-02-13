---
id: 5cdafbc32913098997531680
title: أكمل كائن Promise باستخدام resolve و reject
challengeType: 1
forumTopicId: 301196
dashedName: complete-a-promise-with-resolve-and-reject
---

# --description--

يكون للوعد (promise) ثلاث حالات: `pending`, و `fulfilled`, و `rejected`. كائن Promise الذي قمت بإنشائه في التحدي السابق معلق إلى الأبد في حالة `pending` لأنك لم تضف طريقة لإكمال كائن Promise. حجج `resolve` و `reject` المعطاة لوظفية الكائن promise تستخدم لفعل ذلك. تستخدم `resolve` عندما تريد أن ينجح الكائن promise وتستخدم `reject` عندما تريد أن يفشل الكائن promise. هذا الطرق تستقبل حَجَّة (argument)، كما هو مبين بالإدانة.

```js
const myPromise = new Promise((resolve, reject) => {
  if(condition here) {
    resolve("Promise was fulfilled");
  } else {
    reject("Promise was rejected");
  }
});
```

المثال الوارد أعلاه يستخدم strings نصية كوسيطة لهذه الحَجَّة (argument)، ولكن يمكن أن يكون أي شيء حقا. في كثير من الأحيان، قد يكون كائناً، يمكنك استخدام البيانات منه، لوضع البيانات على موقعك أو في أي مكان آخر.

# --instructions--

اجعل كائن promise يتعامل مع النجاح والفشل. إذا كان `responseFromServer` صحيحاً `true`، فاستدعي طريقة `resolve` لإكمال كائن promisie بنجاح. مرر `resolve` إلى سلسلة (string) نصية بقيمة `We got the data`. إذا كان `responseFromServer` بـ `false`، استخدم دالة `reject` كبديل و مرر اليها الـ string الآتي: `Data not received`.

# --hints--

`resolve` يجب أن تُستدعى مع الـ string المتوقع عندما يكون شرط `if` صحيح، اي `true`.

```js
assert(
  code.match(/if\s*\(\s*responseFromServer\s*\)\s*{\s*resolve\s*\(\s*('|"|`)We got the data\1\s*\)(\s*|\s*;\s*)}/g)
);
```

`reject` يجب أن تُستدعى مع الـ string المتوقع عندما يكون شرط `if` خاطئ، اي `false`.

```js
assert(
  code.match(/}\s*else\s*{\s*reject\s*\(\s*('|"|`)Data not received\1\s*\)(\s*|\s*;\s*)}/g)
);
```

# --seed--

## --seed-contents--

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer represents a response from a server
  let responseFromServer;

  if(responseFromServer) {
    // Change this line
  } else {  
    // Change this line
  }
});
```

# --solutions--

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer represents a response from a server
  let responseFromServer;

  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});
```
