<script>
import NewsItem from '../components/NewsItem.svelte';
import Comments from '../components/Comments.svelte';

export let router = {}

let promise = getPostDetails();

async function getPostDetails() {
  const res = await fetch(`https://api.hackernews.io/item/${router.params.postId}`);
  const postDetail = await res.json();
  console.log(postDetail);
  return postDetail;
}
</script>

{#await promise}
  <h3>Loading...</h3>
{:then postDetail}
  <NewsItem news={postDetail} />
  {#each postDetail.comments as comment}
    <Comments data={comment} />
  {/each}
{/await}