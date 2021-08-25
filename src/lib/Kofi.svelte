<script lang="ts">
  import { onMount } from "svelte"

  export let name: string
  export let label = "Support me"

  let kofiReady = false
  let mounted = false

  onMount(() => {
    mounted = true
    if (kofiReady) {
      loadKofiWidget()
    }
  })

  function kofiLoaded() {
    kofiReady = true
    if (mounted) {
      loadKofiWidget()
    }
  }

  function loadKofiWidget() {
    window.kofiWidgetOverlay?.draw(
      name,
      {
        type: "floating-chat",
        "floating-chat.donateButton.text": label,
        "floating-chat.donateButton.background-color": "#ff3e00",
        "floating-chat.donateButton.text-color": "#fff",
      },
      "kofiContainer"
    )
  }
</script>

<svelte:head>
  <script
    on:load={() => kofiLoaded()}
    async
    defer
    type="text/javascript"
    src="https://storage.ko-fi.com/cdn/scripts/overlay-widget.js" />
</svelte:head>

{#if name}
  <div id="kofiContainer" class="web-only">{label}</div>
{/if}
