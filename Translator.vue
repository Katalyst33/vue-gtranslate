/* eslint-disable */
<template>
  <div>
    <div class="">
      <div v-for="item in country" class="py-2" :key="item.id">

        <a @click="doTranslation(item.code)" :title="item.title"
           href="#">
                    <span class="language-item">
                        <img :alt="item.alt"
                             :src="`https://cdn.jsdelivr.net/npm/vue-gtranslate/img/flags/__${item.title}.png`"
                             class="flag"/>

                      <span class="language__text">{{ item.title }}</span>
                    </span>
        </a>

      </div>
    </div>

    <div id="google_translate_element2"></div>

  </div>
</template>

<script>

export default {
  name: "TranslateComponent",
  data() {
    return {
      modal: {
        'is-active': false,
      },
      country: [
        {
          code: "af",
          title: "Afrikaans"
        },
        {
          code: "sq",
          title: "Albanian"
        },
        {
          code: "ar",
          title: "Arabic"
        },
        {
          code: "hy",
          title: "Armenian"
        },
        {
          code: "az",
          title: "Azerbaijani"
        },
        {
          code: "eu",
          title: "Basque"
        },
        {
          code: "be",
          title: "Belarusian"
        },
        {
          code: "bg",
          title: "Bulgarian"
        },
        {
          code: "ca",
          title: "Catalan"
        },
        {
          code: "zh-CN",
          title: "Chinese (Simplified)"
        },
        {
          code: "zh-TW",
          title: "Chinese (Traditional)"
        },
        {
          code: "hr",
          title: "Croatian"
        },
        {
          code: "cs",
          title: "Czech"
        },

        {
          code: "da",
          title: "Danish"
        },
        {
          code: "nl",
          title: "Dutch"
        },
        {
          code: "en",
          title: "English"
        },
        {
          code: "et",
          title: "Estonian"
        },
        {
          code: "tl",
          title: "Filipino"
        },
        {
          code: "fi",
          title: "Finnish"
        },
        {
          code: "fr",
          title: "French"
        },

        {
          code: "de",
          title: "German"
        },
        {
          code: "el",
          title: "Greek"
        },
        {
          code: "hu",
          title: "Hungarian"
        },
        {
          code: "id",
          title: "Indonesian"
        },
        {
          code: "ga",
          title: "Irish"
        },
        {
          code: "it",
          title: "Italian"
        },
        {
          code: "ja",
          title: "Japanese"
        },
        {
          code: "ko",
          title: "Korean"
        },
        {
          code: "lt",
          title: "Lithuanian"
        },
        {
          code: "ms",
          title: "Malay"
        },
        {
          code: "no",
          title: "Norwegian"
        },
        {
          code: "pl",
          title: "Polish"
        },
        {
          code: "pt",
          title: "Portuguese"
        },
        {
          code: '"ro',
          title: "Romanian"
        },
        {
          code: "ru",
          title: "Russian"
        },
        {
          code: "es",
          title: "Spanish"
        },
        {
          code: "sv",
          title: "Swedish"
        },
        {
          code: "th",
          title: "Thai"
        },
        {
          code: "tr",
          title: "Turkish"
        },
        {
          code: "uk",
          title: "Ukrainian"
        }
      ]
    }
  },

  computed: {
    currentRouteName() {
      if (this.$route.path === "/") {
        return `${this.$route.path}`;
      } else {
        return `${this.$route.path}/`;
      }
    }
  },




  methods: {

    doTranslation(code) {
      // localStorage.setItem("lang", code);

      // const lang = localStorage.getItem("lang");

      this.$router
          .replace(`${this.currentRouteName}#googtrans(${code})`)

          .catch(err => {
            return err;
          });

      // this.$router.replace();
      window.location.reload();

      setTimeout(() => {
        // window.location.reload();
      }, 500);

      return false;
    }


  }
}
</script>

<style scoped>


a:link {
  text-decoration: none;
  font-size: large;
  cursor: pointer;
}

a:hover {
  text-decoration: underline;
}

.language-item {
  display: flex;
  align-items: center;

}


.flag {
  height: 40px;
}

h3 {
  cursor: pointer;
}




</style>
