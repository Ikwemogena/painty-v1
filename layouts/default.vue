<template>
    <div class="home">
        <div class="left">
            <header class="shadow-sm bg-white">
            <nav class="containers
        ">
                <!-- <NuxtLink to="" class="font-bold" >Painty</NuxtLink> -->
                <img src="/paint-logo.svg" alt="">
                <div>
                    <ul class="nav-items">
                    <li class="text-5xl"><NuxtLink to="">Palettes</NuxtLink></li>
                    <li><NuxtLink to="">Blog</NuxtLink></li>
                    <li><NuxtLink to="">About Us</NuxtLink></li>
                    <li><NuxtLink to="" id="button">Sign Up</NuxtLink></li>
                </ul>
                </div>
                <div></div>
            </nav>
        </header>


            <div class="containers
        ">
                <slot />
            </div>
        </div>

        <div class="right ">
            <img src="/painty-bg.png" alt="">
        </div>

    </div>
</template>

<script setup>


</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;300;400;500&display=swap');

body {
    background-color: red;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

.home {
    display: flex;
    justify-content: space-between;
    gap: 0;
    padding: 0;
    margin: 0;
    height: 100vh;
    overflow: hidden;
}

.right img{
    /* width: 100vh;
    height: 90vh;   */
}

.containers {
  /* width: 100vh; */
  /* margin-right: 0rem; */
  padding: 1rem 0 0 2.5rem;
  font-family: 'Poppins', sans-serif;
  /* height: 100vh; */
}
nav {
    display: flex;
    /* gap: 8rem; */
    align-items: center;
}
ul {
    list-style: none;
    text-decoration: none;
}

.nav-items {
    display: flex;
    align-items: center;
    gap: 3rem;
    font-size: 20px;
    color: #5A5A5A;
}

#button {
    color: #284361;
    background-color: #fff;
    font-weight: 400;
    border: 1px solid #284361;
    padding: 0.5rem 1.2rem;
    border-radius: 0.2rem;
}

#button:hover {
    background-color: #284361;
    color: #fff;
    cursor: pointer;
}

@media screen and (max-width: 768px) {
    .container {
      /* padding: 4rem; */
    }
    .landing {
      /* flex-direction: row; */
      font-size: 2rem;
      align-items: center;
      gap: 4rem;
    }
    .title {
      font-size: 2.7rem;
      line-height: 5.4rem;
    }
    
    .right {
        display: none;
    }
    .buttons {
      flex-direction: column;
      gap: 1rem;
    }
    .button {
      padding: 1.2rem 4rem;
    }
    .solid-button {
      padding: 1.2rem 4rem;
    }
    .color-palette {
      margin-top: 0;
    }
  }

  @media screen and (max-width: 468px) {
    .containers {
        padding: 1rem;
    }
    .landing {
      /* flex-direction: row; */
      font-size: 2rem;
      align-items: center;
      /* gap: 4rem; */
    }

    .nav-items {
        display: none;
    }

  }
</style>