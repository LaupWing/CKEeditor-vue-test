<template>
   <ckeditor
      :editor="editor"
      v-model="editorData"
      :config="editorConfig"
   ></ckeditor>
</template>

<script>
import ClassicEditor from "@ckeditor/ckeditor5-build-classic";
// import DecoupledEditor from '@ckeditor/ckeditor5-build-decoupled-document';
import Pagination from "@ckeditor/ckeditor5-pagination/src/pagination";

export default {
   name: "App",
   data() {
      return {
         editor: ClassicEditor,
         editorData: "<p>Content of the editor.</p>",
         editorConfig: {
            plugins:[
               Pagination
            ],
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
            // The configuration of the editor.
         },
      };
   },
};
</script>
