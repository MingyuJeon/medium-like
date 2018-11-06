<template>
<section class="section">
    <div class="container">
        <Index v-if="isIndex" />
        <Single v-if="!isIndex" />
    </div>
</section>
</template>

<script>
import ToolBar from "./components/ToolBar.vue";
import Index from "./layouts/Index";
import Single from "./layouts/Single";

export default {
  components: {
    ToolBar,
    Index,
    Single
  },
  computed: {
    layout() {
      if (this.$page.path) {
        return this.$page.frontmatter.layout || "Layout";
      }
      return "NotFound";
    },
    isIndex() {
      return this.$page.path.endsWith("/");
    }
  }
};
</script>
