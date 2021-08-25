<script lang="ts">
  import { Facebook, Twitter } from "svelte-share-buttons-component"

  const url = "https://single-page-svelte.vercel.app"
  const title = "Single Page Svelte"
</script>

<div class="flex gap-2 justify-center w-full fixed bottom-4 center">
  <Facebook class="h-10 w-10" {url} />
  <Twitter class="h-10 w-10" text={title} {url} />
</div>
