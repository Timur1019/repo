<script setup>
import { themeColor } from "../data/items";
import mainPhoto from "../assets/images/about.svg";

const heading = "About Us";
const subHeading = "About Our Team";
const totalMembers = "50";
const totalTeam = "20";
</script>

<template>
  <div class="untree_co-section" id="about-section">
    <div class="container">
      <div class="row justify-content-between">
        <div class="col-lg-8" data-aos="fade-up" data-aos-delay="100">
          <img :src="mainPhoto" alt="Image" class="img-fluid" />
        </div>
        <div class="col-lg-4">
          <div class="mb-4" data-aos="fade-up" data-aos-delay="0">
            <span class="caption" :style="[{ color: themeColor }]">{{
                heading
              }}</span>
            <h2 class="heading">{{ subHeading }}</h2>
          </div>
          <div class="mb-4" data-aos="fade-up" data-aos-delay="100">
            <p>
              Our company specializes in AI-powered translation, offering a unique product
              that ensures high quality and speed in text processing.
              We use cutting-edge AI technologies to provide clients with solutions that meet their needs.
            </p>
            <p>
              Additionally, we undertake scalable projects in the AI domain, delivering solutions for various tasks and industries.
              <span class="highlight"
              >We create products that help businesses adapt to modern demands</span
              >, striving for innovation and reliability.
            </p>
          </div>
          <ul
              class="list-unstyled ul-check primary mb-4"
              data-aos="fade-up"
              data-aos-delay="200"
          >
            <li>AI for Translation</li>
            <li>Scalable Projects Across Industries</li>
            <li>Innovation and Reliability</li>
          </ul>
          <div class="row count-numbers">
            <div class="col-lg-6" data-aos="fade-up" data-aos-delay="0">
              <span class="counter d-block"
              ><span :data-number="totalMembers">{{ totalMembers }}</span
              ><span>M</span></span
              >
              <span class="caption-2">Team Members</span>
            </div>
            <div class="col-lg-6" data-aos="fade-up" data-aos-delay="100">
              <span class="counter d-block"
              ><span :data-number="totalTeam">{{ totalTeam }}</span
              ><span></span
              ></span>
              <span class="caption-2">Team</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
