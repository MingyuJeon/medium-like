<template>
    <div>
        <div class="content">
            <h1>{{ $page.frontmatter.title }}</h1>
            <Content />
        </div>
        <div class="articles">
            <article class="post section" v-for="post in posts">
                <h2 class="subtitle is-4">{{ post.title }}</h2>
                <p>{{ post.frontmatter.excerpt }}</p>
                <a :href="post.path">Read More →</a>
            </article>
        </div>
    </div>
</template>
<script>
export default {
  computed: {
    posts() {
      return this.$site.pages
        .filter(
          page =>
            page.path.endsWith(".html") && page.path.startsWith(this.$page.path)
        )
        .sort(
          (a, b) =>
            Date.parse(b.frontmatter.date) - Date.parse(a.frontmatter.date)
        );
    }
  }
};
</script>