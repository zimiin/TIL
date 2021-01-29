# 안드로이드 개발 새로운 개념들
### Package Name

안드로이드 스튜디오에서 처음 프로젝트를 만들 때 package name을 설정하게 되는데, 이는 내가 만든 앱을 다른 앱과 구분해준다. 소문자로 시작해야 한다.

### Design Surface

xml 파일을 열면 select design surface 아이콘을 볼 수 있다. 이 아이콘을 클릭해서 선택할 수 있는 옵션은 design과 blue print가 있다. Design은 내가 직접 보는 화면과 같고, blue print는 각 요소들이 배치된 상태를 보여준다. Blue print로는 요소들이 겹쳐 있어도 보기 편하다.

### onCreate()

[MainActivity.java](http://mainactivity.java)의 시작점 역할이다.

### setContentView()

화면에 보여줄 것을 설정해준다. 

ex) setContentView(R.layout.activity_main); 
R.layout.activity_main에서 얻는 화면 구성 요소 정보로 현재 화면을 설정한다. R.layout.activity_main이 app/res/layout/activity_main.xml과 같다.

### Intent

내가 하고자 하는 행위를 의미한다. Intent를 사용해서 안드로이드 플랫폼에 내가 어떤 일을 하고자 하는지 알려줄 수 있다. 

ex) Intent myIntent = new Intent(Intent.ACTION_VIEW, Uri.parse("[http://m.naver.com](http://m.naver.com/)"));
startActivity(myIntent);
Intent 객체를 생성해 줄 때 네이버 주소를 넣어주었다. 이 경우에는 안드로이드에게 내가 네이버 페이지를 열고 싶다는 상태를 전달하게 되고, 안드로이드는 웹 브라우저에서 페이지를 띄워준다.

Uri.parse("tel:123-1234-1234") 가 되면 해당하는 전화번호로 바로 전화걸 수 있게끔 전화 화면을 띄워준다.

### 클릭 이벤트

안드로이드에서는 버튼을 누르는 것을 클릭 이벤트로 인식한다.

xml 파일 버튼 요소의 onClick 속성 값에 함수를 지정해주면, 버튼이 클릭되었을 때 해당하는 함수가 실행된다.

### Toast

간단한 메시지를 잠깐 보여준다.

### 요소를 추가했을 때 하얀 동그라미

하얀 동그라미는 constraint가 만들어지지 않은 상태로, 해당 요소의 위치가 설정되지 않은 것이다. 해당 요소의 동그라미를 다른 요소의 테두리나 화면 경계에 가지고 가면 상대적으로 요소의 위치가 결정되고, 동그라미는 파랗게 변한다.
