<script setup>
import DefaultTheme from "vitepress/theme";
import { useData } from "vitepress";
import PageFindSearch from "vitepress-sls-blog-tmpl/PageFindSearch.vue";
import NavSearchButton from "vitepress-sls-blog-tmpl/NavSearchButton.vue";

const { Layout: DefaultLayout } = DefaultTheme;
const { theme, frontmatter } = useData();
</script>

<template>
    <div id="modals"></div>

    <DefaultLayout>
        <template #nav-bar-content-before>
            <PageFindSearch>
                <NavSearchButton />
            </PageFindSearch>
        </template>

        <template #layout-bottom>
            <footer
                v-if="frontmatter.footer !== false && theme.footer"
                class="VPFooter"
            >
                <div class="container">
                    <div v-if="theme.footer.links" class="links">
                        <a
                            v-for="link in theme.footer.links"
                            :key="link.link"
                            :href="link.link"
                            target="_blank"
                            rel="noopener"
                            class="link"
                        >
                            {{ link.text }}
                        </a>
                    </div>
                    <p
                        v-if="theme.footer.message"
                        class="message"
                        v-html="theme.footer.message"
                    ></p>
                    <p
                        v-if="theme.footer.copyright"
                        class="copyright"
                        v-html="theme.footer.copyright"
                    ></p>
                </div>
            </footer>
        </template>
    </DefaultLayout>
</template>

<style scoped>
.VPFooter {
    position: relative;
    z-index: var(--vp-z-index-footer);
    border-top: 1px solid var(--vp-c-divider);
    padding: 32px 24px;
    background-color: var(--vp-c-bg);
}

.VPFooter.has-sidebar {
    display: none;
}

.container {
    margin: 0 auto;
    max-width: var(--vp-layout-max-width);
    text-align: center;
}

.links {
    display: flex;
    justify-content: center;
    gap: 24px;
    margin-bottom: 8px;
}

.link {
    font-size: 14px;
    font-weight: 500;
    color: var(--vp-c-text-1);
    transition: color 0.25s;
}

.link:hover {
    color: var(--vp-c-brand-1);
}

.message,
.copyright {
    line-height: 24px;
    font-size: 14px;
    font-weight: 500;
    color: var(--vp-c-text-2);
}
</style>
