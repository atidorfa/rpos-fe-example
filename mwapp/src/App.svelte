<script>
  import Button from "./lib/Button.svelte";
  import Index from "./lib/_index.svelte";
  import Mwapp from "./lib/_mwapp.svelte"

  // render
  let pages = ['_index', '_mwapp']
  let activePage = '_index'

  const pageChange = (e) => {
    activePage = '_mwapp'
	}

  function handleClick() {
    console.log(activePage)
		activePage = '_mwapp'
    console.log(activePage)
	}
</script>

<main>
{#if activePage === '_index'}
<Index />
<button on:click={() => { activePage = '_mwapp' }}>
  Go to mwapp
</button>
{:else if activePage === '_mwapp'}
  <Mwapp />
{/if}

</main>

<style>
button {
  margin-top: 4em;
  color: white;
  background-color: #262626;
}
</style> 