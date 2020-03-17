<script>
  import messageData from "../data/messages.json";
  import { flashMessage} from "./stores.js";
  import { mirror } from "./stores.js";
  import Button from "./components/Button.svelte";
  import Flash from "./components/Flash.svelte";
  import MirrorToggle from "./components/MirrorToggle.svelte";
</script>

<main>
  {#if $flashMessage.label}
  <Flash />
  {:else}
  <div id="buttons">
    <MirrorToggle />
    <h1>VOIP Flashcards</h1>
    <p>Ontworpen voor mobiele toestellen. Kies of je wil spiegelen of niet. Tik om een bericht te kiezen. Tik om terug leeg te maken. Richt het gekozen bericht naar je camera.</p>
    <p class='small'>Gemaakt door <a href="https://tomarmitage.com">Tom Armitage</a> (<a href="https://twitter.com/tom_armitage">@tom_armitage</a>). Dit staat <a href="https://github.com/infovore/voip-flashcards">op Github</a>. (Vind je dit leuk? <a class='tipjar' href="https://monzo.me/thomasarmitage/3.00?d=Thanks%20for%20VOIPcards!">Koop me een koffie!</a>)</p>
    {#each messageData as message}
    <Button {...message} />
    {/each}
  </div>
  <footer>
    Gemaakt door <a href="https://tomarmitage.com">Tom Armitage</a> (<a href="https://twitter.com/tom_armitage">@tom_armitage</a>). Dit staat <a href="https://github.com/infovore/voip-flashcards">op Github</a>. (Vind je dit leuk? <a class='tipjar' href="https://monzo.me/thomasarmitage/3.00?d=Thanks%20for%20VOIPcards!">Koop me een koffie!</a>)
  </footer>
  {/if}
</main>

<style>
main {
  height: 100%;
}
h1 {
  margin: 0 0 1rem;
}
#buttons {
  margin: 2rem 0;
}

.small {
  font-size: 0.85rem;
}

.tipjar {
  font-weight: bold;
}

footer {
  font-size: 0.85rem;
  border-top: 1px solid #ccc;
  padding-top: 0.5rem;
  padding-bottom: 1rem;
}
</style>
