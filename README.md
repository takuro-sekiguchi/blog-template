# ブログ風Webサイトの模写コーディング

[デモサイトはこちら](https://taku-web3.com/project/blog-template/index.html)

## 改めて学んだこと
- wrapperを使って、各要素のmax-widthを決める
- 記事にはarticleタグを使う
- 疑似要素の使い方
- mainとasideの使い分け
- sectionタグの使い所
- メディアクエリとflexの相性


```css
.wrapper {
  max-width: 1300px;
  margin: 0 auto;
  padding: 0 16px;
}
```
横幅の最大値を決めておいて、各要素のつけていく。
一部分だけを横幅いっぱいに広げたいときは、.wrapperをつけずにwidth:100%;にする。

```css
header {
  width: 100%;
  position: fixed;
  z-index: 100;
  background-color: white;
}
```
ヘッダーを固定する場合は、background-colorを指定しないと透明になる。

```css
.new-article {
  display: flex;
  justify-content: space-around;
  padding-top: 150px;
  margin-bottom: 70px;
  text-align: center;
}

@media screen and (max-width: 786px) {
  .new-article {
    flex-direction: column; 
  }
}
```
flex-directionを変えるだけで、簡単にレスポンシブ対応のサイトが作れる。

```css
article a::after {
  content: "";
  background-color: black;
  display: block;
  height: 1px;
  width: 80px;
  margin: 0 auto;
}
```
aタグに疑似要素で下線をつける方法

```css
.container {
  display: flex;
  justify-content: space-between;
}

main {
  flex: 0.66;
}
aside {
  flex: 0.33;
}
```
flexを使って2カラムに分割する方法
