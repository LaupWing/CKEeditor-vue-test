<template>
   <div id="app">
      <ckeditor
         :editor="editor"
         v-model="editorData"
         :config="editorConfig"
      ></ckeditor>
   </div>
</template>

<script>
// ⚠️ NOTE: We don't use @ckeditor/ckeditor5-build-classic any more!
// Since we're building CKEditor from source, we use the source version of ClassicEditor.
import ClassicEditor from "@ckeditor/ckeditor5-editor-classic/src/classiceditor";

import EssentialsPlugin from "@ckeditor/ckeditor5-essentials/src/essentials";
import BoldPlugin from "@ckeditor/ckeditor5-basic-styles/src/bold";
import ItalicPlugin from "@ckeditor/ckeditor5-basic-styles/src/italic";
import LinkPlugin from "@ckeditor/ckeditor5-link/src/link";
import ParagraphPlugin from "@ckeditor/ckeditor5-paragraph/src/paragraph";
import Pagination from "@ckeditor/ckeditor5-pagination/src/pagination";
import ExportPdf from "@ckeditor/ckeditor5-export-pdf/src/exportpdf";

export default {
   name: "app",
   data() {
      return {
         editor: ClassicEditor,
         editorData: "<p>Content of the editor.</p>",
         editorConfig: {
            plugins: [
               EssentialsPlugin,
               BoldPlugin,
               ItalicPlugin,
               LinkPlugin,
               ParagraphPlugin,
               ParagraphPlugin,
               ExportPdf,
            ],
            licenseKey:
               "1K0EdkwkDYQmu1P33QNZPmAKGhInfIZ55CwOkdFc64cyQNynLCXpHww39G1L",
            toolbar: {
               items: ["exportPdf", "bold", "italic", "link", "undo", "redo"],
            },
            cloudServices: {
               tokenUrl: 'https://81817.cke-cs.com/api/v4/OVwdufhejHtp2rnVoTt4/'
            },
            pagination: {
               // A4
               pageWidth: "21cm",
               pageHeight: "29.7cm",

               pageMargins: {
                  top: "20mm",
                  bottom: "20mm",
                  right: "12mm",
                  left: "12mm",
               },
            },
            exportPdf: {
               stylesheets: [
                  "./path/to/fonts.css",
                  "EDITOR_STYLES",
                  "./path/to/style.css",
               ],
               fileName: "my-file.pdf",
               converterOptions: {
                  format: "A4",
                  margin_top: "20mm",
                  margin_bottom: "20mm",
                  margin_right: "12mm",
                  margin_left: "12mm",
                  page_orientation: "portrait",
               },
            },
         },
      };
   },
};
</script>