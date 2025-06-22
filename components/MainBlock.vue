<template>
  <div class="content">
    <section class="list-section">
      <h2>Заголовок списка:</h2>
      <ul>
        <li>Опция 1</li>
        <li>Опция 2</li>
        <li>Опция 3</li>
      </ul>
    </section>

    <section class="main-section">
      <div class="banner">Look at my website</div>

      <h2>Заголовок основного блока</h2>
      <div class="greeting">
        <p>{{ greetingText }}</p>
        <button @click="changeGreeting">Поменять приветствие</button>
      </div>

      <div class="cards-container">
        <div class="card">Here</div>
        <div class="card">And here</div>
      </div>
    </section>

    <section class="fill-section">
      <p>Наполнение третьего блока</p>
      <img src="../assets/img/img.jpg" alt="Пример изображения" class="section-image">
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const greetingText = ref('Hello, World!')

const changeGreeting = () => {
  greetingText.value = greetingText.value === 'Hello, World!'
      ? 'Hello, FEFU!'
      : 'Hello, World!'
}
</script>

<style scoped lang="scss">
@use '@/assets/scss/mixins' as mixins;

.content {
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
}

.list-section, .main-section, .fill-section {
  @include mixins.card-base;
  padding: 20px;
}

.list-section {
  flex: 1;
  background: #a4b9fc; }


.main-section {
  flex: 2;
  background: #abf8b1;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.banner {
  @include mixins.card-base;
  background: #4CAF50;
  color: white;
  font-weight: bold;
  padding: 15px;
}

.greeting {
  p {
    font-weight: bold;
    font-size: 1.1rem;
    margin-bottom: 10px;
  }
}

button {
  @include mixins.button-style;
  font-family: var(--font-title),serif;
}

.cards-container {
  display: flex;
  gap: 15px;
  margin-top: 20px;
}

.card {
  @include mixins.card-base;
  flex: 1;
  background-color: #abffff;
  max-width: 200px;
  padding: 15px;
}

.fill-section {
  flex: 1;

  .section-image {
    max-width: 100%;
    height: auto;
    margin-top: 15px;
    border-radius: 5px;
  }
}
</style>