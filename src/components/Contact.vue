<script setup>
import {themeColor, contactInfo} from "../data/items";
import {ref} from "vue";

const heading = "Contact Us";
const subHeading =
    "We provide text translation services for large formats and develop custom projects.";
const contactInfoHeading = "Contact Information";
const buttonSendMessage = "Send Message";

const labels = {
  firstName: "First Name",
  lastName: "Last Name",
  email: "Email",
  phone: "Phone",
  message: "Message",
};

const firstName = ref("");
const lastName = ref("");
const email = ref("");
const phone = ref("");
const message = ref("");

async function submitForm(event) {
  event.preventDefault();

  const telegramMessage = `
Новая заявка от клиента:
Имя: ${firstName.value} ${lastName.value}
Email: ${email.value}
Телефон: ${phone.value}
Сообщение: ${message.value}
  `;

  const botToken = "7219282300:AAFpBgoO232l2vQprDDP4Z0ZDRpnAn-aipQ";
  const chatId = "-1002442792451";
  const telegramUrl = `https://api.telegram.org/bot${botToken}/sendMessage`;

  const params = {
    chat_id: chatId,
    text: telegramMessage,
  };

  try {
    const response = await fetch(telegramUrl, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(params),
    });

    const responseText = await response.text();

    if (response.ok) {
      console.log("Message sent to Telegram:", responseText);
      // Reset the form
      resetForm();
    } else {
      console.error("Error sending message:", responseText);
    }
  } catch (error) {
    console.error("Network error:", error);
  }
}

function resetForm() {
  firstName.value = "";
  lastName.value = "";
  email.value = "";
  phone.value = "";
  message.value = "";
}
</script>

<template>
  <div class="untree_co-section" id="contact-section">
    <div class="container">
      <div class="row mb-4" data-aos="fade-up" data-aos-delay="0">
        <div class="col-12 text-center">
          <h2 class="heading">{{ heading }}</h2>
          <p>{{ subHeading }}</p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-7">
          <form
              class="contact-form"
              @submit="submitForm"
              data-aos="fade-up"
              data-aos-delay="100"
          >
            <div class="row">
              <div class="col-6">
                <div class="form-group">
                  <label for="fname">{{ labels.firstName }}</label>
                  <input
                      type="text"
                      class="form-control"
                      id="fname"
                      v-model="firstName"
                      required
                  />
                </div>
              </div>
              <div class="col-6">
                <div class="form-group">
                  <label for="lname">{{ labels.lastName }}</label>
                  <input
                      type="text"
                      class="form-control"
                      id="lname"
                      v-model="lastName"
                      required
                  />
                </div>
              </div>
            </div>
            <div class="form-group">
              <label for="email">{{ labels.email }}</label>
              <input
                  type="email"
                  class="form-control"
                  id="email"
                  v-model="email"
                  required
              />
            </div>
            <div class="form-group">
              <label for="phone">{{ labels.phone }}</label>
              <input
                  type="tel"
                  class="form-control"
                  id="phone"
                  v-model="phone"
                  required
              />
            </div>
            <div class="form-group">
              <label for="message">{{ labels.message }}</label>
              <textarea
                  class="form-control"
                  id="message"
                  cols="30"
                  rows="5"
                  v-model="message"
                  required
              ></textarea>
            </div>
            <button
                type="submit"
                class="btn btn-primary"
                :style="[{ backgroundColor: themeColor }, { borderColor: themeColor }]"
            >
              {{ buttonSendMessage }}
            </button>
          </form>
        </div>
        <div class="col-lg-4 ml-auto" data-aos="fade-up" data-aos-delay="200">
          <h3 class="h5 mb-4">{{ contactInfoHeading }}</h3>
          <address class="text-black d-flex">
            <span class="mt-1 icon-room mr-2"></span>
            <span>{{ contactInfo.address }}</span>
          </address>
          <ul class="list-unstyled ul-links mb-4">
            <li>
              <a :href="'tel://' + contactInfo.phone1" class="d-flex">
                <span class="mt-1 icon-phone mr-2"></span>
                <span>{{ contactInfo.phone1 }}</span>
              </a>
            </li>
            <li>
              <a :href="'tel://' + contactInfo.phone2" class="d-flex">
                <span class="mt-1 icon-phone mr-2"></span>
                <span>{{ contactInfo.phone2 }}</span>
              </a>
            </li>
            <li>
              <a :href="'mailto:' + contactInfo.email" class="d-flex">
                <span class="mt-1 icon-envelope mr-2"></span>
                <span>{{ contactInfo.email }}</span>
              </a>
            </li>
            <li>
              <a :href="contactInfo.website" target="_blank" class="d-flex">
                <span class="mt-1 icon-globe mr-2"></span>
                <span>{{ contactInfo.website }}</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
