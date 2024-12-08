
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown Timer</title>
    <style>
        #timer {
            font-size: 2em;
            margin: 20px;
        }
    </style>
</head>
<body>
    <div id="timer">10:00</div>
    <button onclick="startTimer()">Start Timer</button>

    <script>
        function startTimer() {
            let timerElement = document.getElementById('timer');
            let time = 600; // time in seconds (e.g., 600 seconds = 10 minutes)

            let interval = setInterval(function() {
                let minutes = Math.floor(time / 60);
                let seconds = time % 60;

                seconds = seconds < 10 ? '0' + seconds : seconds;
                timerElement.textContent = `${minutes}:${seconds}`;

                if (time <= 0) {
                    clearInterval(interval);
                    alert('Time’s up!');
                } else {
                    time--;
                }
            }, 1000);
        }
    </script>
</body>
</html>
