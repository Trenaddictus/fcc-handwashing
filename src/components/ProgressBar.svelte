<script>
  export let progress = 0;
</script>

<div id="progressBar">
  <div id="progression" style="width:{progress}%;" />
</div>

<style>
  #progressBar {
    width: 100%;
    height: 30px;
    box-sizing: border-box;
    border: 2px solid black;
    margin-bottom: 5px;
    padding: 0;
  }
  #progression {
    background-color: green;
    height: 100%;
    padding: 0;
  }
</style>
