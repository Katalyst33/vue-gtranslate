<template>
  <div>


    <div class="">
      <h3 class="is-size-5" @click="toggleModal">
        Select a language </h3>
    </div>

    <div :class="modal" class="modal">
      <div class="modal-background" @click="toggleModal"></div>
      <div class="modal-content">

        <div id="google_translate_element"></div>
        <div>
          <section class="section has-background-dark">


            <div>
              <div class="columns">
                <div class="column">
                  <template v-for="item in country">
                    <div :key="item.id">
                      <div class="my-3" @click="doTranslation(item.code)">
                        <a :title="item.alt"
                           href="#">
                    <span class="language-item">
                        <img :alt="item.alt" :src="`https://cdn.jsdelivr.net/npm/vue-gtranslate/${item.img}`"
                             class="flag"/>
                      <span class="is-size-6 pl-3">{{ item.title }}</span>
                    </span>
                        </a>
                      </div>
                    </div>
                  </template>
                </div>


              </div>
            </div>
          </section>

          <div id="google_translate_element2"></div>

        </div>
      </div>
      <button class="modal-close is-large" @click="toggleModal">
        <i class="fas fa-times is-size-3 has-text-white"></i>
      </button>
    </div>


  </div>
</template>

<script>
import "./translator.css"

export default {
  data() {
    return {
      modal: {
        'is-active': false,
      },
      country: [
        {
          code: 'en|zh-CN',
          title: 'Chinese',
          img: 'img/flags/china.png',
          alt: 'Chinese'
        },
        {
          code: 'en|zh-TW',
          title: 'Chinese (Simplified)',
          img: 'img/flags/china-traditional.png',
          alt: 'Chinese-traditional'
        },
        {
          code: 'en|da',
          title: 'Danish',
          img: 'img/flags/denmark.png',
          alt: 'denmark'
        },
        {
          code: 'en|en',
          title: 'English',
          img: 'img/flags/united-kingdom.png',
          alt: 'English'
        },
      ],


    }
  },

  mounted() {
    console.log("flag location")
  },

  methods: {

    toggleModal() {
      this.modal["is-active"] = !this.modal["is-active"]
    },

    sayHi(data) {
      alert(`Hey bro ${data}`)

    },
    doTranslation(code) {
      window.doGTranslate(code)
      this.toggleModal();
      return false
    },


  }
}
</script>

<style scoped>

.lang__link {
  margin: 10px 0;
}


.language-item {
  display: flex;
  color: white;
}


.flag {
  height: 24px;
  width: 24px;
}

h3 {
  cursor: pointer;
}
</style>
