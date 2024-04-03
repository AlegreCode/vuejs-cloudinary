<script setup>
import { ref } from 'vue';
import Form from './components/Form.vue';
import Viewer from './components/Viewer.vue';

const url_image = ref("https://fakeimg.pl/600x300/");
</script>

<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <h1 class="text-center display-3">Subir imagen</h1>
        <hr>
        <Form />
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-md-6 text-center">
        <Viewer :urlImage="url_image"/>
      </div>
    </div>
  </div>
</template>