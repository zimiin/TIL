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
### Toast (토스트)

간단한 메시지를 잠깐 보여준다. 토스트는 위치나 모양을 바꿀 수 있다. 토스트 대신 스낵바로 간단한 메시지를 보여줄 수도 있다.  
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
</br></br>
### Activity

하나의 화면을 부르는 말. 앱을 실행했을 때 처음 보이는 화면은 Main Activity라 한다.

[MainActivity.java](http://mainactivity.java)는 app/manifests/AndroidManifest.xml 에 자동으로 등록되어 있다. MainActivity.java 외의 다른 코드로 첫화면을 설정하고 싶을 때는 AndroidManifest.xml 파일에서 <activity android:name=".MainActivity.java" 부분을 원하는 코드로 변경한다.
</br></br>
### Gravity

layout_gravity : 뷰의 정렬 속성</br>
gravity : 뷰 내의 내용물 정렬 속성
</br></br>
### 공간 분할

뷰를 배치한 후 남아있는 공간을 분할할 때는 android:layout_weight 속성을 적절한 수로 설정한다. 남아있는 공간이 아닌 부모의 크기를 분할해서 각 뷰가 크기를 설정할 수 있게끔 하려면 가로나 세로 중 어떤 방향으로 나누느냐에 따라 android:layout_width 또는 android:layout_height 속성을 0dp로 설정한 후 layout_weight 속성을 설정해준다.
</br></br>
### Relative Layout (상대 레이아웃)

뷰의 위치를 결정할 때, 부모 컨테이너나 다른 뷰와의 상대적인 위치를 이용한다.

보통 화면 레이아웃을 만들 때는 relative layout과 linear layout을 함께 사용한다.
</br></br>
### 상대적 위치에 뷰를 배치하기 위한 속성들

layout_above : 지정한 뷰의 위쪽에 배치</br>
layout_below : 지정한 뷰의 아래쪽에 배치</br>
layout_alignTop : 지정한 뷰의 위쪽과 맞춤</br>
layout_alignBottom : 지정한 뷰의 아래쪽과 맞춤</br>
layout_alignLeft : 지정한 뷰의 왼쪽과 맞춤</br>
layout_alignRight : 지정한 뷰의 오른쪽과 맞춤</br>
layout_alignBaseline : 지정한 뷰와 내용물의 아래쪽 기준선(baseline)을 맞춤</br></br>

layout_alignParentTop : 부모 컨테이너의 위쪽과 뷰의 위쪽을 맞춤</br>
layout_alignParentBottom : 부모 컨테이너의 아래쪽과 뷰의 아래쪽을 맞춤</br>
layout_alignParentLeft : 부모 컨테이너의 왼쪽 끝과 뷰의 왼쪽 끝을 맞춤</br>
layout_alignParentRight : 부모 컨테이너의 오른쪽 끝과 뷰의 오른쪽 끝을 맞춤</br>
layout_centerHorizontal : 부모 컨테이너의 수평 방향 중앙에 배치</br>
layout_centerVertical : 부모 컨테이너의 수직 방향 중앙에 배치</br>
layout_centerInParent : 부모 컨테이너의 수평과 수직 방향 중앙에 배치</br>
</br></br>
### TableRow

TableRow의 height는 내부적으로 항상 wrap_content로 설정되어 있고, width는 항상 match_parent로 설정되어 있다. 둘 다 xml파일에서는 match_parent로 되어있지만 실제로는 그렇게 동작하지 않는다는 것이다.
</br></br>
### StretchColumns

테이블 레이아웃 내의 특정 열이 테이블의 가로를 꽉 채우도록 설정할 수 있다. 열의 인덱스는 0부터 시작한다.
</br></br>
### layout_span

테이블의 요소가 몇 개의 열을 차지할지 설정하는 속성이다.
</br></br>
### Frame Layout (프레임 레이아웃)

프레임 레이아웃에 뷰를 넣으면 그 중 하나의 뷰만 화면에 표시한다. 중첩(overlay) 특성을 갖고 있어서 여러 개의 뷰를 전환할 때 사용할 수 있다. Visibility(가기성) 속성을 사용해 특정 뷰를 보이거나 보이지 않게 할 수 있다.
</br></br>
### id 참조

XML 레이아웃 파일에서 id 지정 방법 : @+id/아이디</br>
자바 소스 코드에서 참조 방법 : R.id.아이디
</br></br>
### 버튼 위젯

텍스트뷰를 상속하여 정의되어 텍스트뷰의 속성을 그대로 가지고 있다. ex) text, textColor, textSize</br>
체크 박스, 라디오 버튼도 버튼의 속성을 가진다. 버튼과 차이점은 사용자가 설정한 상태 값을 저장하도록 정의되어 있다는 것이다.
</br></br>
### 에디트 텍스트 (EditText)

