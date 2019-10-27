<script>
export let list;
</script>

<style>
.news-item {
  margin-bottom: 5px;
  padding: 5px;
}

.news-item::before {
  counter-increment: news;
  content: counter(news) ". ";
  font-size: 11px;
}

a.title {
  color: #000;
  text-decoration: none;
  font-size: 13px;
}

.comment-link {
  text-decoration: none;
  color: #000
}

.comment-link:hover {
  text-decoration: underline;
}

span.domain {
  font-size: 8pt;
  color: #828282;
  margin-left: 10px;
}

div.subtext {
  font-size: 7pt;
  color: #828282;
}
</style>

{#each list as item}
  <div class="news-item">
    <a href={item.url} target="_blank" class="title">{ item.title }</a>
    <span class="domain">({ item.domain })</span>
    <div class="subtext">
      { item.points } points by { item.user } { item.time_ago } | { item.comments_count } comments
    </div>
  </div>
{/each}
