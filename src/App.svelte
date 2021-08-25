<script lang="ts">
  import "twind/shim"
  import { tw } from "twind"
  import logo from "./assets/svelte.png"
  import Kofi from "./lib/Kofi.svelte"
  import Menu from "./lib/Menu.svelte"
  import Social from "./lib/Social.svelte"

  const url = "https://single-page-svelte.vercel.app"
  const title = "Single Page Svelte"

  const menuItems = [{ name: "Github", url: "https://github.com/narze/single-page-svelte" }]
</script>

<Kofi name="narze" label="Support Me" />
<Menu items={menuItems} />
<Social {url} {title} />

<main class="w-full h-screen flex flex-col justify-center items-center">
  <h1 class="text-6xl text-green-400 flex flex-col">
    <span>Single</span><span>Page</span><span>Svelte</span>
  </h1>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell,
      "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
