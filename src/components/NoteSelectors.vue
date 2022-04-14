<script>
import NoteSelector from './NoteSelector.vue'
export default {
  components: {
    NoteSelector
  },
  data: function () {
    return {

    }
  },
  methods: {
    selectNote: function (note) {
      this.$emit("selectNote", note);
      console.log('selecting from NoteSelectorss');
    }
  },
  props: ["notes", "selectedNoteId"]
}
</script>

<template>
  <div class="note-selectors">
    <NoteSelector v-for="note in notes" v-bind:note="note" v-bind:selectedNoteId="selectedNoteId"
      v-on:selectNote="selectNote" />
  </div>
</template>