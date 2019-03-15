<template>
  <div id="app">
    <div style="float: right;">
      <a href="https://github.com/YitzhakAndrade/vue-tinymce" target="_blank">
        <img
          width="149"
          height="149"
          src="https://github.blog/wp-content/uploads/2008/12/forkme_right_red_aa0000.png?resize=149%2C149"
          alt="Fork me on GitHub"
        >
      </a>
    </div>
    <div>
      <section class="s1-U__width--900px s1-U__pd16" style="margin: 0 auto;">
        <div>
          <div class="s1-U__mg--bt32">
            <div class="md-display-1 s1-U__text-color--dark-2 s1-U__align-children--center">
              <div>
                <h1 class="md-display-1 s1-U__text-color--dark-2 s1-U__align-children--center">
                  <span>Vue TinyMCE</span>
                </h1>
              </div>
            </div>
          </div>
          <md-card>
            <md-content class="md-scrollbar s1-U__pd0 s1-U__pd16" style="overflow: auto;">
              <h3
                class="md-title s1-U__text-color--primary s1-U__fw--300 s1-U__mg--bt16"
              >Enter your text</h3>

              <tinymce id="d1" v-model="content"></tinymce>

              <br>
              <h3>HTML Output:</h3>
              <p style="font-family: monospace; min-height: 200px; margin-top: 12px;">{{ content }}</p>

              <br>
              <br>
              <br>
              <div v-html="content"></div>
            </md-content>
          </md-card>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import tinymce from "vue-tinymce-editor";

export default {
  name: "App",
  components: {
    tinymce
  },
  data: () => ({
    content: ""
  }),
  methods: {}
};
</script>

