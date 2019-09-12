---
title: "React Day 1"
date: 2019-09-12T14:43:09+07:00
draft: false
tag: ["js"]
---
Hari ini saya memulai *challenge* iseng-iseng untuk belajar sekaligus melatih koding saya, dan selama 30 hari kedepan saya akan menuliskan perkembangan saya belajar **ReactJS**.

## Apa Itu React?

![React logo](https://reactjs.org/logo-og.png)

[React](facebook.github.io/react/) adalah sebuah **library** JavaScript yang bersifat *open source* untuk membuat tampilan front end yang dibuat oleh Facebook. Front end adalah sebuah interface UI atau tampilan pada sebuah web atau aplikasi, dan React diciptakan dengan tujuan untuk membangun aplikasi dalam skala besar dengan data yang terus berubah dari waktu ke waktu.

Pada dasarnya aplikasi React adalah sebuah komponen, dan komponen itu bisa saja terdiri dari sekumpulan komponen lainnya. Di dalam satu komponen berisi sebuah fungsi atau method untuk menghasilkan *output*.

Contohnya kita membuat sebuah *form*. Dalam sebuah *form* terdapat beberapa lement interface seperti *input*, *label*, dan *button*. Setiap element itu ditulis menggunakan React komponen.

## Bagaimana Menggunakan React?
Seperti yang saya katakan bahwa React adalah sebuah *library* JavaScript, maka untuk menggunakannya kita menggunakan JavaScript dan HTML.

Contohnya untuk menuliskan **Hello World!**

```html
<html>
<head>
    <title> Hello World</title>

    <!-- React dalam bentuk CDN -->
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div id="app"></div>
    <script type="text/babel">
    ReactDOM.render(
        <h1>Hello World</h1>,
        document.querySelector('#app')
    );
    </script>
</body>
</html>
```

Jika dilihat memang sangat aneh, dimana tag HTML ditulis di dalam JavaScript. Ini di karenakan React menggunakan JSX. JSX atau *extended JavaScript* adalah sebuah pengembangan JavaScript dimana kode HTML bisa diikut sertakan dalam JavaScript.

## Peraturan JSX
Penulisan JSX memang terlihat aneh tetapi sebenarnnya tidak sulit kalau kita mengetahui dasar-dasar HTML. Seperti pada sintaks lainnya yang memiliki aturan, JSX juga memiliki aturan agar nyaman ditulis dan *compiler* tidak *error*.
### Kode HTML harus nested
Artinya kode HTML harus memiliki awalan dan akhiran yang jelas agar tidak *error* saat dijalankan.
contoh
```js
class HelloWorld extends React.Component {
   render() {
      return (
         <div>
            <h1>Hello World!r</h1>
         </div>
      );
   }
}
```
### Kurung kurawal untuk penulisan javascrpit
Pada penulisan tag JavaScript boleh menggunakan tag {} seperti menuliskan *comment*

```js
class HelloWorld extends React.Component {
   render() {
      return (
         <div>
            <h1>Hello World</h1>
            {//Ini komentar untuk satu baris...}
            {/*
            Ini komentar
            unutk multiline
            ..
            */}
         </div>
      );
   }
}
```

### Self closing tag
Element HTML yang paling sering di jumpai menggunakan dua tag, yaitu tag pembuka (`<div>`) dan tag penutup (`</div>`). Namun pada beberapa element seperti `<img>` dan `<input>`, tag seperti ini hanya menggunakan satu tag, tidak ada tag penutup atau biasa yang di sebut self-closing tag.

Walaupun dalam HTML kita tidak di wajib kan menutup tag seperti ini, ketika kita menuliskan tag HTML self-closing tag dalam JSX, tag wajib di beri tanda slash di penghujung tag.
contohnya tag (`<br>`) dibawah ini

```js
class HelloWorld extends React.Component {
   render() {
      return (
         <div>
            <h1>Hello World!r</h1>
            <br /> 
         </div>
      );
   }
}
```

### CSS styling
 Untuk penulisan CSS sendiri menggunakan aturan camelcase misalnya **borderRadius**, **backgroundImage**, dan yang lainnya yang lebih dari satu kata

 ```js
 class App extends React.Component {
   render() {

      var myStyle = {
         fontSize: 100,
         color: '#FF0000'
      }

      return (
         <div>
            <h1 style={myStyle}>Header</h1>
         </div>
      );
   }
}
```

Itu adalah sebagian dari pengenalan React dan JSX di hari pertama.
