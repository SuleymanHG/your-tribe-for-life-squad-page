<script>
  export let data;
  const members = data?.members ?? [];

  // darkmode
  import { onMount } from "svelte"

onMount(() => {
  const btn = document.getElementById("dark-mode-button")

  btn.addEventListener("click", () => {

    document.body.classList.toggle("dark-mode-active")
  })
})
</script>

<main>
    <section class="heading">
        <h1>Maak kennis met Hva FDND</h1>
        <p>Frontend Design & Development aan de HvA. Hier leren we ontwerpen en bouwen voor het web. 
            Ontmoet alle studenten op onze squadpage!</p>
    </section>

    <div class="layout-cards">
        {#each members as m}
          <img src={`https://fdnd.directus.app/assets/${m.mugshot}?w=200&h=200&fit=cover`} alt={m.name} />
        {/each}
    </div>
    
</main>

