<script>
  import { onMount, onDestroy } from 'svelte';

  let minute = 0;
  let seconds = 0;
  let milliseconds = 0;
  let prevTimeInMilliseconds = 0;
  let stopwatchRunning = false;
  let timer;
  let lapTimes = [];

  function startStopwatch() {
    if (stopwatchRunning) {
      return;
    }
    stopwatchRunning = true;
    timer = setInterval(() => {
      milliseconds += 1;
      if (milliseconds === 10) {
        milliseconds = 0;
        seconds++;
        if (seconds === 60) {
          seconds = 0;
          minute++;
        }
      }
    }, 100);
  }

  function stopStopwatch() {
    clearInterval(timer);
    stopwatchRunning = false;
  }

  function recordStopwatch() {
    let currentTimeInMilliseconds = (minute * 60 * 1000) + (seconds * 1000) + (milliseconds * 100);

    // 이전 랩타임과 현재 시간이 동일하면 함수를 종료
    if (currentTimeInMilliseconds === prevTimeInMilliseconds) {
      return;
    }

    let elapsedMilliseconds = currentTimeInMilliseconds - prevTimeInMilliseconds;
    let elapsedMinute = Math.floor(elapsedMilliseconds / (60 * 1000));
    let elapsedSeconds = Math.floor((elapsedMilliseconds - (elapsedMinute * 60 * 1000)) / 1000);
    let elapsedMilli = Math.floor((elapsedMilliseconds - (elapsedMinute * 60 * 1000) - (elapsedSeconds * 1000)) / 100);

    let currentLapTime = formatTime(minute, seconds, milliseconds);
    let elapsedLapTime = formatTime(elapsedMinute, elapsedSeconds, elapsedMilli);
    let lapTime = `${currentLapTime} ( ${elapsedLapTime} )`;
    lapTimes = [lapTime, ...lapTimes];
    prevTimeInMilliseconds = currentTimeInMilliseconds;
  }

  function formatTime(minutes, seconds, milliseconds) {
    return `${minutes.toString().padStart(2, '0')} : ${seconds.toString().padStart(2, '0')} : ${milliseconds.toString().padStart(1, '0')}`;
  }

  onDestroy(() => {
    stopStopwatch();
  });
</script>

<h1>{formatTime(minute, seconds, milliseconds)}</h1>

<button on:click={startStopwatch}>스톱워치 시작</button>
<button on:click={recordStopwatch}>스톱워치 기록</button>
<button on:click={stopStopwatch} >스톱워치 정지</button>

<hr>

{#if lapTimes.length > 0}
  <h3>랩타임</h3>
  <ul>
    {#each lapTimes as lapTime (lapTime)}
      <li>{lapTime}</li>
    {/each}
  </ul>
{/if}