<script>
  import Timer from "./components/Timer.svelte";
  import Image from "./components/Image.svelte";
</script>

<h1>Hand Washing App</h1>
<div id="content">
  <Timer />
  <Image />
</div>

<style>
  h1 {
    width: fit-content;
    margin: 0 auto;
  }
  #content {
    display: flex;
    width: fit-content;
    flex-direction: column;
    margin: 0 auto;
  }
</style>
