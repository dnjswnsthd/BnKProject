<template>
  <footer class="footer">
    <div class="container-fluid">
      <ul class="nav">
        <li class="nav-item">
          <a
            class="nav-link"
            href="https://www.notion.so/Wonjun-Song-9b9c43bde41d46ad972bd223be8227fa"
          >
            Notion-WonJun
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="https://github.com/dnjswnsthd">
            Github-WonJun
          </a>
        </li>
      </ul>
      <div class="copyright">
        © {{ year }} made with Song & Team for a better web.
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      year: new Date().getFullYear(),
    };
  },
};
</script>
<style>
</style>
