<script>
    import Item from "./Item.svelte";

    export let meetings;
</script>
<style>
    section {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
    }

    @media (min-width: 768px) {
        section {
            grid-template-columns: repeat( 2, 1fr)
        }
    }
</style>



<section id="meets">
{#each meetings as meeting}
<Item 
title = {meeting.title} 
subtitle = {meeting.subtitle} 
description = {meeting.description} 
imageUrl = {meeting.imageUrl} 
contactEmail = {meeting.contactEmail} 
city={meeting.city} />

{/each}
</section>