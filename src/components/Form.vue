<script setup>
function handleFileChange(event) {
  var file = event.target.files[0];
  var url = URL.createObjectURL(file);
  document.querySelector('img').src = url;
};
</script>
<template>
    <form>
      <div class="form-group py-2 text-center">
        <img src="https://fakeimg.pl/350x200/" alt="avatar" id="preview" class="img-thumbnail mb-2 mx-auto" />
        <input type="file" id="image" class="form-control-file" @change="handleFileChange"/>
      </div>
      <div class="form-group py-2 d-grid">
          <button type="submit" class="btn btn-primary">Enviar</button>
      </div>
    </form>
  </template>