<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Угадайка</title>
	<link rel="stylesheet" href="styles.css">
	<script type="text/javascript">

		var answer = parseInt(Math.random() * 100);
		var tryCount = 0;
		var maxTryCount = 5;

    function readInt(){
      var number = document.getElementById("userAnswer").value;
      return parseInt(number);
    }

    function hide(id){
    	document.getElementById(id).style.display = "none";
    }
	
	function write(text){
		document.getElementById("info").innerHTML = text;
	}
 
    function guess(){
  tryCount++;
  
      var userAnswer = readInt();
      if (userAnswer == answer){
      	write("<b>Поздравляю, вы угадали!</b>")
      	hide("button");
      	hide("userAnswer");
      } else if(tryCount >= tryCount){
         write("Вы проиграли<br>Правильный ответ: " + answer);
         hide("button");
      	 hide("userAnswer");
      } else if (userAnswer > answer){
      	write("Вы ввели слишком большое число<br>Попробуйте ещё раз. Введите число от 1 до 100");
      } else if (userAnswer < answer){
      	write("Вы ввели слишком маленькое число<br>Попробуйте ещё раз. Введите число от 1 до 100");
      }
    }


</script>
</head>
<body>

	<div class="content">
<div class="header">
	<a href="rubber.html">Главная</a>
	<a href="puzzle.html">Угадайка</a>
	<a href="Angl.html">Английский</a>
</div>

<div class="contentWrap">
  <div class="content">
    <div class="center">

     <h1>Игра в угадайка</h1>

     <div class="box">

       <p id="info">Угадайте число от 0 до 100</p>
       <input type="text" id="userAnswer">
       <br>
       <a href="#" onClick="guess();" id="button">Начать</a>
      </div>

     </div>
  </div>
</div>

<div class="footer">
   Copyringt &copy; Kirill Levochkin
</div>

</body>
</html>

