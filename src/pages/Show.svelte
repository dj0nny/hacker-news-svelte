<script>
import { onMount } from 'svelte';
import NewsList from '../components/NewsList.svelte';

let promise = getShows();

async function getShows() {
  const res = await fetch('https://api.hackernews.io/show');
  const showsList = await res.json();
  return showsList;
}
</script>


{#await promise}
  <p>loading...</p>
{:then showsList}
  <NewsList list={showsList} />
{/await}