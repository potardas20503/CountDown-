<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CountDown Workshop</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Happy New Year : 2023</h1>
    <div id="countdown" class="countdown">
        <div class="time">
            <h2 id="days">00</h2>
            <small>Day</small>
        </div>
        <div class="time">
            <h2 id="hours">00</h2>
            <small>Hour</small>
        </div>
        <div class="time">
            <h2 id="minutes">00</h2>
            <small>Minute</small>
        </div>
        <div class="time">
            <h2 id="seconds">00</h2>
            <small>Second</small>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

###

@import url('https://fonts.googleapis.com/css2?family=Edu+AU+VIC+WA+NT+Hand:wght@400..700&display=swap');

*{
    font-family: "Edu AU VIC WA NT Hand", cursive;
    box-sizing: border-box;
}
body{
    background-image: url(https://img2.pic.in.th/pic/pexels-rakicevic-nenad-233369-769525.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    height: 100vh;
    display: flex;
    margin: 0;
    color: #fff;
    overflow: hidden;
    flex-direction: column;
    text-align: center;
    align-items: center;
    justify-content: center;
}
body::after{
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
}
body *{
    z-index: 1;
}
h1{
    font-size: 40px;
    margin: -80px 0 40px;
}

    .countdown{
        display: flex;
        transform: scale(2);
    }
    .time{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 15px;
    }
    .time h2{
        margin: 0 0 5px;
    }
    @media(max-width: 500px){
        h1{
            font-size: 35px;
        }
        .time{
            margin: 5px;
        }
        .time h2{
            font-size: 12px;
            margin: 0;
        }
        .time small{
            font-size: 10px;
        }
    }

    ###

    const day=document.getElementById('days');
const hour=document.getElementById('hours');
const minute=document.getElementById('minutes');
const second=document.getElementById('seconds');

const currentYear=new Date().getFullYear();
const newYearTime=new Date(`January 01, ${currentYear+1} 00:00:00`);

function updateCountDown() {
    const currentTime=new Date();
    const diff=newYearTime-currentTime;
    console.log(diff);
    const d=Math.floor(diff/1000/60/60/24);
    console.log(d);
    const h=Math.floor(diff/1000/60/60)%24;
    console.log(h);
    const m=Math.floor(diff/1000/60)%60;
    console.log(m);
    const s=Math.floor(diff/1000)%60;
    console.log(s);

    day.innerHTML=d;
    hour.innerHTML=h;
    minute.innerHTML=m;
    second.innerHTML=s;
}

setInterval(updateCountDown,1000);
