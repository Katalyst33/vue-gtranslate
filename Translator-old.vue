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
                  <div class="lang__box my-3" onclick="doGTranslate('en|zh-CN');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="Chinese" class="flag"
                             src="/img/flags/china.png"/>
                      <span class="is-size-6 pl-3">Chinese (Simplified)</span>
                    </span>
                    </a>
                  </div>
                  <div class="my-3"  onclick="doGTranslate('en|zh-TW');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="Chinese(Traditional)" class="flag"
                             src="/img/flags/china-traditional.png"/>
                      <span class="is-size-6 pl-3">Chinese(Traditional)</span>
                    </span>
                    </a>
                  </div>
                  <div class="my-3" onclick="doGTranslate('en|da');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/denmark.png"/>
                      <span class="is-size-6 pl-3">Danish</span>
                    </span>
                    </a>
                  </div>
                </div>
                <div class="column">
                  <div class="lang__box my-3" onclick="doGTranslate('en|en');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/netherlands.png"/>
                      <span class="has-text-white is-size-6 pl-3">Dutch</span>
                    </span>
                    </a>
                  </div>
                  <div class="lang__box my-3" onclick="doGTranslate('en|en');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/united-kingdom.png"/>
                      <span class="has-text-white is-size-6 pl-3">English</span>
                    </span>
                    </a>
                  </div>
                  <div class="lang__box my-3" onclick="doGTranslate('en|fi');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/finland.png"/>
                      <span class="has-text-white is-size-6 pl-3">Finnish</span>
                    </span>
                    </a>
                  </div>
                </div>
                <div class="column">

                  <div class="my-3" onclick="doGTranslate('en|fr');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/france.png"/>
                      <span class="has-text-white is-size-6 pl-3">French</span>
                    </span>
                    </a>
                  </div>
                  <div class="my-3" onclick="doGTranslate('en|de');return false;">
                    <a href="#"
                       title="English">
                    <span class="language-item">
                        <img alt="English" class="flag"
                             src="/img/flags/germany.png"/>
                      <span class="has-text-white is-size-6 pl-3">German</span>
                    </span>
                    </a>
                  </div>
                  <div class="my-3" onclick="doGTranslate('en|el');return false;">
                    <a href="#" title="English">
                    <span class="language-item">
                        <img alt="Greek" class="flag"
                             src="/img/flags/greece.png"/>
                      <span class="has-text-white is-size-6 pl-3">Greek</span>
                    </span>
                    </a>
                  </div>


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

      options: [
        {
          value: '',
          title: 'Select Language',
          icon: '',
        },
        {
          value: 'en|af',
          title: 'Afrikaans',
          icon: '🇿🇦',
        },
        {
          value: 'en|sq',
          title: 'Albanian',
          icon: '🇦🇱',
        },
        {
          value: 'en|en',
          title: 'English',
          icon: '🇬🇧',
        },
        /*   {
          value:'',
          title:'',
          icon:'',
        },*/


      ]
    }
  },

  mounted() {
    console.log("flag location")
  },

  methods: {

    toggleModal() {
      this.modal["is-active"] = !this.modal["is-active"]
    }


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
