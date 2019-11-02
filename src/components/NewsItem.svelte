<script>
import { Link } from 'svero'; 

export let news;
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

<div class="detail">
  <div class="news-detail">
    <div class="news-item">
      <a href={news.url} target="_blank" class="title">{ news.title }</a>
      <span class="domain">({ news.domain })</span>
      <div class="subtext">
        { news.points } points by { news.user } { news.time_ago } | <Link class="comment-link" href="/item/{news.id}"> { news.comments_count } comments </Link> 
      </div>
    </div>
  </div>
</div>