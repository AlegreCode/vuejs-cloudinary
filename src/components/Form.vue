<script setup>
import { ref } from 'vue';

const fileInput = ref(null);

function handleSubmit(){
  const file = fileInput.value.files[0];
  console.log("Archivo seleccionado: ", file);
}

function handleFileChange(event) {
  var file = event.target.files[0];
  var url = URL.createObjectURL(file);
  document.querySelector('img').src = url;
};
</script>
<template>
    <form @submit.prevent="handleSubmit">
      <div class="form-group py-2 text-center">
        <div style="width: 350px;height: auto;" class="mx-auto">
            <img src="https://fakeimg.pl/350x200/" alt="avatar" id="preview" class="img-thumbnail mb-2 mx-auto" />
        </div>
        <input type="file" id="image" class="form-control-file" @change="handleFileChange" ref="fileInput"/>
      </div>
      <div class="form-group py-2 d-grid">
          <button type="submit" class="btn btn-primary">Enviar</button>
      </div>
    </form>
  </template>