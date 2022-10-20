<script>
  import Index from "./lib/_index.svelte";
  import Mwapp from "./lib/_mwapp.svelte"

  // render
  let pages = ['_index', '_mwapp']
  let activePage = '_mwapp'

  const pageChange = (e) => {
    activePage = '_mwapp'
	}
</script>

<main>
{#if activePage === '_index'}
  <Index />
{:else if activePage === '_mwapp'}
  <Mwapp />
{/if}
</main>

<style>

</style> 