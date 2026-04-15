---
layout: home
---

<script setup>
import { useData } from "vitepress";
import SiteHome from "vitepress-sls-blog-tmpl/SiteHome.vue";

const { theme, localeIndex } = useData();

const hero = {
  name: "FastCat",
  text: "Видео редактор с использованием ИИ",
  tagline: "",
  image: {
    src: theme.value.mainHeroImg,
    alt: "Логотип FastCat",
  },
  actions: [
    {
      theme: "brand",
      text: `📃 О проекте`,
      link: `/${localeIndex.value}/guide/about`,
    },
    {
      theme: "alt",
      text: `📢 Мы в соц сетях`,
      link: `/${localeIndex.value}/page/links`,
    },
  ],
}
const features = [
  {
    icon: "🤝",
    title: "Быстрое создание публикаций с помощью ИИ",
    details: "Используйте возможности искусственного интеллекта для создания качественного контента",
    linkText: "Читать о",
    link: "/ru/doc/ai-features",
  },
  {
    icon: "📖",
    title: "Подборки свежих новостей",
    details: "описание",
    linkText: "Читать о",
    link: "/ru/doc/index",
  },
]
</script>

<SiteHome :hero="hero" :features="features">
</SiteHome>
