<template>
  <div class="modal" v-if="isVisible">
    <div class="modal-coontent">
      <span class="close" @click="close">&times;</span>
        <ul>
          <h1>Mon CV</h1>
          <p>Crée le 10/11/2023</p>
          <p>HTML5 / CSS </p>
          <p>lien pdf du site</p>
          <p>le repository GitHub</p>
          • Les technologies utilisées.
          • La modal se fermera lorsqu'on clique sur le bouton de fermeture ou en dehors. Elle
          devra rester fixe sur la page même si on scrolle
      </ul>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ModalCV',
    data() {
      return{
        isVisible: false
      };
    },
    methods: {
      open() {
        this.isVisible= true;
      },
      close() {
        this.isVisible= false;
      },
    }
};
</script>

<style>

</style>