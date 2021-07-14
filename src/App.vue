<template>
   <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
</template>

<script>
import ClassicEditor from '@ckeditor/ckeditor5-build-classic'
import DecoupledEditor from '@ckeditor/ckeditor5-build-decoupled-document';

export default {
   name: "App",
   data() {
      return {
         editor: DecoupledEditor,
         editorData: "<p>Content of the editor.</p>",
         editorConfig: {
            plugins:[
               
            ]
            // The configuration of the editor.
         },
      };
   },
};
</script>
