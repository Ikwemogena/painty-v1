<template>
    <div class="container">
      <div class="landing">
        <h1 class="title">Color Palette Generator 
  Generate Color Schemes That work Beautifully</h1>
          <div class="buttons">
            <button class="solid-button cursor-pointer" @click="generatePalette">Generate a palette</button>
            <button class="button">Explore popular palette</button>
          </div>
  
          <div class="color-palette">
          <div v-for="color in randomColors" :key="color" :style="{ backgroundColor: color }" class="color-swatch"></div>
          <!-- {{ color }} -->
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  
  import chroma from 'chroma-js';
  
  // Generate a color scale with 5 colors between 'red' and 'blue'
  // const colorScale = chroma.scale(['random', 'random']).colors(5);
  
  // console.log(colorScale)
  // function generateRandomColor() {
  //   const randomColor = chroma.random();
  //   return randomColor.hex();
  // }
  
  // // Generate an array of 5 random colors
  // const randomColors = Array.from({ length: 5 }, generateRandomColor);
  
  // console.log(randomColors);
  
  function generateRandomColor() {
    const randomColor = chroma.random();
    return randomColor.hex();
  }
  
  const randomColors = ref([]);
  
  const generatePalette = () => {
    console.log('clicked.')
    randomColors.value = Array.from({ length: 5 }, generateRandomColor);
  
    console.log(randomColors.value)
  };

  generatePalette();
  
  </script>
  
  <style scoped>
  .container {
    width: 100%;
    /* padding: 4rem; */
  }
  .landing {
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  .title {
    font-size: 50px;
    max-width: 40rem;
    line-height: 4.4rem;
    color: #4F4F4F;
    text-justify: justify;
  }
  
  .buttons {
    display: flex;
    gap: 2rem;
  }
  .button {
    color: #5A5A5A;
    background-color: #fff;
    font-weight: 300;
    font-size: 18px;
    border: 1px solid #5A5A5A;
    padding: 1.2rem 3rem;
    border-radius: 0.2rem;
    cursor: pointer;
  }
  
  .solid-button {
    color: #fff;
    background-color: #284361;
    font-size: 18px;
    font-weight: 300;
    border: 1px solid #5A5A5A;
    padding: 1.2rem 3rem;
    border-radius: 0.2rem;
    cursor: pointer;
  }
  
  .color-palette {
    display: flex;
    /* gap: 1rem; */
    margin-top: 2rem;
    /* border: 1px solid red; */
  }
  
  .color-swatch {
    width: 100px;
    height: 100px;
    padding-right: 0;
  }
  

  
  @media screen and (max-width: 768px) {
    .container {
      /* padding: 4rem; */
    }
    .landing {
      /* flex-direction: row; */
      font-size: 2rem;
      /* align-items: center; */
      gap: 2rem;
    }
    .title {
      font-size: 2.7rem;
      line-height: 5.4rem;
    }
    
    .right {
        display: none;
    }
    .buttons {
      /* flex-direction: column; */
      gap: 1rem;
    }
    .button {
        /* flex-direction: row; */
      padding: 1.2rem 4rem;
    }
    .solid-button {
      padding: 1.2rem 4rem;
    }
    .color-palette {
      margin-top: 0;
    }

    .color-swatch {
        color: white;
        font-size: 1rem;
    }
  }

  @media screen and (max-width: 468px) {
    .container {
      /* padding: 4rem; */
    }
    .landing {
      /* flex-direction: row; */
      font-size:1.5rem;
      /* align-items: center; */
      gap: 2rem;
    }
    .title {
      font-size: 2rem;
      /* line-height: 5.4rem; */
      line-height: 2.5rem;
    }
    
    .right {
        display: none;
    }
    .buttons {
        width: 100%;
      flex-direction: column;
      gap: 1rem;
    }
    .button {
        /* flex-direction: row; */
      padding: 1.2rem 4rem;
    }
    .solid-button {
      padding: 1.2rem 4rem;
    }
    .color-palette {
      margin-top: 0;
      display: flex;
    flex-wrap: wrap;
    margin-bottom: 3rem;
    }

    .color-swatch {
        color: white;
        font-size: 1rem;
        margin-bottom: 3rem;
    }
  }

  </style>