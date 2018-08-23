# hello-world-riita
just another responsibility

<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>入試まであと何日</title>
</head>
<style>
    article{
        padding: 0;
        margin:0 auto;
        width:980px;
    }
    section{
        position: relative;
    }
    .headline{
        top: 30%;
        left:30%;
        position: absolute;
        transform: translate(-50%,-50%);
        margin:0;
        padding:0;
        color: rgba(255, 255, 255, 0.74);
        font-size: 55px;
        font-family: arial, sans-serif;
    }
    #the_time{
        width:100%;
        text-align: center;
        top:62%;
        left: 50%;
        font-size:90px;
        /* text-shadow: 10px 10px 0 rgba(66, 255, 255, 0.2); */
        position: absolute;
        transform: translate(-50%,-50%);
        margin:0;
        padding:0;
        color: rgba(255, 255, 255, 0.74);
        font-family: arial, sans-serif;
    }

</style>
<script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>
<script>
    $(document).ready(function(){
        indication();
        setInterval(indication,1000);
    });
    function indication(){
        var Day1 = new Date();
        var Day2 = new Date("2019/02/25 09:30:00");
        var day1 = Day1.getTime();
        var day2 = Day2.getTime();
        var day_gap = day2 - day1;
        var term_day = Math.floor(day_gap / 86400000);
        day_gap -= term_day*86400000;
        var term_hour = Math.floor(day_gap/3600000);
        day_gap -= term_hour*3600000;
        var term_minute = Math.floor(day_gap/60000);
        day_gap -= term_minute*60000;
        var term_second = Math.floor(day_gap/1000);
        var screen = '';
        if (day_gap>=0){
            if(term_day>0){
                screen += term_day+'日';
            }
            if(term_hour>0){
                screen += term_hour+'時間';
            }
            if(term_minute>0){
                screen += term_minute+'分';
            }
            if(term_second>0){
                screen += term_second+'秒';
            }
        }
        else{
                $('.headline').html = ''
                screen='試験当日です。頑張ってください。'
        }
        $('#the_time').html(screen);
    }
</script>
<body>
   <article>
       <section>
            <img src="images/tsubame2.jpg">
           <div class=flame>
               <p class=headline>入試開始まで</p>
               <strong id=the_time></strong>
           </div>
       </section>
   </article>

</body>

</html>
