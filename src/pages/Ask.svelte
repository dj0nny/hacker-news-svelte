<script>
import { onMount } from 'svelte';
import NewsList from '../components/NewsList.svelte';

let promise = getAsks();

async function getAsks() {
  const res = await fetch('https://api.hackernews.io/ask');
  const asksList = await res.json();
  return asksList;
}
</script>


{#await promise}
  <p>loading...</p>
{:then asksList}
  <NewsList list={asksList} />
{/await}