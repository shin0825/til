# Node.js

### 初期設定

```
const express = require('express');
const app = express();
```

### ルーティング

```
app.get('/', (req, res) => {
  res.send('Hello Node.js!'); // 文字のみ表示
});

app.get('/top', (req, res) => {
  res.render('top.ejs'); // ファイルの内容を表示する
});
```

### 起動処理

```
app.listen(3000, () => {
    console.log("My app listening on port 3000!");
});
```

- 第一パラメータにアプリケーションのポートを指定する
- 第２パラメータの関数はなくても良い
