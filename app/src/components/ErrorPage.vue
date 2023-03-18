<template>
  <div class="error">
    <div class="error-page">
      <p class="text">404</p>
      <router-link to="/" class="home">Return to Home</router-link>
    </div>
  </div>
</template>

<script>
export default {};
</script>


<style>
  .error {
     background-color: #01708B;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .text {
    font-size: 10rem;
    font-weight: bold;
    color: white;
    margin: 0;
    text-shadow: 2px 2px #8c8c8c; /* Dark gray */
  }

  .subtext {
    font-size: 2rem;
    font-weight: bold;
    color: white;
    margin-top: 0;
    text-shadow: 1px 1px #8c8c8c; /* Dark gray */
  }

  .home {
    display: inline-block;
    background-color: white;
    color:#01708B;
    font-weight: bold;
    text-decoration: none;
    padding: 1rem 2rem;
    border-radius: 5px;
    box-shadow: 2px 2px #8c8c8c; /* Dark gray */
    transition: all 0.3s ease;
  }

  .home:hover {
    transform: translate(2px, 2px);
    box-shadow: none;
  }
</style>
