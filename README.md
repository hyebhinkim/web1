<!doctype html>
<html lang="en">

<head>
    <link rel="stylesheet" href="index.css">

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>집을자바</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link href="https://fonts.googleapis.com/css?family=Do+Hyeon&display=swap&subset=korean" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Sunflower:300&display=swap&subset=korean" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Noto+Sans+KR&display=swap" rel="stylesheet">
	
    <style>
        .nav-link{font-family: 'Do Hyeon', sans-serif;}
     .navbar-brand{font-family: 'Do Hyeon', sans-serif;}
     .container
     {

       background-color:  white;
       margin-top: 15px;



     }
body {
  font-family: Arial, sans-serif;
 <!-- background: url(http://www.shukatsu-note.com/wp-content/uploads/2014/12/computer-564136_1280.jpg) no-repeat;-->
  background-size: cover;
  height: 100vh;
}

h1 {
  text-align: center;
  font-family: Tahoma, Arial, sans-serif;
  color: #06D85F;
  margin: 80px 0;
}

.box {
  width: 1;
 <!-- margin: 0 auto;-->
 <!-- background: rgba(255,255,255,0.2);-->
  padding: 35px;
  <!--border: 2px solid #fff;-->
  <!--border-radius: 20px/50px;-->
  background-clip: padding-box;
  <!--text-align: center;-->
}

.button {
  font-size: 1em;
  padding: 10px;
  color: black;
  <!--border: 2px solid #06D85F;
  border-radius: 20px/50px;-->
  text-decoration: none;
  cursor: pointer;
  transition: all 0.3s ease-out;
}
.button:hover {
 <!-- background: #06D85F;-->
}

.overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.7);
  transition: opacity 500ms;
  visibility: hidden;
  opacity: 0;
}
.overlay:target {
  visibility: visible;
  opacity: 1;
}

.popup {
  margin: 70px auto;
  padding: 20px;
  background: #fff;
  border-radius: 5px;
  width: 40%;
  position: relative;
  transition: all 5s ease-in-out;
}

.popup h2 {
  margin-top: 0;
  color: #333;
  font-family: Tahoma, Arial, sans-serif;
}
.popup .close {
  position: absolute;
  top: 20px;
  right: 30px;
  transition: all 200ms;
  font-size: 30px;
  font-weight: bold;
  text-decoration: none;
  color: #333;
}
.popup .close:hover {
  color: #ffcc00
}
.popup .content {
  max-height: 30%;
  overflow: auto;
}

@media screen and (max-width: 700px){
  .box{
    width: 70%;
  }
  .popup{
    width: 70%;
  }
}
.popup > .popup-header > h2,.popup > .popup-header > p{display:inline-block;}
.btn {z-index:0 !important;}
.popup-body {border:1px solid black;border-radius: 5px;padding:20px;}
.popup-body > div.content p {margin:0;}
.popup-body > div.content {display:flex;flex:1}
.popup-body > div.content .content-left p{width:50px}
.popup-body > div.content .content-left {flex:1}
.popup-body > div.content .content-right {margin-left:10px;}




.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; }
 .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }
 </style>
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
    
	<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBRxlb4rhy3YKZIs80Ikjqs0OiiN3lQFc4"></script> 
    <script>
        function popup(url, w, h, name, option) {
        var pozX, pozY;
        var sw = screen.availWidth;
        var sh = screen.availHeight;
        var scroll = 0;
        if (option == 'scroll') {
          scroll = 1;
        }
        pozX = (sw - w) / 2;
        pozY = (sh - h) / 2;
        window.open(url, name, "location=0,status=0,scrollbars=" + scroll + ",resizable=1,width=" + w + ",height=" + h + 
                    ",left=" + pozX + ",top=" + pozY);
   }
  
//여기는 전세월세 바뀌면 실행되는 이벤트
function changeType(){
      console.log($("#TYPE option:selected").val());
   }
   
   
function numberWithCommas(x) {

    //var str = x.slice(0, -1);
    var money = x.value;
    console.log(money.toLocaleString());

    var deleteComma = x.value.replace(/\,/g, "");

    x.value= inputNumberWithComma(inputNumberRemoveComma(x.value));

 // var i = x.value.replace(/[^0-9]/g,'');   // 입력값이 숫자가 아니면 공백
  //j = i.replace(/,/g,'');        // ,값 공백처리
  //x.value = j.replace(/\B(?=(\d{3})+(?!\d))/g, ",") + "원";
}

function inputNumberWithComma(str){
    str = String(str);
    return str.replace(/(\d)(?=(?:\d{3})+(?!\d))/g, "$1,");
}

function inputNumberRemoveComma(str){
    str = String(str);
    return str.replace(/[^\d]+/g, "");
}

