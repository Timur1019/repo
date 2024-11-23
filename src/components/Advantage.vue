<script setup>
import { themeColor } from "../data/items";

const heading = "Benefits of Using Our Products";
const subHeading = "Innovative Solutions Based on Artificial Intelligence";
const buttonLearnMore = "Learn More";
const advantages = [
  {
    name: "Grow Your Business",
    des: "We help companies expand by leveraging the power of artificial intelligence and innovative technologies for sustainable growth.",
  },
  {
    name: "Create Cutting-Edge Products",
    des: "With our solutions, you can bring unique ideas to life and create products that meet high-quality standards.",
  },
  {
    name: "Achieve Success Every Day",
    des: "Our technologies help achieve outstanding results and increase productivity on a daily basis.",
  },
  {
    name: "Bring Ideas to Life",
    des: "We provide flexible and scalable solutions that take your ideas to the next level.",
  },
];
</script>

<template>
  <div class="untree_co-section">
    <div class="container">
      <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading">{{ heading }}</h2>
          <p>{{ subHeading }}</p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-6 mb-4" data-aos="fade-up" data-aos-delay="100">
          <div class="service horizontal d-flex">
            <div class="service-icon color-1 mb-4">
              <!-- SVG Icon -->
            </div>
            <div class="service-contents">
              <h3>{{ advantages[0].name }}</h3>
              <p>{{ advantages[0].des }}</p>
              <p>
                <a href="#" class="read-more" :style="[{ color: themeColor }]">
                  {{ buttonLearnMore }}
                </a>
              </p>
            </div>
          </div>
        </div>
        <div class="col-lg-6 mb-4" data-aos="fade-up" data-aos-delay="200">
          <div class="service horizontal d-flex">
            <div class="service-icon color-2 mb-4">
              <!-- SVG Icon -->
            </div>
            <div class="service-contents">
              <h3>{{ advantages[1].name }}</h3>
              <p>{{ advantages[1].des }}</p>
              <p>
                <a href="#" class="read-more" :style="[{ color: themeColor }]">
                  {{ buttonLearnMore }}
                </a>
              </p>
            </div>
          </div>
        </div>
        <div class="col-lg-6 mb-4" data-aos="fade-up" data-aos-delay="300">
          <div class="service horizontal d-flex">
            <div class="service-icon color-3 mb-4">
              <!-- SVG Icon -->
            </div>
            <div class="service-contents">
              <h3>{{ advantages[2].name }}</h3>
              <p>{{ advantages[2].des }}</p>
              <p>
                <a href="#" class="read-more" :style="[{ color: themeColor }]">
                  {{ buttonLearnMore }}
                </a>
              </p>
            </div>
          </div>
        </div>
        <div class="col-lg-6 mb-4" data-aos="fade-up" data-aos-delay="400">
          <div class="service horizontal d-flex">
            <div class="service-icon color-4 mb-4">
              <!-- SVG Icon -->
            </div>
            <div class="service-contents">
              <h3>{{ advantages[3].name }}</h3>
              <p>{{ advantages[3].des }}</p>
              <p>
                <a href="#" class="read-more" :style="[{ color: themeColor }]">
                  {{ buttonLearnMore }}
                </a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
