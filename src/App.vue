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

              <tinymce
                id="d1"
                v-model="content"
                :toolbar1="toolbar"
                :plugins="plugins"
                :other_options="options"
              ></tinymce>

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
    content:
      '<h2>Titulo&nbsp;</h2> <p>Textinho</p> <p>&nbsp;</p> <h3>SubTitulo</h3> <p>Aqui tem um texto corrido, como paragrafo normal mesmo.</p> <table style="border-collapse: collapse; width: 100%;" border="1"> <tbody> <tr> <td style="width: 25%;">1</td> <td style="width: 25%;">2</td> <td style="width: 25%;">3</td> <td style="width: 25%;">4</td> </tr> <tr> <td style="width: 25%;">5</td> <td style="width: 25%;">6</td> <td style="width: 25%;">7</td> <td style="width: 25%;">8</td> </tr> <tr> <td style="width: 25%;">9</td> <td style="width: 25%;">10</td> <td style="width: 25%;">11</td> <td style="width: 25%;">12</td> </tr> </tbody> </table> <p>&nbsp;</p> <p>Loren ipsum cabuloso</p> <p>&nbsp;</p> <p>Minhas listinha:</p> <ol> <li>item 1</li> <li>item 2</li> <li>item 3 <ol> <li>item 3.1</li> <li>item 3.2 <ol> <li>item 3.2.1</li> </ol> </li> <li>item 3.3</li> </ol> </li> <li>item 4</li> </ol> <p>Lista nao numerada:</p> <ul> <li>item <ul> <li>item</li> </ul> </li> <li>item</li> </ul>',
    plugins: ["lists preview hr searchreplace table hr wordcount"],
    toolbar:
      "formatselect | bold italic underline strikethrough superscript subscript | numlist bullist | table hr | removeformat",
    options: {
      branding: false,
      menu: {},
      ...{
        table_advtab: false,
        table_cell_advtab: false,
        table_row_advtab: false,
        table_resize_bars: false,
        table_appearance_options: false
        // table_default_styles: { "border-collapse": "collapse", width: "100%" }
        // table_default_attributes: {}
      },
      language_url:
        "https://dyonir.github.io/vue-tinymce-editor/static/langs/pt_BR.js",
      formats: {
        underline: { inline: "u" },
        strikethrough: { inline: "s" }
      }
    }
  }),
  methods: {}
};
</script>

