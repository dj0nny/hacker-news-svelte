<script>
import { onMount } from 'svelte';
import NewsList from '../components/NewsList.svelte';

let promise = getNews();

async function getNews() {
  const res = await fetch('https://api.hackernews.io/news');
  const newsList = await res.json();
  return newsList;
}
</script>

{#await promise}
  <p>loading...</p>
{:then newsList}
  <NewsList list={newsList} />
{/await}