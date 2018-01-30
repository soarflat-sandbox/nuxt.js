<template>
  <div>
    <p>Hi from {{ name }}</p>
    <nuxt-link to="/hello-world/">Home page</nuxt-link>
  </div>
</template>

<script>
  export default {
    // asyncDataはページコンポーネントがロードされる前に毎回呼び出されるメソッド
    // サーバーサイドレンダリングや、ユーザーがページ遷移する前にも呼び出される
    // このメソッドは第一引数としてcontext（https://ja.nuxtjs.org/api/context）を受取り
    // contextを利用し、データを取得してコンポーネントのデータを返す
    asyncData() {
      return {
        name: process.static ? 'static' : (process.server ? 'server' : 'client')
      }
    },
    head: {
      title: 'About page'
    }
  }
</script>