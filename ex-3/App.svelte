<script>
  import MyLink from "./MyLink.svelte";
  let link = {
    href: "http://www.mysite.com",
    title: "My Site",
    link: "#",
    color: "#ff3300"
  };
</script>

<MyLink {...link} />
