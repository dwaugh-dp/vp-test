<template>
    
  </template>
  
  <script>
  export default {
    data() {
      return {
        sliderValue: 5
      }
    }
  }
  </script>
  
  <style>
  .range-slider {
    -webkit-appearance: none;
    appearance: none;
    height: 10px;
    background-color: #0c58f0;
    border-radius: 5px;
    outline: none;
    opacity: 0.7;
    transition: opacity 0.2s;
  }
  
  .range-slider:hover {
    opacity: 1;
  }
  
  .range-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 20px;
    height: 20px;
    background-color: #574141;
    border-radius: 50%;
    cursor: pointer;
    box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1);
  }
  
  .range-slider::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background-color: #544f4f;
    border-radius: 50%;
    cursor: pointer;
    box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1);
  }
  </style>
  