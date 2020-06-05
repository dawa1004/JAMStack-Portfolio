<template>
  <div class="font-main flex flex-wrap justify-around">
    <header class="md:w-64 w-full h-64 px-2">
      <div class="md:w-64 w-full md:mt-24 mt-12 relative md:fixed">
        <div class="flex">
          <div class="bg-center bg-cover w-16 h-16 mr-2 rounded-full shadow photo"></div>
          <div>
            <h1 class="font-bold">Ryo's works</h1>
            <p class="text-xs text-justify">作品置き場です。<br>
            Worksアイコンで一覧ページを表示します。
            トップからは各記事のタイトルをクリックで詳細ページに飛びます。<br>
            カテゴリータグソート可能。</p>
          </div>
        </div>
        <div class="flex justify-around mt-5 text-xs">
          <nuxt-link to="/">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faCode" />
              </fa-layers>
              Works
            </button>
          </nuxt-link>
          <a href="https://twitter.com/DawaProgramming" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faTwitter" />
              </fa-layers>
              Twitter
            </button>
          </a>
          <a href="https://github.com/dawa1004" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faGithub" />
              </fa-layers>
              GitHub
            </button>
          </a>
        </div>
        <input type="text" placeholder="Keywords" class="bg-gray-300 p-2 text-xs rounded w-full mt-5 focus:outline-none" v-model="keyword" @keypress.enter="$router.push('/search/'+keyword)">
      </div>
    </header>
    <main class="w-full mt-10 p-2">
      <nuxt />
    </main>
  </div>
</template>

<script>
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import { faGithub } from '@fortawesome/free-brands-svg-icons'
import { faCode } from '@fortawesome/free-solid-svg-icons'
export default {
  data() {
    return {
      keyword: ''
    }
  },
  computed: {
    faTwitter () {
      return faTwitter
    },
    faGithub () {
      return faGithub
    },
    faCode () {
      return faCode
    }
  }
}
</script>

<style>
main {
  max-width: 550px;
}
.photo {
  min-width: 4rem; 
  min-height: 4rem;
  background-image: url('~assets/icon.jpeg');
}
button:focus {
  outline: none;
}
</style>
