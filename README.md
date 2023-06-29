# swipe_nav_pratice_android
[one of the geeks for geeks's pages](https://www.geeksforgeeks.org/how-to-create-swipe-navigation-in-an-android-app/?ref=lbp)를 보고 따라서 타이핑한 swipe Navigation 연습입니다.

# Geeks for Geeks 부분 한국어로 해석
안드로이드에선 button click이 아니라 좌, 우 방향의 swipe를 통해서도 navigation을 할 수 있습니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다. 이것은 사용자가 navigation을 더 쉽게 할 수 있게 해줍니다.<br>
서로 다른 activity로 swipe하는 swipe 특징을 사용하는 앱이 있다. 예를 들어, 유명한 채팅 앱인 snapchat은 lense, chats, storeis를 swipe 한다. 우리는 우리의 swipe view를 구현하는 법을 배워보자. 우리는 아래의 두 가지 features를 사용해 구현할 것이다.
<ol>
    <li><b>Fragments :</b> Fragment는 한 activity의 부분이다. 우리는 screen의 부분 혹은 전체를 차지하는 Fragment를 가진다. 혹은 우리는 전체 스크린을 구성하기 위해 동시에 여러 프래그먼트를 보여줄 수 도 있다. 액티비티 안에서 우리는 또한 다른 fragments끼리 서로 swap 할 수 있다.</li>
    <li><b>ViewPager :</b> ViewPager는 Fragments들의 conjunction에 사용되는 Java의 클래스이다. 이것은 보통 app의 UI를 디자인하기 위해 사용된다.</li>
</ol>

<h2>How Does it Work?</h2>
우선, setAdapter()를 사용해 ViewPager의 adapter를 설정한다. 우리가 셋팅한 adapter는 자바의 추상 클래스로 FragmentPagerAdapter라 불린다. 
그런 이유로, FragmentPagerAdapter를 상속받고(연장하고) screen에 우리의 Fragments를 보여주는 우리 자신의 SampleFragmentPagerAdapter를 만든다.<br>
기기에서 앱을 런치할 때, ViewPager는 SampleFragmentPagerAdapter에게 얼마나 많은 page를 swipe할지 묻는다.
adapter의 getCount() 메소드는 ViewPager에게 이 대답을 해준다.<br>
그리고 나서, ViewPager는 0번째 있는 Fragment를 요청하고 adapter는 우리의 screen 위에 ViewPager가 보여줄 특정한 fragment를return한다.
우리가 왼쪽으로 swipe할 때, VeiwPager는 adapter에게 1번째 위치의 Fragment를 요청하고, 그 스크린 위에 그것을 보여준다. 이러한 행위를 반복한다.<br>

<h4>재정리 </h4>
<ul>
    <li>viewPager(스크린 기능 담당)이 adapter에게 얼마나 많은 page가 있는 지 질문</li>
    <li>adapter는 getCount()로 이에 대한 답장</li>
    <li>viewPager는 adapter에게 0번 Fragment 요청</li>
    <li>adapter는 이에 대한 답장</li>
    <li>있는 pages 수 만큼 반복</li>
</ul>