사용자에게 값을 입력받을 때 사용함. 입력하는 문자의 유형을 inputType으로 지정할 수 있다.</br>
xml파일 design 모드에서는 왼쪽 Palette의 Text 아래에서 고를 수 있다 (Plain Text, Password 등).
</br></br>
### 이미지 뷰 / 이미지 버튼

두 위젯 모두 이미지를 화면에 표시할 때 사용하는데, 이미지 버튼은 이미지를 버튼처럼 사용할 수 있다.
</br></br>
### 이미지 파일 지정 방식

1. 이미지 리소스 지정 방식</br>
drawable 폴더에 이미지를 둔 후 app:srcCompat="@drawable/파일명" 으로 지정한다. 파일명에 확장자는 제외한다.</br>
2. 이미지 파일을 소스 코드에서 직접 로딩하여 비트맵으로 만든 후 설정하는 방식.
</br></br>
### 해상도에 따른 이미지 로딩

drawable : 일반적으로 사용되는 이미지</br>
drawable-hdpi : 고해상도 화면</br>
drawable-mdpi : 중간 해상도 화면</br>
외에도 해상도에 따라 폴더를 만들어 사용하면 된다.
</br></br>
### Drawable

뷰에 설정할 수 있는 객체로, 그 위에 그래픽을 그릴 수 있다.
</br></br>
### 터치 이벤트 처리

뷰에 리스너를 등록해서 처리한다.
</br></br>
### 제스처 이벤트 처리

제스처 이벤트는 터치 이벤트 중에서 스크롤 등을 구별한 후 알려주는 이벤트이다. 제스처 이벤트를 처리하는 GestureDetector 객체에 터치 이벤트를 전달하면 각 제스처에 대한 함수를 호출한다.
</br></br>
### 키 이벤트 처리

onKeyDown() 메소드를 재정의하여 처리한다. onKeyDown()으로 전달되는 파라미터는 두 개이며, KeyCode는 어떤 키가 사용되는지 구별할 때 사용되고, KeyEvent는 키 입력 이벤트에 대한 정보를 알고 싶을 때 사용된다.
</br></br>
### 시스템 버튼

단말 아래쪽에 보이는 버튼. (뒤로가기, 홈 등)</br>
뒤로가기 버튼은 앱에서 제어할 수 있지만, 홈과 Recent Apps 버튼은 제어가 불가능하고 정보만 전달받게 됨.</br>

많이 사용하는 키 입력 : 카메라 미리보기를 하면서 사용하는 [카메라] 버튼, 시스템 [BACK] 버튼. 각 버튼의 키 값은 KEYCODE_CAMERA, KEYCODE_BACK 이다.
</br></br>
### 단말 방향 전환

단말 방향이 바뀔때는 액티비티가 메모리에서 없어졌다가 다시 만들어지게 된다. 그렇기 때문에 이전에 액티비티 안에서 사용하던 변수 값을 저장했다가 다시 복원해주어야 한다. 그런데 액티비티를 없앴다가 다시 만들 필요가 없는 경우에는 그렇게 설정할 수도 있다.</br>

값 복원 방법 : onSaveInstanceState 콜백 메소드로 액티비티가 종료되기 전의 상태를 저장하고, 저장한 상태는 onCreate 메소드가 호출될 때 전달되는 객체로 복원가능하다.</br>

단말이 가로 방향일 때 사용되는 리소스 폴더는 layout-land이다 (세로 방향일 때는 layout폴더가 사용된다).
</br></br>
### 수명 주기 (생명 주기, Life Cycle) 메소드

직접 호출하는 것이 아니라 화면의 상태의 따라 시스템이 자동으로 호출해주는 메소드
</br></br>
### 로그

Log 클래스 사용해서 로그를 출력할 수 있다. 로그는 안드로이드 스튜디오 하단의 Logcat 창에서 확인할 수 있다.
</br></br>
### 알림 대화상자

화면 위에 뜨면서 사용자에게 예, 아니오, 취소 버튼을 누르게 한다. 대화상자도 모양을 바꿀 수 있다.

```java
// 1. 대화상자를 만들기 위한 builder 객체 생성
AlertDialog.Builder builder = new AlertDialog.Builder(this);

// 2. Title, Message, Icon을 설정해주고, setPositiveButton, setNeutralButton, 
// setNegativeButton 함수로 각 버튼의 text를 설정해주고, onClickListener() 객체를 전달하면서 버튼이 눌렸을 때 처리해준다.

// 3. 대화상자 만들고 띄우기
AlertDialog dialog = builder.create();
dialog.show();
```
</br></br>
### 프로그레스바 (Progress Bar)

