<script setup>
const items = [
  {
    iconBg: "background-color: #6fe7dd",
    title: "Expand Your Business",
    description:
        "We help companies overcome language barriers by providing text translation services for large formats.",
  },
  {
    iconBg: "background-color: #ffc93c",
    title: "Product Creation",
    description:
        "Our team develops custom projects to meet the unique needs of your business.",
  },
  {
    iconBg: "background-color: #f73859",
    title: "Success Every Day",
    description:
        "With us, you can be assured of high-quality translations and timely delivery of materials.",
  },
  {
    iconBg: "background-color: #407BFF",
    title: "Bring Ideas to Life",
    description:
        "We help turn your ideas into high-quality translated materials.",
  },
];
</script>

<template>
  <div class="untree_co-section">
    <div class="container">
      <div class="row">
        <div
            v-for="(item, index) in items"
            :key="index"
            class="col-md-6 mb-4 mb-lg-0 col-lg-3"
            :data-aos="'fade-up'"
            :data-aos-delay="index * 100"
        >
          <div class="service">
            <div class="service-icon mb-4" :style="[item.iconBg]">
              <svg
                  class="bi bi-app-indicator"
                  width="1em"
                  height="1em"
                  viewBox="0 0 16 16"
                  fill="currentColor"
                  xmlns="http://www.w3.org/2000/svg"
              >
                <!-- SVG icon content -->
              </svg>
            </div>
            <div class="service-contents">
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