function initialize() { 

var myLatlng = new google.maps.LatLng(35.156765, 128.105978); // 좌표값

  var mapOptions = { 

        zoom: 14, // 지도 확대레벨 조정

        center: myLatlng, 

        mapTypeId: google.maps.MapTypeId.ROADMAP 

  } 

  var map = new google.maps.Map(document.getElementById('map_canvas'), mapOptions); 

  var marker = new google.maps.Marker({ 

position: myLatlng, 

map: map, 

title: "평화원룸" // 마커에 마우스를 올렸을때 간략하게 표기될 설명글

}); 

  } 

window.onload = initialize;
     
</script>



   
   
</head>


<body>



    <!--  <div class="container">
   <div style=" margin-left:50px;"> -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <a class="navbar-brand" href="#">HOME</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item">
                    <a class="nav-link" href="#">ABOUT</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">CONTACT 070-234-2284</a>
                </li>
            </ul>
        </div>
    </nav>
    <!-- <section style="position:absoulute; margin-top:1000px; color:#FFBF00">
  Section
  
</section> -->
<div style="background-color:#ffcc00; height:350px;">
    <div class="row" style="">
        <div style="position:relative; width:100%;" class="col">
            <img style="position:absolute ; left: 490px; top: 0px; width:25%; height:385px;" src="C:\Users\Elodie\Desktop\동고비\여자.png" alt="">
        </div>
    </div>
    <div class="row">
        <div class="col-8" style="position:relative;width:100%;">
           <h4 style="position:absolute; margin-top:80px; margin-left:40px; font-family: 'Do Hyeon', sans-serif; font-size:70px; color:white"><em>#진주시</em></h4>
            <h4 style="position:absolute; margin-top:80px; margin-left:290px; font-family: 'Do Hyeon', sans-serif; font-size:70px; color:white"><em>#원룸</em> <br><em> 구할 때</br></em></h4>
            <!--<h4 style="position:absolute; margin-top:200px; margin-left:180px;">TEXT HERE</h4>-->
        </div>
        <div class="col-4" style="position:relative;width:100%;">
           <h4 style="position:absolute; margin-top:60px; margin-left:-10px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white">·</h4>
            <h4 style="position:absolute; margin-top:130px; margin-left:-50px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white"><em>집</em></h4>
            <h4 style="position:absolute; margin-top:45px; margin-left:95px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white">·</h4>
            <h4 style="position:absolute; margin-top:110px; margin-left:50px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white"><em>을</em></h4>
            <h4 style="position:absolute; margin-top:60px; margin-left:190px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white">·</h4>
            <h4 style="position:absolute; margin-top:130px; margin-left:150px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white"><em>자</em></h4>
            <h4 style="position:absolute; margin-top:45px; margin-left:290px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white">·</h4>
            <h4 style="position:absolute; margin-top:110px; margin-left:250px;font-family: 'Do Hyeon', sans-serif; font-size:100px; color:white"><em>바</em></h4>
            <!-- <h4 style="position:absolute; margin-top:170px; margin-left:30px;">TEXT HERE</h4>-->
        </div>
    </div>
</div>
    <div class="row" style="">
        <div class="col-3 rounded-left" style="background-color:rgba(0,0,0,0.2)"></div>
        <div class="col-6" style="background-color:rgba(0, 0, 0,0.2)">

            <div class="card-body">
                <form class="" action="" method="post">
                    <div class="input-group mb-3">
                        <input type="text" class="form-control" aria-label="Sizing example input" placeholder="검색어를 입력하세요.." aria-describedby="inputGroup-sizing-default">
                        <div class="input-group-prepend">
                            <button type="button" class="btn btn-secondary rounded">Search</button>
                        </div>
                    </div>
                </form>
                <p><a class="" data-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample  " style="text-decoration:none">검색옵션</a></p>

                <div class="collapse" id="collapseExample">

                    <div class="d-flex bd-highlight">

                        <div class="p-0 bd-highlight" style="float:left;">
                    <div>
                            <select id="TYPE" name="TYPE" onChange="changeType();" class="form-control" style="width:200px; float:left; margin-left:24px;margin-right:38px;">
         <option value="0">타입</option>
                                <option value="1">월세</option>
                                <option value="2">전세</option>
                                <option value="3">반전세</option>
                            </select>
                                <select id="sturcture" name="sturcture" onChange="changeSturcture();" class="form-control" style="width:200px;">
                                    <option value="0">구조</option>
                                    <option value="1">분리형</option>
                                    <option value="2">원룸형</option>
                                    <option value="3">투룸형</option>
                                </select>