작업의 진행 정도를 표시하거나 작업이 진행 중임을 사용자에게 알려줌. XML에서 <ProgressBar> 태그로 추가한다. 타이틀바에 프로그레스바를 표시할 수도 있다.
</br></br>
### R.layout.activity_main 의미

R은 /app/res 폴더, layout은 R 안의 layout 폴더, activity_main은 R.layout 폴더 안의 activity_main.xml 파일
</br></br>
### 인플레이션 (Inflation)

앱이 실행될 때 XML 레이아웃의 내용이 메모리에 객체화되고, 객체화된 XML 레이아웃을 소스 파일에서 사용한다. 이 과정을 인플레이션이라 한다. </br>

소스코드에서 레이아웃을 객체화하기 전에 (setContentView() 호출) 뷰 객체를 참조하려고 하면 오류가 발생한다.
</br></br>
### LayoutInflater 클래스

setContentView() 로는 부분 화면(부분 레이아웃)을 메모리에 객체화할 수 없다. 부분 화면을 메모리에 객체화하려면 인플레이터(LayoutInflater)를 활용한다. </br>

부분화면은 LayoutInflater 객체를 사용해 뷰그룹 객체로 객체화(인플레이션)한 후 메인 레이아웃에 추가한다.
</br></br>
### 안드로이드 앱 구성 요소

1. 액티비티 (Activity)</br>
2. 서비스 (Service)</br>
3. 브로드캐스트 수신자 (Broadcast Receiver)</br>
4. 내용 제공자 (Content Provider)</br></br>

위의 구성 요소들은 AndroidManifest.xml 파일에 들어간다. 예를 들어 <activity> 태그로 액티비티에 대한 정보를 전달한다. 
</br></br>
### 액티비티 태그 속성

android:label 화면 제목 설정</br>

android:theme 테마 설정 ex) Theme.AppCompat.Dialog는 대화상자 형태의 액티비티
</br></br>
### 새로운 액티비티를 만들어 추가하고 데이터 주고받기

1. 새로운 액티비티 만들기 </br>
XML 파일, 자바 소스파일이 만들어지고 매니페스트 파일에 액티비티 태그 추가됨</br></br>
2. 새로운 액티비티의 XML 레이아웃 정의하기</br>
새로 만들어진 XML 파일 수정</br></br>
3. 메인 액티비티에서 새로운 액티비티 띄우기</br>
startActivityForResult 사용. startActivity는 단순히 화면을 띄워주는 역할만 하고, startActivityForResult를 사용하면 새로운 액티비티에서 응답을 받아 처리할 수 있게 됨.</br>
startActivityForResult의 requestCode는 액티비티 구별에 사용하고, intent객체는 액티비티를 띄우는 목적으로 사용.</br></br>
4. 새로운 액티비티에서 응답 보내기</br>
setResult 사용 (이전 액티비티로 인텐트 전달함)</br></br>
5. 응답 처리하기</br>
onActivityResult 사용
</br></br>
### 인텐트 (Intent)

앱 구성 요소 간 정보를 전달하는 역할.</br></br>

ex) 인텐트 전달 대표 메서드</br>
액티비티를 화면에 띄울 때 : startActivity(), startActivityForResult()</br>
서비스를 시작할 때 : startService(), bindService()</br>
인텐트 객체를 브로드캐스팅 방식으로 전송할 때 : broadcastIntent()</br></br>

인텐트 구성 요소 : 액션 (수행할 기능), 데이터 (액션이 수행될 대상의 데이터).</br>
데이터의 포맷이 어떤 MIME 타입을 갖고 있는지에 따라 적절한 앱을 찾아 액티비티를 띄워준다.</br></br>

ex) 액션 예시 : ACTION_DIAL, ACION_VIEW, ACTION_EDIT
</br></br>
### 컴포넌트 (Component)

액티비티와 같은 독립적인 구성 요소</br>
ex) ComponentName객체를 만들어 대상 액티비티의 이름을 지정 (패키지 이름까지 함께). 
</br></br>
### 액티비티 처리 방식

액티비티 매니저 (ActivityManager)라는 객체에 의해 액티비티 스택(ActivityStack)으로 관리된다. 같은 액티비티를 StartActivity나 StartActivityForResult로 여러 번 호출하면 같은 액티비티가 중복되어 스택에 쌓이게 되니 주의해야 한다.
</br></br>
### 플래그

액티비티의 중복 생성 문제를 해결하기 위해 사용한다. </br></br>

