<script>
  import ProgressBar from "./ProgressBar.svelte";

  const washTime = 20;
  let timer;
  let progress = 0;
  let timerIsRunning = false;

  $: seconds = washTime;
  $: progress = (1 - seconds / washTime) * 100; //calculates progress procentage of time elapsed compared to the total washtime

  $: if (seconds < 0) {
    clearInterval(timer);
    resetValues();
  }

  function resetValues() {
    progress = 0;
    seconds = washTime;
    timerIsRunning = false;
  }

  function startTimer() {
    timer = setInterval(() => (seconds -= 1), 1000);
    timerIsRunning = true;
  }
</script>

<div id="timerWrapper">
  <h2>Seconds Left: {seconds}</h2>
  <ProgressBar {progress} />
  <button id="startButton" on:click={startTimer} disabled={timerIsRunning}
    >Start</button
  >
</div>

<style>
  #timerWrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 5px;
  }
  #startButton {
    width: 100px;
    height: 30px;
    border: none;
    background-color: crimson;
    border-radius: 5px;
  }
  button:hover {
    cursor: pointer;
  }
  #startButton:disabled {
    background-color: grey;
    cursor: default;
  }
</style>
