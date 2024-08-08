### CORS란?
**Cross-Origin Resource Sharing** 으로, "교차 출처 리소스 공유 정책"

### SOP(Same Origin Policy)
``동일한 출처에 대한 정책으로, '동일한 출처에서만 리소스를 공유할 수 있다'는 법률
즉, 동일한 출처(Same-Origin) 서버에 있는 리소스는 자유로이 가져올 수 있지만, 다른 출처(Cross-Origin)서버에 있는 이미지나 유튜브 영상 같은 리소스는 상호작용이 불가능하다``

그렇다면 동일 출처가 아닌 경우 접근을 차단하는 이유는 뭘까? </br>
사실 출처가 다른 두 어플리케이션이 자유로이 소통할 수 있는 환경은 꽤 위험한 환경이다. </br>
만일 제약이 없다면, 해커가 CSRF(Cross-Site Request Forgery)나 XSS(Cross-Site Scripting) 등의 방법을
이용해서 우리가 만든 어플리케이션에서 해커가 심어놓은 코드가 실행하여 개인 정보를 가로챌 수 있다.
```
하지만 인터넷은 여러 사람들에게 오픈된 환경이고, 이런 환경에서 웹페이지에서
다른 출처에 있는 리소스를 가져와 사용하는 일은 매우 흔한 일이라 무턱대고 막을 수는 없는 일이다.
그래서 몇 가지 예외 조항을 두고 다른 출처의 리소스 요청이라도 이 조항에 해당할 경우에는 허용하기로 했는데,
그 중 하나가 바로 **CORS 정책을 지킨 리소스 요청**이다
```
그럼 어떻게 CORS 정책을 따르게 하여 SOP 정책을 회피할 수 있을까? </br>
이를 알기 위해선 브라우저의 CORS 동작 과정을 살펴 보아야 한다.

### CORS 동작 과정

CORS 코딩
예를 들면, jQuery는 Ajax 요청을 통해 http://api.example.com/api/data 엔드포인트에 GET 요청을 보내는데, 이 요청을 성공적으로 수행하려면, 서버에서 CORS를 설정해야 한다.
```html
<!DOCTYPE html>
<html>
<head>
    <title>JSP - Hello World</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
    <script>
        $(function(){
            console.log("ready...");
            let url2 = "http://localhost:8090/web07total_war_exploded/json_m_selectAll.do";
            $.ajax({
                url:url2, // <b> 서버의 CORS 허용이 필요한 주소 </b>
                type:"get",//get
                data:{},
                dataType:"json", //xml,html,text
                success:function(response){
                    console.log(response);//파싱된 결과 객체
                    let tag ='';

                    for (let i = 0; i < response.length; i++) {
                        tag += `<tr>
                                      <td><a href="ajax_selectOne.do?num=\${response[i].num}">\${response[i].num}</a></td>
                                      <td>\${response[i].id}</td>
                                      <td>\${response[i].pw}</td>
                                      <td>\${response[i].name}</td>
                                      <td>\${response[i].tel}</td>
                                  </tr>`;
                    }

                    $("#result").html(tag);
                },
                error:function(ex){
                    console.log(ex);
                }
            });


        });


    </script>

</head>
<body>
```
