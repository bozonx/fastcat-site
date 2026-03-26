---
layout: home
---

<script setup>
import { useData } from "vitepress";
import SiteHome from "vitepress-sls-blog-tmpl/SiteHome.vue";

const { theme, localeIndex } = useData();

const hero = {
  name: "FastCat",
  text: "AI-powered video editor",
  tagline: "",
  image: {
    src: theme.value.mainHeroImg,
    alt: "FastCat logo",
  },
  actions: [
    {
      theme: "brand",
      text: `📃 About the project`,
      link: `/${localeIndex.value}/doc/about`,
    },
    {
      theme: "alt",
      text: `📢 We in social media`,
      link: `/${localeIndex.value}/page/links`,
    },
  ],
}
const features = [
  {
    icon: "🤝",
    title: "Fast creation of publications using AI",
    details: "Use the capabilities of artificial intelligence to create quality content",
    linkText: "Read about",
    link: "/en/doc/ai-assistant",
  },
  {
    icon: "📖",
    title: "News compilations",
    details: "",
    linkText: "Read about",
    link: "/en/doc/news-compilations",
  },
]
</script>

<SiteHome :hero="hero" :features="features">
</SiteHome>
