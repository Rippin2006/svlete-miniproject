<script>
  import Seo from "$lib/Seo.svelte";
  import What from "$lib/What.svelte";

  export let data;

  const { posts } = data;
</script>

<What />

<div class="container">
  <div class="grid">
      
  </div>

  <div class="">

  </div>
</div>

<Seo title="Business Frontpage" description="This is homepage" type="WebSite" />

<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2em;
    padding: 2em 0;
  }
</style>
