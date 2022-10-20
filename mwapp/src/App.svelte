<script>
  import Index from "./lib/_index.svelte";
  import Mwapp from "./lib/_mwapp.svelte"
  import Blank from "./lib/_blank.svelte"
  import Tabs from "./lib/components/Tabs.svelte"

  // pages
  let pages = ['_index', '_mwapp']
  let activePage = '_index'

  // tabs
	let tabs = ['HOME', 'SALE SCREEN', 'DRIVE THRU-ORDERS', 'FIRE ORDERS', 'KIOSK ORDERS', 'PAYMENT'];
	let activeTab = 'HOME';

	const tabChange = (e) => {
		activeTab = e.detail;
	}
</script>

<main>
{#if activePage === '_index'}
<Index />
<button on:click={() => { activePage = '_mwapp' }}>
  Go to mwapp
</button>
{:else if activePage === '_mwapp'}
  <Tabs {tabs} {activeTab} on:tabChange={tabChange}/>
  {#if activeTab === 'HOME'}
    <Mwapp />
  {:else}
		<Blank />
  {/if}
{/if}

</main>

<style>
button {
  margin-top: 4em;
  color: white;
  background-color: #262626;
}
</style> 