</div><br>


                            
                            <div class="p-0 bd-highlight">
                                <div class="custom-control">
                                    <label for="Name" style="margin-right:10px; font-family: 'Noto Sans KR', sans-serif;">전세/보증금</label>
                                    <input type="text"  class="form-control" aria-label="Sizing example input" 
                                            placeholder=" 원 이상" aria-describedby="inputGroup-sizing-default" id="customCheck2" style="width:157px;text-align:right;display:inline-block;" onKeyup="numberWithCommas(this);" onChange="numberWithCommas(this);"><!--<span>이상</span>-->
                                    <span>&nbsp;~&nbsp;</span>
                                    <input type="text" class="form-control" aria-label="Sizing example input" placeholder=" 원 이하" 
                                            aria-describedby="inputGroup-sizing-default" id="customCheck3" style="width:157px;text-align:right;display:inline-block;" onkeyup="numberWithCommas(this);" onChange="numberWithCommas(this);"><!--<span>이하</span>-->
                                </div>
                            </div><br>
         
                            
                            <div class="p-0 bd-highlight">
                                <div class="custom-control">
                                    <label for="Name" style="margin-right:60px; font-family: 'Noto Sans KR', sans-serif;">월세</label>
                                    <input type="text" class="form-control" aria-label="Sizing example input" placeholder=" 원 이상" aria-describedby="inputGroup-sizing-default" id="customCheck4" style="width:157px;text-align:right;display:inline-block;" onKeyup="numberWithCommas(this);" onChange="numberWithCommas(this);"><!--<span>이상</span>-->
                                    <span>&nbsp;~&nbsp;</span>
                                    <input type="text" class="form-control" aria-label="Sizing example input" placeholder=" 원 이하" aria-describedby="inputGroup-sizing-default" id="customCheck4" style="width:157px;text-align:right;display:inline-block" onKeyup="numberWithCommas(this);" onChange="numberWithCommas(this);"><!--<span>이상</span>-->
                                </div>
                            </div>
                        </div>
                    </div>

                  

                </div>
            </div>
        </div>
        <div class="col-3 rounded-right" style="background-color:rgba(0, 0, 0,0.2)"></div>
    </div>

    <div class="row" style="margin-top:15px;">
        <div class="col-1"></div>
        <div class="col-10">
            <table class="table table-striped">
                <thead>
                    <tr>
                        <th scope="col">#</th>
                        <th scope="col">원룸명</th>
                        <th scope="col">&emsp;&emsp;&emsp;&emsp;주소</th>
                        <th scope="col">전화</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <th scope="row">1</th>
                        <td>평화원룸</td>
                        <td>
                          <!--  <a href="file:///C:/Users/Elodie/Desktop/TEST/%EA%B5%AC%EA%B8%80%EB%A7%B5.html" style="text-decoration:none" onclick="popup(this.href,400,500,'팝업1','scroll'); return false;">
                                진주시 가좌동 170-94</a></p>-->

<div class="box">
   <a class="button" href="#popup1">진주시 가좌동 170-94</a>
</div>

<div id="popup1" class="overlay">
   <div class="popup">
       <div class="popup-header">
            <h2>평화원룸</h2>
            <p>( 진주시 가좌동 170-94 )</p>
			<div id="map_canvas"  class="embed-container"></div>

       </div>
      <div class="popup-body">
        <a class="close" href="#">&times;</a>
        <div class="content">
            <div class="content-left">
                <p>반전세</p>
                <p>옵션 : </p>
            </div>
            <div class="content-right">
                <p>3000/10 원룸</p>
                <p>에어컨 냉장고 세탁기 가스레인지 전자레인지 책상 침대 옷장 신발장 TV 엘리베이터 주차장</p>
            </div>
        </div>
      </div>
   </div>
</div>



                    
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">2</th>
                        <td>가좌빌</td>
                        <td>진주시 가좌동 450-25</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">3</th>
                        <td>해바라기빌 </td>
                        <td>진주시 가좌동 454-7</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">4</th>
                        <td>성공빌 </td>
                        <td>진주시 가좌동 369-5</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">5</th>
                        <td>노리터빌 </td>
                        <td>진주시 가좌동 1502-2</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">6</th>
                        <td>가좌그린빌 </td>
                        <td>진주시 가좌동 856-9</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">7</th>
                        <td>11번가 </td>
                        <td>진주시 가좌동 688-7</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">8</th>
                        <td>그레이스빌 </td>
                        <td>진주시 가좌동 101-3</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">9</th>
                        <td>행복원룸 </td>
                        <td>진주시 가좌동 1109</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">10</th>
                        <td>좋은인연빌 </td>
                        <td>진주시 가좌동 1459-7</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <th scope="row">11</th>
                        <td>하늘정원 </td>
                        <td>진주시 가좌동 488</td>
                        <td>-</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="col-1"></div>
    </div>

    </div>
    
</body>


</html>
