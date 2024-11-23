<template>
  <div class="untree_co-section bg-light">
    <div class="container">
      <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading">{{ heading }}</h2>
          <p>{{ subHeading }}</p>
        </div>
      </div>
      <div class="row">
        <div
            v-for="(item, index) in blogItems"
            :key="index"
            class="col-md-6 mb-4 mb-lg-0 col-lg-4"
            :data-aos="'fade-up'"
            :data-aos-delay="index * 100"
        >
          <div class="news-item">
            <!-- Изображение и автор -->
            <div class="vcard d-flex align-items-center mb-4">
              <div class="img-wrap">
                <img :src="item.photo" alt="Image" class="img-fluid" />
              </div>
              <div class="post-meta ml-3">
                <strong>Автор: {{ item.name }}</strong>
                <span>{{ item.date }}</span>
              </div>
            </div>
            <!-- Контент -->
            <div class="news-contents mb-4">
              <span class="post-meta-2">{{ item.category }}</span>
              <h3>
                <a :href="item.link" target="_blank">{{ item.title }}</a>
              </h3>
            </div>
            <!-- Кнопка -->
            <div class="text-center mt-auto">
              <button
                  type="button"
                  class="btn btn-primary"
                  data-toggle="button"
                  aria-pressed="false"
                  autocomplete="off"
                  @click="goToArticle(item.link)"
              >
                Read more
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const heading = "Our News";
const subHeading = "Latest Updates and Achievements in AI and Translations";


const blogItems = ref([]);

async function fetchNews() {
  try {
    const response = await fetch("https://newsapi.org/v2/top-headlines?country=us&apiKey=f52de76d448944e98b88b341edbc4921");
    const data = await response.json();

    if (data.articles) {
      blogItems.value = data.articles.map((item) => ({
        title: item.title,
        name: item.author || "Неизвестный автор",
        date: new Date(item.publishedAt).toLocaleDateString("ru-RU", {
          day: "numeric",
          month: "long",
          year: "numeric",
        }),
        category: item.source.name,
        photo: item.urlToImage || "default-image.jpg",
        link: item.url || "#",
      })).slice(0, 3); // Ограничиваем до 3 новостей
    }
  } catch (error) {
    console.error("Error fetching news:", error);
  }
}

function goToArticle(link) {
  window.open(link, "_blank"); // Открывает ссылку в новой вкладке
}

onMounted(fetchNews); // Загружаем новости при монтировании компонента
</script>

<style scoped>
.news-item {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 4px;
  background-color: #fff;
  transition: transform 0.3s, box-shadow 0.3s;
}

.news-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.news-contents h3 {
  font-size: 1.2em;
  margin: 0;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.news-contents .post-meta-2 {
  font-size: 0.9em;
  color: gray;
  display: block;
  margin-bottom: 8px;
}

.img-wrap {
  height: 150px;
  overflow: hidden;
  border-radius: 8px;
}

.img-wrap img {
  width: 100%;
  height: auto;
  object-fit: cover;
}
</style>