FLAG_ACTIVITY_SINGLE_TOP : 액티비티 생성 시 이미 생성된 액티비티가 있으면 그것을 사용. </br>
이러한 상황에서 인텐트를 전달받으려면 onNewIntent 메서드를 사용한다. 인텐트는 onCreate 함수에서 getIntent로 전달받을 수 있는데, 액티비티 재사용 시 onCreate함수가 호출되지 않기 때문이다. </br></br>

FLAG_ACTIVITY_NO_HISTORY : 처음 이후에 실행된 액티비티는 액티비티 스택에 추가되지 않는다.</br></br>

FLAG_ACTIVITY_CLEAR_TOP : 이 액티비티 위에 있는 다른 액티비티를 모두 종료시킨다.
</br></br>
### 부가 데이터

한 액티비티에서 다른 액티비티를 띄우며 데이터를 전달할 때 사용한다. 인텐트 내의 번들(Bundle)객체에 담아서 전달하게 된다. 
</br></br>
### 번들 객체

putExtra(), getExtra()로 데이터를 넣고 뺀다. 문자열이나 정수와 같은 부가 데이터를 넣을 때는 Key와 Value를 쌍으로 만들어 넣고, Key를 통해 다시 그 값을 받아올 수 있다. </br></br>

전달하고 싶은 자료형이 기본 자료형이 아니라 객체(Object) 자료형인 경우에는 객체 데이터를 바이트 배열로 변환하거나 Parcelable 인터페이스를 구현하는 객체를 만들어 직렬화한 다름 전달해야 한다. Serializable, Parcelable은 유사한데 Parcelable이 직렬화했을 때 크기가 더 작다.
</br></br>
### 태스크 (Task)

앱을 실행하면 하나의 프로세스 위에서 동작한다. 프로세스가 하나 실행되고, 그 위에는 가상 머신이 만들어지며, 가상 머신 위에서 앱이 실행되는 방식이다. 프로세스간 정보 공유는 어렵기 때문에 태스크가 만들어져 있다.

</br></br>
### 액티비티의 상태

실행(Running) : 화면상에 액티비티가 보이면서 실행되어 있는 상태. 액티비티 스택의 최상위에 있으며 포커스를 가지고 있음</br>
일시 정지 (Paused) : 사용자에게 보이지만 다른 액티비티가 위에 있어 포커스를 받지 못하는 상태. 대화상자가 위에 있어 일부가 가려진 경우에 해당한다.</br>
중지 (Stopped) : 다른 액티비티에 의해 완전히 가려져 보이지 않는 상태</br></br>

상태 사이를 이동할때는 특정한 함수가 실행된다.
</br></br>
### SharedPreferences

앱 안에서 간단한 데이터를 저장, 복원하는 데 사용한다.
</br></br>
### 액티비티 (Activity)

안드로이드 앱의 스크린 하나
</br></br>
### tools:context 속성

해당 레이아웃이 어떤 액티비티와 관련있는지 정의한다.
</br></br>
### Context

어플리케이션(객체)의 현재 상태의 맥락(context)를 의미한다. 새로 생성된 객체가 지금 어떤 일이 일어나고 있는지 알 수 있도록 한다. 따라서, 액티비티와 어플리케이션에 대한 정보를 얻기 위해서는 컨텍스트를 사용하면 된다.
</br></br>
### Application Context

어플리케이션 자체와 연결된 것으로, 어플리케이션의 life cycle이 지속되는 동안 동일하다. 어플리케이션 컨텍스트는 현재의 컨텍스트와 분리된 라이프사이클을 가진 컨텍스트가 필요할 때나 액티비티의 범위를 넘어선 컨텍스트를 전달할 때 사용한다. 
</br></br>
### Activity Context

액티비티와 연결된 것으로, 액티비티를 파괴시키고 다시 시작시키면 activity context도 바뀐다. 
</br></br>
### getApplicationContext()

application context를 가리킨다. this는 activity context를 가리킨다.
</br></br>
### selector

버튼 눌림 효과를 줄 때 사용한다.
</br></br>
### Adapter

AdapterView와 해당 뷰에 들어갈 데이터를 연결해주는 다리 역할을 한다. Adapter로 데이터 아이템 접근, 데이터 셋의 아이템으로 뷰를 만들 수 있다.
</br></br>
### android:background만으로 배경 색을 바꿀 수 없을 때

```
android:background="@drawable/select_button"
app:backgroundTint="@null"
```

backgroundTint를 null로 설정하거나, background대신에 backgroundTint로 색상을 설정한다.
</br></br>
### SeekBar

ProgressBar를 확장한 것으로, 현재 진행 상태를 유저가 조절할 수 있는 것.
</br></br>
### app:cardElevation

CardView사용 시 cardElevation속성은 그림자의 사이즈와 부드러움을 결정해서 깊이를 표현한다.
