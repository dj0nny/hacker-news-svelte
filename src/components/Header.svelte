<script>
import { Link } from 'svero';

</script>

<div class="header">
  <div class="logo">
    <img src="https://news.ycombinator.com/y18.gif" alt="">
  </div>
  <div class="title">
    <strong>Hacker News</strong>
  </div>
  <ul class="menu">
    <li class="menu-item"><Link href="/news">news</Link></li> |
    <li class="menu-item"><Link href="/newest">newest</Link></li> |
    <li class="menu-item"><Link href="/">show</Link></li> |
    <li class="menu-item"><Link href="/">ask</Link></li> |
    <li class="menu-item"><Link href="/">jobs</Link></li>
  </ul>
</div>

<style>
.header {
  background: rgb(255, 102, 0);
  padding: 3px;
  font-size: 10pt;
  display: flex;
}

.logo img {
  outline: 1px solid #fff;
}

.title {
  margin-left: 5px;
}

ul.menu {
  margin: 0;
  padding: 0;
  list-style-type: none;
  margin-left: 15px;
}

ul.menu li.menu-item {
  display: inline-block;
} 

:global(.header a) {
  color: #000;  
}
</style>