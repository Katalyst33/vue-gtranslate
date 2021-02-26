/* eslint-disable */
<template>
  <div>


      <div class="grid md:grid-cols-2 lg:grid-cols-3  p-4 shadow m-4 rounded-lg">
        <div v-for="item in country"  class="py-2" :key="item.id">

          <a @click="doTranslation(item.code)" :title="item.title"
             href="#">
                    <span class="language-item">
                        <img :alt="item.alt" :src="`https://cdn.jsdelivr.net/npm/vue-gtranslate/img/flags/__${item.title}.png`"
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
  name:"TranslateComponent",
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


      ],


    }
  },



  methods: {




    doTranslation(code) {

     window.doGTranslate(code)


      setTimeout( ()=>{
        this.window.location.reload()
      },2000 )

      return false
    },


  }
}
</script>

<style scoped>


a:link {
  text-decoration: none;
  font-size: large;
  cursor: pointer;
}
a:hover{
  text-decoration: underline;
}

.language-item {
  display: flex;

}

.language__text {
  color: black;

  margin-top: 7px;
  padding-left: 5px;
  text-decoration: none;
}


.flag {
  height: 40px;

}

h3 {
  cursor: pointer;
}

/*//columns*/
/* Container for flexboxes */
.row {
  display: flex;
  flex-wrap: wrap;
}

/* Create four equal columns */
.column {
  flex: 20%;
  padding: 10px;
}

/* On screens that are 992px wide or less, go from four columns to two columns */
@media screen and (max-width: 992px) {
  .column {
    flex: 25%;
  }
}

/* On screens that are 600px wide or less, make the columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .row {
    flex-direction: column;
  }
}

</style>
