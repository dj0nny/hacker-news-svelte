<script>
export let router = {}

let promise = getComments();

async function getComments() {
  const res = await fetch(`https://api.hackernews.io/item/${router.params.postId}`);
  const commentsList = await res.json();
  console.log(commentsList);
  return commentsList;
}
</script>

<style>
span.comment-meta {
  display: block;
  font-size: 8pt;
  color: #828282;
  margin-left: 10px;
}

.comment {
  margin-bottom: 20px;
  max-width: 1215px;
  overflow: auto;
  font-family: Verdana, Geneva, sans-serif;
  font-size: 9pt;
}

.comment-body {
  margin-left: 20px;
}

.nested {
  margin-left: 30px;
}

.nested .comment {
  margin-bottom: 0;
}
</style>

{#await promise}
  <p>loading...</p>
{:then commentsList}
<div class="comment">
  <span class="comment-meta">{ commentsList.user } { commentsList.time_ago }</span>
  <div class="comment-body">{commentsList.content}</div>
  <div class="nested">
    <!-- <Comment v-for="comment in data.comments" :key="comment.id" :data="comment" /> -->
  </div>
</div>
{/await}

