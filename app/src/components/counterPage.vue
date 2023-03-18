<template>
  <div class="header-box">
    <header>
      <div class="wrapper">
        <nav>
          <router-link class="link" to="/">COUNTER</router-link>
          <router-link class="link" to="/404error">404 PAGE</router-link>
        </nav>
      </div>
    </header>
  </div>
  <div class="counter-wrapper">
    <div class="counter-box">
      <div class="heading-count">
        <p
          class="count"
          :class="{
            'count--positive': state.count > 0,
            'count--negative': state.count < 0,
          }"
        >
          {{ formattedCount }}
        </p>
      </div>

      <div class="button-box">
        <button class="counter-button" @click="incrementCount">+</button>
        <button class="counter-button" @click="decrementCount">-</button>
        <button class="counter-button" @click="resetCount">Reset</button>
      </div>
      <div class="input-value">
        <input type="number" placeholder="insert count" v-model="state.count" />
        <button class="setbutton" @click="setValue">Set Value</button>
      </div>
    </div>
  </div>
</template>

<script>
import { useCounter } from "@/composable/useCounter";

export default {
  setup() {
    const {
      state,
      formattedCount,
      incrementCount,
      decrementCount,
      resetCount,
      setValue,
    } = useCounter();

    return {
      state,
      formattedCount,
      incrementCount,
      decrementCount,
      resetCount,
      setValue,
    };
  },
};
</script>

<style>
  body {
      background-color: #01708B;
    display: flex;
    justify-content: center;
    
  }
  
  .header-box {
    background-color: white;
    color: #fff;
    padding: 10px 10px;
    margin:10px 10px;
    border-radius:10px;
  }

  header {
    display: flex;
    justify-content: center;
  
  }



  .link {
    color:  #01708B;
    text-decoration: none;
    padding: 5px 20px;
    font-size: 25px;
    font-weight: bold;
  }

  .link:hover {
    color: white;
    background-color: #01708B; 
    border-radius:10px;
  }

  .counter-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .counter-box {
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
    padding: 30px;
    text-align: center;
  }

  .count-heading {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
  }

  .count {
    font-size: 10rem;
    font-weight: bold;
    color: black;
    margin: 0;
    text-shadow: 2px 2px #8c8c8c; /* Dark gray */
  }

  .count--positive {
    color: green;
  }

  .count--negative {
    color: red;
  }

  .button-box {
    margin-bottom: 20px;
  }

  .counter-button, .setbutton {
    display: inline-block;
    background-color: #01708B;
    color: white;
    font-weight: bold;
    text-decoration: none;
    padding: 1rem 2rem;
    border-radius: 5px;
    box-shadow: 2px 2px #8c8c8c; /* Dark gray */
    transition: all 0.3s ease;
    margin:20px;
    
  }

  .counter-button:hover, .setbutton:hover{
    background-color: white;
    color:black;

  }

  .input-value {
    display: flex;
    justify-content:center;
    display: inline-block;
    color: white;
    font-weight: bold;
    text-decoration: none;
    padding: 1rem 2rem;
    border-radius: 5px;
    box-shadow: 1px 1px 2px 2px #8c8c8c; /* Dark gray */
    transition: all 0.3s ease;
  
  
    }
</style>