<script>
import NewsItem from './NewsItem.svelte';

export let list;
</script>

{#each list as item}
  <NewsItem news={item} />
{/each}
