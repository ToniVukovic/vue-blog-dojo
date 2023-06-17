<template>
  <div class="spinner"></div>
</template>

<style scoped>
.spinner {
  display: block;
  width: 40px;
  height: 40px;
  margin: 30px auto;
  border: 3px solid transparent;
  border-radius: 50%;
  border-top-color: #ff8800;
  border-bottom-color: #ff880050;
  border-left-color: #ff880050;
  border-right-color: #ff880050;
  animation: spin 1s ease infinite;
}

@keyframes spin {
  to {
    transform: rotateZ(360deg);
  }
}
</style>
