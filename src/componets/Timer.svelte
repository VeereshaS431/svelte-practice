<script>
    let milisec=0
    let sec=0
    let min=0
    let hr=0

    let timer
    function start(){
        timer=setInterval(()=>{
            milisec+=1
            if(milisec==100){
                sec+=1
                milisec=0
            }
            if(sec==60){
                min+=1
                sec=0
            }
            if(hr==60){
                hr+=1
                min=0
            }
        },10)
    }

    function stop(){
        clearInterval(timer)
    }

    function reset(){
        clearInterval(timer)
        milisec=0
        sec=0
        min=0
        hr=0
    }
    
</script>

<div class="main">
    <h1>STOP WATCH</h1>
<div class="container">
   <div class="box"><span class="time">{hr<10?`0${hr}`:{hr}}</span> <span class="units">hr</span></div>
   <div class="box"><span class="time">{min<10?`0${min}`:{min}}</span> <span class="units">min</span></div>
   <div class="box"><span class="time">{sec<10?`0${sec}`:`${sec}`} </span><span class="units">sec</span></div>
   <div class="box"><span class="time">{milisec<10?`0${milisec}`:`${milisec}`}</span> <span class="units">ms</span></div>
</div>
<!-- <h1>{hr} : {min} : {sec} : {milisec}</h1> -->
 <div class="btns">
    <button on:click={start}>start</button>
    <button on:click={stop}>stop</button>
    <button on:click={reset}>reset</button>
 </div>
</div>

<style>
    .main{
        display: flex;
        width: 600px;
        height: 400px;
        background-color: #34acf2;
        flex-direction: column;
        /* justify-content: center; */
        align-items:center;
        row-gap: 50px;
        border-radius: 20px;
        padding: 30px;
    }
    .container{
        display: flex;
        column-gap: 20px;
    }
    .box{
        font-size: 35px;
        border: 2px solid white;
        border-radius: 10px;
        padding: 10px;
        width: 100px;
        height: 50px;
    }
    .btns{
        display: flex;
        column-gap: 30px;
    }
    button{
        width: 100px;
    }
    button:active{
        background-color: white;
        color: black;
    }
.time{
    position: absolute;
    margin-left: -40px;
}
.units{
    font-size: 20px;
    position: absolute;
    margin-top: 20px;
    margin-left: 5px;
   
}
</style>