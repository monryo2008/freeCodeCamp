---
id: 587d7fb1367417b2b2512bf2
title: 使用 .env 文件
challengeType: 2
forumTopicId: 301521
dashedName: use-the--env-file
---

# --description--

`.env` 文件是一个用于将环境变量传给应用程序的隐藏文件， 这是一个除了开发者之外没人可以访问的私密文件，它可以用来存储你想保密或者隐藏的数据， 例如，它可以存储第三方服务的 API 密钥或者数据库 URI， 也可以使用它来存储配置选项， 通过设置配置选项，你可以改变应用程序的行为，而无需重写一些代码。

在应用程序中可以通过 `process.env.VAR_NAME` 访问到环境变量。 `process.env` 对象是 Node 程序中的一个全局对象，可以给这个变量传字符串。 习惯上，变量名全部大写，单词之间用下划线分隔。 `.env` 是一个 shell 文件，因此不需要用给变量名和值加引号。 还有一点需要注意，当你给变量赋值时等号两侧不能有空格，例如：`VAR_NAME=value`。 通常来讲，每一个变量定义会独占一行。

# --instructions--

添加一个环境变量作为配置选项。

Create a `.env` file in the root of your project directory, and store the variable `MESSAGE_STYLE=uppercase` in it. Then, in the GET `/json` route handler that you created in the last challenge, transform the response object’s message to uppercase if `process.env.MESSAGE_STYLE` equals `uppercase`. 即响应对象应该是 `{"message": "HELLO JSON"}`。

# --hints--

端口 `/json` 响应的值，应该随着环境变量 `MESSAGE_STYLE` 的变化而改变

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/use-env-vars').then(
    (data) => {
      assert.isTrue(
        data.passed,
        'The response of "/json" does not change according to MESSAGE_STYLE'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

# --solutions--

```js
/**
  Backend challenges don't need solutions, 
  because they would need to be tested against a full working project. 
  Please check our contributing guidelines to learn more.
*/
```
