<script setup>
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['getUrlImage']);

const fileInput = ref(null);

async function handleSubmit() {
  const file = fileInput.value.files[0];
  const cloudname = "dezkmxexp";
  const formData = new FormData();
  formData.append('file', file);
  formData.append('upload_preset', 'images_vuejs');

  try {
    const response = await fetch(`https://api.cloudinary.com/v1_1/${cloudname}/image/upload`, {
      method: 'POST',
      body: formData
    });
    const data = await response.json();
    console.log("Archivo subido con éxito: ", data);
    document.getElementById('preview').src = "https://fakeimg.pl/350x200/";
    emit('getUrlImage', data.secure_url);

  } catch (error) {
    console.error("Error al subir el archivo: ", error);
  }
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