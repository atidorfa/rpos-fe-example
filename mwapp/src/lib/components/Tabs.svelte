<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    export let tabs;
    export let activeTab;
</script>


<div class="tabs">
    <ul>
        {#each tabs as tab}
            <li on:click={() => dispatch('tabChange', tab)}>
                <div class:active={tab === activeTab}>{tab}</div>
            </li>           
        {/each}
    </ul>
</div>



<style>
    .tabs {
        position: fixed;
        top: 0; 
        margin-bottom: 4em;
    }

    ul {
        display: flex;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }

    li {
        margin: 0 16px;
        font-size: 18px;
        color: #555;
        cursor: pointer;
    }

    .active {
        color: #f44336;
        border-bottom: 2px solid #f44336;
        padding-bottom: 8px;
    }

</style>