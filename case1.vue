<template>
    <div class="sql-editor-component">
        <div
            ref="editor"
            class="editor language-sql h-100"
        />
    </div>
</template>

<script>
import { CodeJar } from 'codejar';
import Prism from 'prismjs';

export default {
    name: 'SQLEditorComponent',

    data() {
        return {
            editor: null
            template: null
        };
    },

    mounted() {
        this.editor = CodeJar(this.$refs.editor, Prism.highlightElement);
        this.editor.onUpdate(text => this.template.sql = text);
    }
} 
</script>
