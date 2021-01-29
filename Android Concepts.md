# 안드로이드 개발 새로운 개념들
출처: Do it! 안드로이드 앱 프로그래밍 (이지퍼블리싱 | 정재곤 지음 | 2020년 1월 23일 출간)
</br>
### Package Name

안드로이드 스튜디오에서 처음 프로젝트를 만들 때 package name을 설정하게 되는데, 이는 내가 만든 앱을 다른 앱과 구분해준다. 소문자로 시작해야 한다.
내가 만든 앱을 다른 앱과 구분해주는 것이기 때문에 어떤 앱과도 패키지 이름이 중복되면 안된다. 그래서 중복되지 않는 인터넷 주소 형태로 많이 사용된다.
</br></br>
### Design Surface

xml 파일을 열면 select design surface 아이콘을 볼 수 있다. 이 아이콘을 클릭해서 선택할 수 있는 옵션은 design과 blue print가 있다. Design은 내가 직접 보는 화면과 같고, blue print는 각 요소들이 배치된 상태를 보여준다. Blue print로는 요소들이 겹쳐 있어도 보기 편하다.
</br></br>
### onCreate()

[MainActivity.java](http://mainactivity.java)의 시작점 역할이다.
</br></br>
### setContentView()

화면에 보여줄 것을 설정해준다. 

ex) setContentView(R.layout.activity_main); 
R.layout.activity_main에서 얻는 화면 구성 요소 정보로 현재 화면을 설정한다. R.layout.activity_main이 app/res/layout/activity_main.xml과 같다.
</br></br>
### Intent

내가 하고자 하는 행위를 의미한다. Intent를 사용해서 안드로이드 플랫폼에 내가 어떤 일을 하고자 하는지 알려줄 수 있다. 

ex) Intent myIntent = new Intent(Intent.ACTION_VIEW, Uri.parse("[http://m.naver.com](http://m.naver.com/)"));
startActivity(myIntent);
Intent 객체를 생성해 줄 때 네이버 주소를 넣어주었다. 이 경우에는 안드로이드에게 내가 네이버 페이지를 열고 싶다는 상태를 전달하게 되고, 안드로이드는 웹 브라우저에서 페이지를 띄워준다.

Uri.parse("tel:123-1234-1234") 가 되면 해당하는 전화번호로 바로 전화걸 수 있게끔 전화 화면을 띄워준다.
</br></br>
### 클릭 이벤트

안드로이드에서는 버튼을 누르는 것을 클릭 이벤트로 인식한다.

xml 파일 버튼 요소의 onClick 속성 값에 함수를 지정해주면, 버튼이 클릭되었을 때 해당하는 함수가 실행된다.
</br></br>
### Toast

간단한 메시지를 잠깐 보여준다.
</br></br>
### 요소를 추가했을 때 하얀 동그라미

하얀 동그라미는 constraint가 만들어지지 않은 상태로, 해당 요소의 위치가 설정되지 않은 것이다. 해당 요소의 동그라미를 다른 요소의 테두리나 화면 경계에 가지고 가면 상대적으로 요소의 위치가 결정되고, 동그라미는 파랗게 변한다. Constraint란 뷰가 레이아웃 안의 다른 요소와 어떻게 연결되는지 알려준다. 뷰의 연결점(Anchor Point)와 대상(Target)을 연결한다.</br>
뷰는 크기 속성 또한 반드시 가지고 있어야 한다. layout_width, layout_height 속성으로 뷰의 폭과 높이를 설정해 줄 수 있다. 크기가 지정되지 않으면 오류를 출력한다.
</br></br>
### Sync Project with Gradle Files

Gradle이 새로 프로젝트를 빌드하면서 변경된 파일의 내용을 모두 반영한다.
</br></br>
### 뷰 (View)

컨트롤이나 위젯으로 불리는 UI 구성 요소. 
뷰를 여러 개 포함하고 있는 것을 뷰그룹(ViewGroup)이라 한다. 뷰그룹 내에서 뷰의 위치를 지정할 수 있다. 어떤 뷰그룹을 다른 뷰그룹 안에 넣고 뷰와 동일하게 다룰 수도 있다.
</br></br>
### 위젯 / 레이아웃

뷰 중에서 일반적인 컨트롤 역할을 하는 것을 위젯(Widget)이라고 한다. 뷰그룹 중에서 내부에 뷰들을 포함하고 있으면서 그것들을 배치하는 역할을 하는 것을 레이아웃(Layout)이라고 한다. 
</br></br>
### 태그

<태그명 /> 처럼 하나의 태그로 사용 가능하고,

<태그명
    속성1="속성값1"
    속성2="속성값2" >

</ 태그명>
위처럼 시작, 끝 태그로 나누어 사용도 가능하다.
</br></br>
### 태그명 입력 방법

위젯이나 레이아웃이 안드로이드 기본 API에 포함되어 있다면 그 위젯이나 레이아웃의 이름만 입력한다. 만약 기본 API에 포함된 것이 아니라 외부 라이브러리에서 불러온 것이라면 패키지 이름까지 같이 입력한다. 

ex) androidx.constraintlayout.widget.ConstraintLayout
ConstraintLayout은 안드로이드 SDK에 나중에 추가되면서 외부 라이브러리로 분류되어있다. 
</br></br>
### xmlns

```jsx
xmlns:android="[http://schemas.android.com/apk/res/android](http://schemas.android.com/apk/res/android)"
xmlns:app="[http://schemas.android.com/apk/res-auto](http://schemas.android.com/apk/res-auto)"
xmlns:tools="[http://schemas.android.com/tools](http://schemas.android.com/tools)"
```

이러한 속성들은 이후 속성에서 아래처럼 사용할 때

```
android:orientation="vertical"
app:layout_constraintGuide_begin="27dp"
```

orientation, layout_constraintGuide_begin 속성이 어디에 위치한 속성인지 지정해준다.

tools 속성은 앱이 실행될 때는 적용되지 않고, 안드로이드 스튜디오에서만 적용된다.
</br></br>
### Constraint 레이아웃에서 속성 이름 규칙

layout_constraint[소스 뷰의 연결점]_[타깃 뷰의 연결점]="[타깃 뷰의 id]"

ex) app:layout_constraintStart_toStartOf="@+id/guideline"
소스 뷰의 start를 타깃 뷰 guideline의 start로 연결한다는 의미다.

start는 left와, end는 right와 같다.
</br></br>
### 크기 표시 단위

dp / dip : Density Independent Pixel. 화면 크기에 따라 크기가 같은 비율로 조정된다.

sp / sip : Scale Independent Pixel. 글꼴 설정에 따라 글자 크기가 바뀐다.

em : 글꼴과 상관 없이 동일한 텍스트 크기를 갖는다.
</br></br>
### Minimum SDK

어느 OS 버전의 단말까지 지원할 것인지에 대한 설정이다.
