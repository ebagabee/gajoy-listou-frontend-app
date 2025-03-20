<template>
  <q-page class="listou-page">
    <div class="content-container">
      <div class="header">
        <div class="title">Crie sua</div>
        <div class="subtitle">Lista de Compras</div>
        <div class="description">
          Com o <span class="highlight text-dark text-italic">Listou</span>, você pode criar e
          organizar suas compras com
          <span class="highlight">facilidade</span>
        </div>
      </div>

      <div class="image-section">
        <q-img src="/images/background-initial.png" alt="Onda de fundo" class="wave-background" />
        <q-img
          src="/images/prancheta.png"
          alt="Prancheta com lista de compras"
          class="prancheta-img"
        />
      </div>

      <div class="buttons-container">
        <q-btn class="entrar-btn" unelevated label="ENTRAR" />
        <q-btn class="offline-btn" unelevated label="CONTINUAR OFFLINE" />
      </div>
    </div>
  </q-page>
</template>

<script setup></script>

<style scoped>
.listou-page {
  background-color: #f5f5f5;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-container {
  background-color: white;
  width: 100%;
  max-width: 400px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.05);
}

.header {
  margin-top: 60px;
  text-align: center;
  margin-bottom: 40px;
}

.title {
  font-size: 2rem;
  font-weight: bold;
  color: #000;
}

.subtitle {
  font-size: 2.2rem;
  font-weight: bold;
  color: #ff6421;
  margin-bottom: 15px;
}

.description {
  font-size: 1.3rem;
  color: #000;
  text-align: center;
}

.highlight {
  color: #ff6421;
  font-weight: bold;
}

.image-section {
  position: relative;
  margin: 80px 0;
  height: 230px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.wave-background {
  position: absolute;
  width: 100vw;
  height: auto;
  z-index: 1;
  margin-top: 100px;
}

.prancheta-img {
  position: relative;
  z-index: 2;
  max-width: 300px;
}

.buttons-container {
  margin-top: 40px;
  margin-bottom: 50px;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.entrar-btn {
  background-color: #e0e0e0;
  color: #000;
  font-weight: bold;
  width: 60%;
  margin: 0 auto;
  padding: 14px 0;
  border-radius: 25px;
  letter-spacing: 1px;
}

.offline-btn {
  background-color: #ff6421;
  color: white;
  font-weight: bold;
  width: 60%;
  margin: 0 auto;
  padding: 14px 0;
  border-radius: 25px;
  letter-spacing: 0.5px;
}
</style>
