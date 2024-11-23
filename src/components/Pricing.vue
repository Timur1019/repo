<script setup>
import {themeColor} from "../data/items";

const heading = "About Our Translator";
const subHeading =
    "The perfect tool for translation. Fast, accurate, and simple! " +
    "We use the latest artificial intelligence technologies " +
    "so you can easily communicate in any language.";
const actionButtonText = "Try Now";
const imageSrc = "https://st2.depositphotos.com/2894069/10690/v/450/depositphotos_106903146-stock-illustration-vector-detailed-character-language-translator.jpg"; // Replace with the desired image URL
</script>

<template>
  <div class="untree_co-section bg-light" id="about-section">
    <div class="container">
      <div class="row align-items-center">
        <!-- Text Section -->
        <div class="col-lg-6" data-aos="fade-right" data-aos-delay="100">
          <h2 class="heading">{{ heading }}</h2>
          <p class="subheading">{{ subHeading }}</p>
          <a
              href="#"
              class="btn btn-primary mt-3"
              :style="[
              { backgroundColor: themeColor },
              { borderColor: themeColor },
            ]"
          >{{ actionButtonText }}</a>
        </div>
        <!-- Image Section -->
        <div class="col-lg-6 text-center" data-aos="fade-left" data-aos-delay="200">
          <img :src="imageSrc" alt="Translator illustration" class="img-fluid rounded">
        </div>
      </div>
    </div>
  </div>
</template>
