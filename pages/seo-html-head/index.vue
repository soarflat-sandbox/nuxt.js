<template>
  <div class="container">
    <h1>Home page 🚀</h1>
    <nuxt-link to="/seo-html-head/about">About page</nuxt-link>
  </div>
</template>

<script>
  export default {
    head: {
      title: 'Home page 🚀',
      meta: [
        {
          // 子コンポーネント利用されたときにメタ情報が重複してしまうことを避けるためにhidキーでユニーク識別子を付与する。
          hid: 'description',
          name: 'description',
          content: 'Home page description'
        }
      ],
      noscript: [
        {
          innerHTML: 'Body No Scripts',
          body: true
        }
      ],
      script: [
        { src: '/seo-html-head/head.js' },
        // body: trueを指定するとスクリプトをbodyタグの最後に移動できる
        { src: '/seo-html-head/body.js', body: true },
        // defer: ''を指定しているためdefer=""が描画される
        { src: '/seo-html-head/defer.js', defer: '' },
      ]
    }
  }
</script>

<style>
  .container {
    text-align: center;
    margin-top: 150px;
    font-size: 20px;
  }
</style>