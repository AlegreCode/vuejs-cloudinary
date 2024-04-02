<script setup>
import Form from './components/Form.vue';
import Viewer from './components/Viewer.vue';
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
      <div class="col-md-6">
        <Viewer />
      </div>
    </div>
  </div>
</template>