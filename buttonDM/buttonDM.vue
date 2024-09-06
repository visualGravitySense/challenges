<template>
<button @click="toggleDarkMode" :class="{ 'dark-mode': darkMode }">
    {{ darkMode ? 'Light Mode' : 'Dark Mode' }}
  </button>
</template>
  
<style>
  button {
    padding: 0.75rem 1.5rem;
    background-color: #007bff;
    color: white;
    border: 2px solid transparent;
    border-radius: 1.5rem;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    outline: none;
    position: relative;
    overflow: hidden;
    transition: background-color 0.3s ease, border-color 0.3s ease, color 0.3s ease;
  }
  
  /* Цветовая смена на hover */
  button:hover {
    background-color: #fff;
    color: #007bff;
    border-color: #007bff;
  }
  
  /* Темный режим */
  button.dark-mode {
    background-color: #343a40;
    color: white;
    border-color: #343a40;
  }
  
  /* Анимация круга при клике */
  button:before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 300%;
    height: 300%;
    background-color: rgba(255, 255, 255, 0.3);
    transition: width 0.6s ease, height 0.6s ease, top 0.6s ease, left 0.6s ease;
    border-radius: 50%;
    transform: translate(-50%, -50%);
    z-index: 0;
    opacity: 0;
  }
  
  button:active:before {
    width: 0;
    height: 0;
    opacity: 1;
    transition: none;
  }
  
  /* Уровень текста поверх анимации */
  button span {
    position: relative;
    z-index: 1;
  }
</style>