<script>
import Comments from './Comments.svelte';
export let data;
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

<div class="comment">
  <span class="comment-meta">{ data.user } { data.time_ago }</span>
  <div class="comment-body">{@html data.content }</div>
  <div class="nested">
    {#each data.comments as comment}
      <Comments data={comment} />
    {/each}
  </div>
</div>
