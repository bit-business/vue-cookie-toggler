<script>
import Vue from 'vue';
import VueCookieToggler from '@/vue-cookie-toggler.vue';

export default Vue.extend({
  name: 'ServeDev',

  components: {
    VueCookieToggler,
  },

  computed: {
    cookiesGroups() {
      return [
        {
          category: 'essential',
          name: 'Essential website cookies',
          description:
              'Morbi in sem quis dui placerat ornare. Pellentesque odio nisi, euismod in, pharetra a, ultricies in, diam. Sed arcu. Cras consequat.',
          active: true,
          required: true,
        },
        {
          category: 'analytics',
          services: [{
            name: 'Google Tag Manager',
            description:
                'Morbi in sem quis dui placerat ornare. Pellentesque odio nisi, euismod in, pharetra a, ultricies in, diam. Sed arcu. Cras consequat.',
            active: false,
          }, {
            name: 'Google Analytics',
            description:
                'Morbi in sem quis dui placerat ornare. Pellentesque odio nisi, euismod in, pharetra a, ultricies in, diam. Sed arcu. Cras consequat.',
            active: false,
          }],
          name: 'Analytics and customization',
          description:
              'Donec nec justo eget felis facilisis fermentum. Aliquam porttitor mauris sit amet orci. Aenean dignissim pellentesque felis.',
          active: false,
        },
        {
          category: 'social_networking',
          services: ['Facebook'],
          name: 'Social networking',
          description:
              'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Donec odio. Quisque volutpat mattis eros. Nullam malesuada erat ut turpis. Suspendisse urna nibh, viverra non, semper suscipit, posuere a, pede.',
          active: false,
        },
      ]
    }
  }
});
</script>

<template>
  <div id="app">
    <vue-cookie-toggler
        :cookies-groups="cookiesGroups"
        title="Cookie policy title"
        settings-title="Cookie settings title"
        settings-label="Settings button label"
        accept-label="Accept button label"
        save-label="Save button label"
        cancel-label="Cancel button label"
    >
      Cookie policy message

      <template #settingsContent>
        Cookie settings message
      </template>

      <template #mainButtons="{ accept, settings }">
        <button
            class="vct__btn vct__btn--default"
            @click="settings"
        >
          Customize settings
        </button>
        <button
            class="vct__btn vct__btn--primary"
            @click="accept"
        >
          Accept all cookies
        </button>
      </template>

      <template #settingsButtons="{ accept, save }">
        <button
            class="vct__btn vct__btn--default"
            @click="accept"
        >
          Accept all cookies
        </button>
        <button
            class="vct__btn vct__btn--primary"
            @click="save"
        >
          Save settings
        </button>
      </template>
    </vue-cookie-toggler>

    <div class="flex justify-center align-center">
      <button data-cookie-toggler="settings">
        Open cookies settings
      </button>

      <!-- Global site tag (gtag.js) - Google Analytics -->
      <script type="text/plain"
              data-cookie
              data-category="analytics"
              data-name="Google Analytics"
              async
              src="https://www.googletagmanager.com/gtag/js?id=UA-184982471-1"
      >
      </script>
      <script type="text/plain"
              data-cookie
              data-category="analytics"
              data-name="Google Analytics"
      >
  window.dataLayer = window.dataLayer || [];

  function gtag() {
    dataLayer.push(arguments);
  }

  gtag('js', new Date());

  gtag('config', 'UA-184982471-1');



      </script>
      <!-- End Global site tag (gtag.js) - Google Analytics -->


      <!-- Google Tag Manager -->
      <script type="text/plain"
              data-cookie
              data-category="analytics"
              data-name="Google Tag Manager"
      >
  (function (w, d, s, l, i) {
    w[l] = w[l] || [];
    w[l].push({
      'gtm.start':
        new Date().getTime(),
      event: 'gtm.js'
    });
    var f = d.getElementsByTagName(s)[0],
      j = d.createElement(s),
      dl = l != 'dataLayer' ? '&l=' + l : '';
    j.async = true;
    j.src =
      'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
    f.parentNode.insertBefore(j, f);
  })(window, document, 'script', 'dataLayer', 'GTM-TZR2Z6L');


      </script>
      <!-- End Google Tag Manager -->


      <iframe
          data-cookie
          data-category="analytics"
          data-placeholder="true"
          alt="Please accept the cookie policy to see the content"
          data-src="https://www.youtube.com/embed/azUbCdcAeFM"
      />
    </div>
  </div>
</template>

<style scoped>
.flex {
  display: flex;
  flex-direction: column;
}

.justify-center {
  justify-content: center;
}

.align-center {
  align-items: center;
}
</style>
