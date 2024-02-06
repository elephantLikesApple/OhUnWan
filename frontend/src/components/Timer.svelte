<script>
  let totalTime = 10 * 1000;
  let timer;

  function startTimer() {
    timer = setInterval(() => {
      totalTime -= 100;

      if (totalTime <= 0) {
        stopTimer();
        totalTime = 0;
      }
    }, 100);
  }

  function stopTimer() {
    clearInterval(timer);
  }

  function formatTime(totalMilliseconds) {
    let minutes = Math.floor(totalTime / (60 * 1000));
    let seconds = Math.floor((totalTime - (minutes * 60 * 1000)) / 1000);
    let milliseconds = Math.floor((totalTime - (minutes * 60 * 1000) - (seconds * 1000)) / 100);
    return `${minutes.toString().padStart(2, '0')} : ${seconds.toString().padStart(2, '0')} : ${milliseconds.toString().padStart(1, '0')}`;
  }

</script>

<h1>{formatTime(totalTime)}</h1>

<button on:click={startTimer}>타이머 시작</button>
<button on:click={stopTimer} >타이머 정지</button>

<hr>