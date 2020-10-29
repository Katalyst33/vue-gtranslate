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
                        <a :title="item.title"
                           href="#">
                    <span class="language-item">
                        <img :alt="item.alt" :src="`https://cdn.jsdelivr.net/npm/vue-gtranslate/img/flags/_${item.title}.png`"
                             class="flag"/>
              <!--            <img :alt="item.alt" :src="`img/flags/_${item.title}.png`"
                               class="flag"/>-->
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
          code: 'en|af',
          title: 'Afrikaans',
        },
        {
          code: 'en|sq',
          title: 'Albanian',
        },
        {
          code: 'en|ar',
          title: 'Arabic',
        },
        {
          code: 'en|hy',
          title: 'Armenian',
        },
        {
          code: 'en|az',
          title: 'Azerbaijani',
        },
        {
          code: 'en|eu',
          title: 'Basque',
        },
        {
          code: 'en|be',
          title: 'Belarusian',
        },
        {
          code: 'en|bg',
          title: 'Bulgarian',
        },
        {
          code: 'en|ca',
          title: 'Catalan',
        },
        {
          code: 'en|zh-CN',
          title: 'Chinese (Simplified)',
        },
        {
          code: 'en|zh-TW',
          title: 'Chinese (Traditional)',
        },
        {
          code: 'en|hr',
          title: 'Croatian',
        },
        {
          code: 'en|cs',
          title: 'Czech',
        },

        {
          code: 'en|da',
          title: 'Danish',
        },
        {
          code: 'en|nl',
          title: 'Dutch',
        },
        {
          code: 'en|en',
          title: 'English',
        },
        {
          code: 'en|et',
          title: 'Estonian',
        },
        {
          code: 'en|tl',
          title: 'Filipino',

        },
        {
          code: 'en|fi',
          title: 'Finnish',

        },
        {
          code: 'en|fr',
          title: 'French',
        },

        {
          code: 'en|de',
          title: 'German',

        },
        {
          code: 'en|el',
          title: 'Greek',

        },
        {
          code: 'en|hu',
          title: 'Hungarian',

        },
        {
          code: 'en|id',
          title: 'Indonesian',

        },
        {
          code: 'en|ga',
          title: 'Irish',

        },
        {
          code: 'en|it',
          title: 'Italian',

        },
        {
          code: 'en|ja',
          title: 'Japanese',

        },
        {
          code: 'en|ko',
          title: 'Korean',

        },
        {
          code: 'en|lt',
          title: 'Lithuanian',

        },
        {
          code: 'en|ms',
          title: 'Malay',

        },
        {
          code: 'en|no',
          title: 'Norwegian',

        },
        {
          code: 'en|pl',
          title: 'Polish',

        },

        {
          code: 'en|pt',
          title: 'Portuguese',

        },
        {
          code: '"en|ro',
          title: 'Romanian',

        },
        {
          code: 'en|ru',
          title: 'Russian',

        },
        {
          code: 'en|es',
          title: 'Spanish',

        },
        {
          code: 'en|sv',
          title: 'Swedish',

        },
        {
          code: 'en|th',
          title: 'Thai',

        },
        {
          code: 'en|tr',
          title: 'Turkish',
        },
        {
          code: 'en|uk',
          title: 'Ukrainian',

        },
        {
          code: '',
          title: '',
        },


      ],


    }
  },

  mounted() {
    console.log("update images")
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
