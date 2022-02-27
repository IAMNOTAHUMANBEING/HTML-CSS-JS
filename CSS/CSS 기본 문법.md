출처: https://poiemaweb.com/

1. CSS 기본 문법
CSS(Cascading Style Sheets): HTML이나 XML과 같은 구조화 된 문서(Document)를 화면, 종이 등에 어떻게 렌더링할 것인지를 정의하기 위한 언어이다. 
즉, CSS는 HTML의 각 요소(Element)의 style(design, layout etc)을 정의하여 화면(Screen) 등에 어떻게 렌더링하면 되는지 브라우저에게 설명하기 위한 언어이다.
셀렉터 (Selector, 선택자): 스타일을 적용하고자 하는 HTML 요소를 선택하기 위해 CSS에서 제공하는 수단
- Rule Set(또는 Rule): 셀렉터에 의해 선택된 특정 HTML 요소를 어떻게 렌더링(Rendering)할 것인지 브라우저에 지시하는 역할을 한다. Rule Set의 집합을 스타일시트(Style Sheet)라고 함.
셀렉터(선언블록(선언(프로퍼티:값)))
프로퍼티 (Property / 속성): 다양한 style을 정의, 여러 개의 프로퍼티를 연속해서 지정할 수 있으며 세미콜론(;)으로 구분
값 (Value / 속성값):  해당 프로퍼티에 사용할 수 있는 값을 “키워드”나 “크기 단위” 또는 “색상 표현 단위” 등의 특정 단위로 지정
HTML과 CSS의 연동: Link style(선호), Embedding style, Inline Style
Reset CSS 사용하기: 모든 웹 브라우저는 디폴트 스타일(브라우저가 내장하고 있는 기본 스타일)을 가지고 있어 CSS가 없어도 작동한다. 
그런데 웹브라우저에 따라 디폴트 스타일이 상이하고 지원하는 tag나 style도 제각각이어서 주의가 필요, 
Reset CSS는 기본적인 HTML 요소의 CSS를 초기화하는 용도로 사용한다. 즉, 브라우저 별로 제각각인 디폴트 스타일을 하나의 스타일로 통일시켜 주는 역할을 한다.
자주 사용되는 Reset CSS: Eric Meyer’s reset, normalize.css

2. 셀렉터
복수개의 셀렉터를 연속하여 지정할 수 있으며 쉼표( , )로 구분한다.
*{} 전체 셀렉터 (Universal Selector): HTML 문서 내의 모든 요소를 선택한다. html 요소를 포함한 모든 요소가 선택된다. (head 요소도 포함된다)
태그명{} 태그 셀렉터 (Type Selector): 지정된 태그명을 가지는 요소를 선택한다.
#id{} ID 셀렉터 (ID Selector): id 어트리뷰트 값을 지정하여 일치하는 요소를 선택한다. id 어트리뷰트 값은 중복될 수 없는 유일한 값이다.
.class{} 클래스 셀렉터 (Class Selector): class 어트리뷰트 값을 지정하여 일치하는 요소를 선택한다. class 어트리뷰트 값은 중복될 수 있다.
HTML 요소에 class 어트리뷰트 값은 공백으로 구분하여 여러 개 지정할 수 있다. 아래와 같이 클래스 셀렉터를 사용하여 미리 스타일을 정의해 두고, 
HTML 요소는 이미 정의되어 있는 클래스를 지정하는 것으로 필요한 스타일을 지정할 수 있다. 이것은 재사용의 측면에서 유용하다.
어트리뷰트 셀렉터 (Attribute Selector)
- 셀렉터[어트리뷰트]{} : 지정된 어트리뷰트를 갖는 모든 요소를 선택한다.
- 셀렉터[어트리뷰트=”값”]{} :지정된 어트리뷰트를 가지며 지정된 값과 어트리뷰트의 값이 일치하는 모든 요소를 선택한다.
- 셀렉터[어트리뷰트~=”값”]{}: 지정된 어트리뷰트의 값이 지정된 값을 (공백으로 분리된) 단어로 포함하는 요소를 선택한다.
- 셀렉터[어트리뷰트|=”값”]{}: 지정된 어트리뷰트의 값과 일치하거나 지정 어트리뷰트 값 뒤 연이은 하이픈(“값-“)으로 시작하는 요소를 선택한다.
- 셀렉터[어트리뷰트^=”값”]{}: 지정된 어트리뷰트 값으로 시작하는 요소를 선택한다.
- 셀렉터[어트리뷰트$=”값”]{}: 지정된 어트리뷰트 값으로 끝나는 요소를 선택한다.
- 셀렉터[어트리뷰트*=”값”]{}: 지정된 어트리뷰트 값을 포함하는 요소를 선택한다(단어로 포함하는 것과 구분)
복합 셀렉터 (Combinator): 
- 후손 셀렉터 (Descendant Combinator): 셀렉터A 셀렉터B
자신의 1 level 상위에 속하는 요소를 부모 요소, 1 level 하위에 속하는 요소를 자손 요소(자식 요소)라한다. 자신보다 n level 하위에 속하는 요소는 후손 요소(하위 요소)라 한다.
후손 셀렉터는 셀렉터A의 모든 후손(하위) 요소 중 셀렉터B와 일치하는 요소를 선택한다.
- 자식 셀렉터 (Child Combinator): 셀렉터A > 셀렉터B
자손 셀렉터는 셀렉터A의 모든 자식 요소 중 셀렉터B와 일치하는 요소를 선택한다.
- 형제(동위) 셀렉터 (Sibling Combinator): 형제(동위) 셀렉터는 형제 관계(동위 관계)에서 뒤에 위치하는 요소를 선택할 때 사용한다.
- - 인접 형제 셀렉터(Adjacent Sibling Combinator): 셀렉터A + 셀렉터B
    셀렉터A의 형제 요소 중 셀렉터A 바로 뒤에 위치하는 셀렉터B 요소를 선택한다. A와 B 사이에 다른 요소가 존재하면 선택되지 않는다.
- - 일반 형제 셀렉터(General Sibling Combinator): 셀렉터A ~ 셀렉터B
    셀렉터A의 형제 요소 중 셀렉터A 뒤에 위치하는 셀렉터B 요소를 모두 선택한다.
가상 클래스 셀렉터 (Pseudo-Class Selector): 가상 클래스는 요소의 특정 상태에 따라 스타일을 정의할 때 사용된다. 특정 상태란 예를 들어 다음과 같다.
마우스가 올라와 있을때, 링크를 방문했을 때와 아직 방문하지 않았을 때, 포커스가 들어와 있을 때 등
가상 클래스는 마침표(.) 대신 콜론(:)을 사용한다. CSS 표준에 의해 미리 정의된 이름이 있기 때문에 임의의 이름을 사용할 수 없다.
selector:pseudo-class {
  property: value;
}
- 링크 셀렉터(Link pseudo-classes), 동적 셀렉터(User action pseudo-classes): 
- - :link: 셀렉터가 방문하지 않은 링크일 때
- - :visited: 셀렉터가 방문한 링크일 때
- - :hover:	셀렉터에 마우스가 올라와 있을 때
- - :active: 셀렉터가 클릭된 상태일 때
- - :focus: 셀렉터에 포커스가 들어와 있을 때
- UI 요소 상태 셀렉터(UI element states pseudo-classes):
- - :checked: 셀렉터가 체크 상태일 때
- - :enabled: 셀렉터가 사용 가능한 상태일 때
- - :disabled: 셀렉터가 사용 불가능한 상태일 때
- 구조 가상 클래스 셀렉터(Structural pseudo-classes):
- - :first-child: 셀렉터에 해당하는 모든 요소 중 첫번째 자식인 요소를 선택한다.
- - :last-child: 셀렉터에 해당하는 모든 요소 중 마지막 자식인 요소를 선택한다.
- - :nth-child(n): 셀렉터에 해당하는 모든 요소 중 앞에서 n번째 자식인 요소를 선택한다.
- - :nth-last-child(n): 셀렉터에 해당하는 모든 요소 중 뒤에서 n번째 자식인 요소를 선택한다.
0과 음수는 생략되기 때문에 2n+1과 2n-1, 3n-2와 3n+1은 결과적으로 같은 수열을 생성한다.
- - :first-of-type	셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 첫번째 등장하는 요소를 선택한다.
- - :last-of-type	셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 마지막에 등장하는 요소를 선택한다.
- - :nth-of-type(n)	셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 앞에서 n번째에 등장하는 요소를 선택한다.
- - :nth-last-of-type(n)	셀렉터에 해당하는 요소의 부모 요소의 자식 요소 중 뒤에서 n번째에 등장하는 요소를 선택한다.
- 부정 셀렉터(Negation pseudo-class)
- - :not(셀렉터): 셀렉터에 해당하지 않는 모든 요소를 선택한다.
- 정합성 체크 셀렉터(validity pseudo-class)
- - :valid(셀렉터): 정합성 검증이 성공한 input 요소 또는 form 요소를 선택한다.
- - :invalid(셀렉터): 정합성 검증이 실패한 input 요소 또는 form 요소를 선택한다.
가상 요소 셀렉터 (Pseudo-Element Selector): 가상 요소는 요소의 특정 부분에 스타일을 적용하기 위하여 사용된다. 특정 부분이란 예를 들어 다음과 같다.
요소 콘텐츠의 첫글자 또는 첫줄, 요소 콘텐츠의 앞 또는 뒤, 가상 요소에는 두개의 콜론(::)을 사용한다. CSS 표준에 의해 미리 정의된 이름이 있기 때문에 임의의 이름을 사용할 수 없다.
- ::first-letter	콘텐츠의 첫글자를 선택한다.
- ::first-line	콘텐츠의 첫줄을 선택한다. 블록 요소에만 적용할 수 있다.
- ::after	콘텐츠의 뒤에 위치하는 공간을 선택한다. 일반적으로 content 프로퍼티와 함께 사용된다.
- ::before	콘텐츠의 앞에 위치하는 공간을 선택한다. 일반적으로 content 프로퍼티와 함께 사용된다.
- ::selection	드래그한 콘텐츠를 선택한다. iOS Safari 등 일부 브라우저에서 동작 않는다.


3. CSS 프로퍼티 값의 단위
CSS 프로퍼티에는 키워드, 크기 단위, 색상 표현 단위 등의 특정 단위를 갖는 값을 지정한다.
키워드: 각 프로퍼티에 따라 사용할 수 있는 키워드가 존재한다. 예를 들어 display 프로퍼티의 값으로 사용할 수 있는 키워드는 block, inline, inline-block, none이 있다. 자세한 내용은 각각의 프로퍼티를 참조하기 바란다.
크기 단위: cm, mm, inch 등의 단위도 존재하나 CSS에서 사용하는 대표적인 크기 단위는 px, em, %이다. px은 절대값이고 em, %는 상대값이다.
대부분 브라우저의 폰트 사이즈 기본값은 16px, 1em, 100%이다. 프로퍼티 값이 0인 경우, 단위를 생략할 수 있다.
- px: px은 픽셀(화소) 단위이다. 1px은 화소 1개 크기를 의미한다. 픽셀은 디바이스 해상도(resolution)에 따라 상대적인 크기를 갖는다.
이와 같이 디바이스 별로 픽셀(화소)의 크기는 제각각이기 때문에 픽셀을 기준으로 하는 단위는 명확하지 않다. 따라서 대부분의 브라우저는 1px을 1/96 인치의 절대단위로 인식한다. px은 요소의 크기나 이미지의 크기 지정에 주로 사용된다.
- %: %는 백분률 단위의 상대 단위이다. 요소에 지정된 사이즈(상속된 사이즈나 디폴트 사이즈)에 상대적인 사이즈를 설정한다.
- em: em은 배수(倍數) 단위로 상대 단위이다. 요소에 지정된 사이즈(상속된 사이즈나 디폴트 사이즈)에 상대적인 사이즈를 설정한다. 예를 들어 1em은 요소에 지정된 사이즈와 같고 2em은 요소에 지정된 사이즈의 2배이다.
폰트 사이즈 설정이나 콘텐츠를 포함하는 컨테이너의 크기 설정에 사용하면 상대적인 설정이 가능하여 편리하다. 첩된 자식 요소에 em을 지정하면 모든 자식 요소의 사이즈에 영향을 미치기 때문에 주의하여야 한다.
- rem: em의 기준은 상속의 영향으로 바뀔 수 있다. 즉, 상황에 따라 1.2em은 각기 다른 값을 가질 수 있다. rem은 최상위 요소(html)의 사이즈를 기준으로 삼는다. rem의 r은 root를 의미한다.
사용자가 브라우저의 기본 폰트 크기를 변경(Mac Chrome의 경우, 설정 > 고급 설정 표시 > 웹 콘텐츠 > 글꼴 맞춤 설정)하더라도 이에 따라 웹사이트의 레이아웃을 적절히 조정할 수 있다는 장점이 있다. 따라서 폰트 사이즈 뿐만이 아니라 콘텐츠의 크기에 따라 가변적으로 대응하여야 하는 wrapper 요소(container) 등에 적합하다. Reset CSS를 사용하여 사전에 html 요소의 font-size 지정이 필요하다. font-size 미지정 시에는 16px가 적용된다.
- Viewport 단위(vh, vw, vmin, vmax): 반응형 웹디자인은 화면의 크기에 동적으로 대응하기 위해 % 단위를 자주 사용한다. 하지만 % 단위는 em과 같이 상속에 의해 부모 요소에 상대적 영향을 받는다.
Viewport 단위는 상대적인 단위로 viewport를 기준으로 한 상대적 사이즈를 의미한다.
- - vw	viewport 너비의 1/100
- - vh	viewport 높이의 1/100
- - vmin	viewport 너비 또는 높이 중 작은 쪽의 1/100
- - vmax	viewport 너비 또는 높이 중 큰 쪽의 1/100
색상 표현 단위: 색상을 지정하기 위해 키워드(red, blue…)를 사용할 수 있다. 사용이 간편하다는 장점이 있으나 표현할 수 있는 색상의 수는 제한된다. 색상를 표현할 수 있는 키워드 리스트는 W3C css3-color를 참고하기 바란다.
더욱 다양한 색상을 표현하기 위해 다음과 같은 색상 표현 단위를 사용할 수 있다. HTML COLOR CODES를 참조하면 편리하다.
- HEX 코드 단위 (Hexadecimal Colors)	#000000
- RGB (Red, Green, Blue)	rgb(255, 255, 0)
- RGBA (Red, Green, Blue, Alpha/투명도)	rgba(255, 255, 0, 1)
- HSL (Hue/색상, Saturation/채도, Lightness/명도)	hsl(0, 100%, 25%)
- HSLA (Hue, Saturation, Lightness, Alpha)	hsla(60, 100%, 50%, 1)

4. 박스 모델
모든 HTML 요소는 Box 형태의 영역을 가지고 있다. Box는 콘텐트(Content), 패딩(Padding), 테두리(Border), 마진(Margin)로 구성된다.
- Content: 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. width, height 프로퍼티를 갖는다.
- Padding: 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역이다. padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명(transparent)이다. 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용된다.
- Border: 테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미한다.
- Margin: 테두리(Border) 바깥에 위치하는 요소의 외부 여백 영역이다. margin 프로퍼티 값은 마진 영역의 두께를 의미한다. 기본적으로 투명(transparent)하며 배경색을 지정할 수 없다.
width / height 프로퍼티: width와 height 프로퍼티는 요소의 너비와 높이를 지정하기 위해 사용된다. 이때 지정되는 요소의 너비와 높이는 콘텐츠 영역을 대상으로 한다.
(이는 box-sizing 프로퍼티에 기본값인 content-box가 적용되었기 때문이다. box-sizing 프로퍼티에 border-box를 적용하면 콘텐츠 영역, padding, border가 포함된 영역을 width / height 프로퍼티의 대상으로 지정할 수 있다)
만일 width와 height로 지정한 콘텐츠 영역보다 실제 콘텐츠가 크면 콘텐츠 영역을 넘치게 된다는 것에 유의하여야 한다.
(overflow: hidden;을 지정하면 넘친 콘텐츠를 감출 수 있다.)
기본적으로 width와 height 프로퍼티는 콘텐츠 영역을 대상으로 요소의 너비와 높이를 지정하므로 박스 전체 크기는 다음과 같이 계산할 수 있다.
전체 너비: width + left padding + right padding + left border + right border + left margin + right margin
전체 높이: height + top padding + bottom padding + top border + bottom border + top margin + bottom margin
width와 height 프로퍼티의 초기값은 auto로써 이것은 브라우저가 상황에 따라 적당한 width와 height 값을 계산할 것을 의미한다.
예를 들어 block 요소의 경우, width는 부모 요소의 100%, height는 콘텐츠의 높이(+ 약간의 여분)가 지정된다.
명시적으로 width와 height를 지정하기 위해서는 px, % 등의 크기 단위를 사용한다.(width와 height 프로퍼티를 비롯한 모든 박스모델 관련 프로퍼티(margin, padding, border, box-sizing 등)는 상속되지 않는다.)
 margin / padding 프로퍼티: margin / padding 프로퍼티는 content의 4개 방향(top, right, left, bottom)에 대하여 지정이 가능하다.
 -top, -right, -bottom, -left 4방향의 프로퍼티를 각각 지정하지 않고 margin, padding 1개의 프로퍼티만으로 4방향의 프로퍼티를 한번에 지정할 수 있다.
 margin 프로퍼티에 auto 키워드를 설정하면 해당 요소를 브라우저 중앙에 위치 시킬 수 있다. 보다 자세한 중앙 정렬 방법에 대해서는 검색하기 바란다.
 요소 너비가 브라우저 너비보다 크면 가로 스크롤바가 만들어진다. 이 문제를 해결하기 위해서 max-width 프로퍼티를 사용할 수 있다.
 max-width 프로퍼티를 사용하면 브라우저 너비가 요소의 너비보다 좁아질 때 자동으로 요소의 너비가 줄어든다.
 max-width 프로퍼티는 요소 너비의 최대값을, min-width 프로퍼티는 요소 너비의 최소값을 지정한다. 예를 들어 max-width: 300px;의 경우, 브라우저의 너비가 300px보다 작아지면 요소 너비는 브라우저의 너비에 따라서 작아진다. 
 min-width: 300px;의 경우 브라우저의 너비가 300px보다 작아져도 요소 너비는 지정 너비(300px)을 유지한다.
 border 프로퍼티
 - border-style: 테두리 선의 스타일을 지정한다. 프로퍼티 값의 갯수에 따라 4개 방향(top, right, left, bottom)에 대하여 지정이 가능하다.
 - border-width: 테두리의 두께를 지정한다. 프로퍼티 값의 갯수에 따라 4개 방향(top, right, left, bottom)에 대하여 지정이 가능하다.
 - border-color: 테두리의 색상을 지정한다. 프로퍼티 값의 갯수에 따라 4개 방향(top, right, left, bottom)에 대하여 지정이 가능하다.
 - border-radius: 테두리 모서리를 둥글게 표현하도록 지정한다. 프로퍼티 값은 길이를 나타내는 단위(px, em 등)와 %를 사용한다. 각각의 모서리에 border-radius 프로퍼티를 개별적으로 지정할 수도 있고 4개의 모서리를 short-hand로 한번에 지정할 수도 있다. 하나 혹은 두개의 반지름을 설정하여 각각의 모서리 굴곡을 설정할 수 있기 때문에 원 혹은 타원의 모양으로 정의가 가능하다.
 - border: border-width, border-style, border-color를 한번에 설정하기 위한 shorthand 프로퍼티이다
box-sizing 프로퍼티: width, height 프로퍼티의 대상 영역을 변경할 수 있다. box-sizing 프로퍼티의 기본값은 content-box이다. 이는 width, height 프로퍼티의 대상 영역이 content 영역을 의미한다. box-sizing 프로퍼티의 값을 border-box로 지정하면 마진을 제외한 박스 모델 전체를 width, height 프로퍼티의 대상 영역으로 지정할 수 있어서 CSS Layout을 직관적으로 사용할 수 있게 한다.
- content-box: width, height 프로퍼티 값은 content 영역을 의미한다. (기본값)
- border-box: width, height 프로퍼티 값은 content 영역, padding, border가 포함된 값을 의미한다.
box-sizing 프로퍼티는 상속되지 않는다. 따라서 box-sizing 프로퍼티를 사용하도록 초기화하려면 아래와 같이 정의한다.
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}

5. display, visibility, opacity 프로퍼티
display 프로퍼티: display 프로퍼티는 layout 정의에 자주 사용되는 중요한 프로퍼티이다.
- block: block 특성을 가지는 요소(block 레벨 요소)로 지정
- inline: inline 특성을 가지는 요소(inline 레벨 요소)로 지정
- inline-block: inline-block 특성을 가지는 요소(inline-block 레벨 요소)로 지정
- none: 해당 요소를 화면에 표시하지 않는다 (공간조차 사라진다)
모든 HTML 요소는 아무런 CSS를 적용하지 않아도 기본적으로 브라우저에 표현되는 디폴트 표시값을 가진다. HTML 요소는 block 또는 inline 특성을 갖는다.(display 프로퍼티는 상속되지 않는다.)
- block 레벨 요소
- - 항상 새로운 라인에서 시작한다.
- - 화면 크기 전체의 가로폭을 차지한다. (width: 100%)
- - width, height, margin, padding 프로퍼티 지정이 가능하다.
- - block 레벨 요소 내에 inline 레벨 요소를 포함할 수 있다
- - ex. div, h, p, ol, ul, li, hr, table, form
- inline 레벨 요소
- - 새로운 라인에서 시작하지 않으며 문장의 중간에 들어갈 수 있다. 즉, 줄을 바꾸지 않고 다른 요소와 함께 한 행에 위치한다
- - content의 너비만큼 가로폭을 차지한다.
- - width, height, margin-top, margin-bottom 프로퍼티를 지정할 수 없다. 상, 하 여백은 line-height로 지정한다.
- - inline 레벨 요소 뒤에 공백(엔터, 스페이스 등)이 있는 경우, 정의하지 않은 space(4px)가 자동 지정된다
- - inline 레벨 요소 내에 block 레벨 요소를 포함할 수 없다. inline 레벨 요소는 일반적으로 block 레벨 요소에 포함되어 사용된다.
- - ex. span, a, strong, img, br, input, select, textarea, button
- inline-block 레벨 요소: block과 inline 레벨 요소의 특징을 모두 갖는다. inline 레벨 요소와 같이 한 줄에 표현되면서 width, height, margin 프로퍼티를 모두 지정할 수 있다.
- - 기본적으로 inline 레벨 요소와 흡사하게 줄을 바꾸지 않고 다른 요소와 함께 한 행에 위치시킬 수 있다.
- - block 레벨 요소처럼 width, height, margin, padding 프로퍼티를 모두 정의할 수 있다. 상, 하 여백을 margin과 line-height 두가지 프로퍼티 모두를 통해 제어할 수 있다.
- - content의 너비만큼 가로폭을 차지한다.
- - inline-block 레벨 요소 뒤에 공백(엔터, 스페이스 등)이 있는 경우, 정의하지 않은 space(4px)가 자동 지정된다. 이것을 회피 방법은 (https://css-tricks.com/fighting-the-space-between-inline-block-elements/)를 참조하기 바란다.
- visibility 프로퍼티: visibility 프로퍼티는 요소를 보이게 할 것인지 보이지 않게 할 것인지를 정의한다. 즉, 요소의 렌더링 여부를 결정한다.
- - visible: 해당 요소를 보이게 한다 (기본값)
- - hidden: 해당 요소를 보이지 않게 한다. display: none;은 해당 요소의 공간까지 사라지게 하지만 visibility: hidden;은 해당 요소의 공간은 사라지지 않고 남아있게 된다.
- - collapse: table 요소에 사용하며 행이나 열을 보이지 않게 한다
- - none: table 요소의 row나 column을 보이지 않게 한다. IE, 파이어폭스에서만 동작하며 크롬에서는 hidden과 동일하게 동작한다.
- opacity 프로퍼티: opacity 프로퍼티는 요소의 투명도를 정의한다. 0.0 ~ 1.0의 값을 입력하며 0.0은 투명, 1.0은 불투명을 의미한다.

6. 백그라운드
Background 관련 프로퍼티는 해당 요소의 배경으로 이미지 또는 색상을 정의한다. 자세한 내용은 (https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders)를 참조한다.
background-image 프로퍼티: 요소에 배경 이미지를 지정한다.
background-repeat 프로퍼티: 배경 이미지의 반복을 지정한다. 수직, 수평 또는 수직과 수평 모두의 반복을 지정할 수 있다. 설정된 이미지의 크기가 화면보다 작으면 자동으로 이미지가 반복 출력되어 화면을 채우게 된다. 이것은 background-repeat 프로퍼티의 기본값이 repeat이기 때문이다. 반복 출력을 멈추고 싶은 경우, background-repeat 프로퍼티값에 no-repeat를 설정한다.
x축으로만 배경 이미지를 반복할 경우, background-repeat 프로퍼티값에 repeat-x, y축으로만 배경 이미지를 반복할 경우, repeat-y를 설정한다.
background-image에 복수개의 이미지를 설정할 경우, 먼저 설정된 이미지가 전면에 출력된다.
background-size 프로퍼티: 배경 이미지의 사이즈를 지정한다. 배경 이미지의 고유 비율을 유지하기 때문에 설정에 따라 이미지의 일부가 보이지 않을 수 있다. 프로퍼티값은 px, %, cover, contain 등을 사용한다.
배경이미지의 width, height를 모두 설정할 수 있다. 이때 첫번째 값은 width, 두번째 값은 height를 의미한다. 하나의 값만을 지정한 경우, 지정한 값은 width를 의미하게 되며 height는 auto로 지정된다.
- px값 지정: 배경이미지 크기가 지정된 px값 그대로 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다.
- %값 지정: 배경이미지 크기가 지정된 %값에 비례하여 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다. 화면을 줄이거나 늘리면 배경이미지의 크기도 따라서 변경되어 찌그러지는 현상이 나타난다.
- cover 지정: 배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 width, height 중 큰값에 배경이미지를 맞춘다. 따라서 이미지의 일부가 보이지 않을 수 있다.
- contain 지정: 배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 영역에 배경이미지가 보이지 않는 부분없이 전체가 들어갈 수 있도록 이미지 스케일을 조정한다.
width, height의 프로퍼티값은 공백으로 구분하여야 한다. 프로퍼티값을 쉼표로 구분하면 다른 배경이미지의 너비를 지정하는 것으로 인식되기 때문에 주의가 필요하다.
background-attachment 프로퍼티: 일반적으로 화면을 스크롤하면 배경 이미지도 함께 스크롤된다. 화면이 스크롤되더라도 배경이미지는 스크롤되지 않고 고정되어 있게 하려면 background-attachment 프로퍼티에 fixed 키워드를 지정한다.
background-position 프로퍼티: 일반적으로 background-image는 좌상단부터 이미지를 출력한다. 이때 background-position 프로퍼티를 사용하면 이미지의 좌표(xpos, ypos)를 지정 할 수 있다.
기본값은 background-position: 0% 0%;로 배경이미지는 좌측 상단에 위치하게 된다.
background-color 프로퍼티: background-color 프로퍼티는 요소의 배경 색상을 지정한다. 색상값 또는 transparent 키워드를 지정할 수 있다.
background Shorthand: background-color, background-image, background-repeat, background-position를 한번에 정의하기 위한 Shorthand Syntax이다.
ex. background: color || image || repeat || attachment || position

7. 폰트와 텍스트
폰트 및 텍스트 관련 프로퍼티는 폰트의 크기, 폰트의 지정, 폰트의 스타일, 텍스트 정렬 등을 정의한다.
font-size 프로퍼티: 텍스트의 크기를 정의한다.
font-family 프로퍼티: 폰트를 지정한다. 컴퓨터에 해당 폰트가 설치되어 있지 않으면 적용되지 않는다.
폰트는 여러 개를 동시에 지정이 가능하다. 첫번째 지정한 폰트가 클라이언트 컴퓨터에 설치되어 있지 않은 경우, 다음에 지정된 폰트를 적용한다. 따라서 마지막에 지정하는 폰트는 대부분의 OS에 기본적으로 설치되어 있는 generic-family 폰트(Serif, Sans-serif, Mono space)를 지정하는 것이 일반적이다. 폰트명은 따옴표로 감싸주며 폰트명이 한단어인 경우는 따옴표로 감싸주지 않아도 된다.
font-style / font-weight 프로퍼티: font-style 프로퍼티는 이탤릭체의 지정, font-weight 프로퍼티는 폰트 굵기 지정에 사용된다.
font Shorthand: Shorthand Syntax ex. font : font-style(optional) font-variant(optional) font-weight(optional) font-size(mandatory) / line-height(optional) font-family(mandatory)
line-height 프로퍼티: 텍스트의 높이를 지정한다. 텍스트 수직 정렬에도 응용되어 사용된다.
다음은 수직 중앙 정렬 예제이다. a 요소의 line-height 값과 a 요소를 감싸는 div 요소의 height 값을 일치시킨다.
letter-spacing 프로퍼티: 글자 사이의 간격을 지정한다.
text-align 프로퍼티: 텍스트의 수평 정렬을 정의한다.
text-decoration 프로퍼티: 링크 underline을 제거할 수 있다. 또는 텍스트에 underline, overline, line-through를 추가할 수도 있다.
white-space 프로퍼티: white space는 공백(space), 들여쓰기(tab), 줄바꿈(line break)을 의미한다. html은 기본적으로 연속된 공백(space), 들여쓰기(tab)는 1번만 실행되며 줄바꿈(line break)은 무시된다. 또한 텍스트는 부모의 가로 영역을 벗어나지 않고 자동 줄바꿈(wrap)된다. white-space 프로퍼티는 이러한 기본 동작을 제어하기 위한 프로퍼티이다.
프로퍼티 값 | line break | space/ tab | wrapping(자동줄바꿈)
normal	        무시	     1번만 반영	         O
nowrap	        무시	     1번만 반영	         X
pre	            반영	     그대로 반영	       X
pre-wrap	      반영	     그대로 반영	       O
pre-line	      반영	     1번만 반영	         O
text-overflow 프로퍼티: 부모 영역을 벗어난 wrapping(자동줄바꿈)이 되지 않은 텍스트의 처리 방법을 정의한다. 이 프로퍼티를 사용하기 위해서는 아래의 조건이 필요하다.
- width 프로퍼티가 지정되어 있어야 한다. 이를 위해 필요할 경우 block 레벨 요소로 변경하여야 한다.
- 자동 줄바꿈을 방지하려면 white-space 프로퍼티를 nowrap으로 설정한다.
- overflow 프로퍼티에 반드시 “visible” 이외의 값이 지정되어 있어야 한다.
text-overflow 프로퍼티에 설정할 수 있는 프로퍼티 값은 아래와 같다.
- clip	영역을 벗어난 텍스트를 표시하지 않는다. (기본값)
- ellipsis	영역을 벗어난 텍스트를 잘라내어 보이지 않게 하고 말줄임표(…)를 표시한다.
word-wrap 프로퍼티: 한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다. link 등을 표기할 때(e.g. https://poiemaweb.com/css3-font-text) 그 길이가 매우 길어지는데 이 프로퍼티를 사용하지 않으면 부모 영역을 넘어가게 된다.
word-break 프로퍼티: 한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다. word-wrap 프로퍼티는 단어를 어느 정도는 고려하여 개행하지만(.,- 등을 고려한다) word-break: break-all;는 단어를 고려하지 않고 부모 영역에 맞추어 강제 개행한다.

8. 요소의 위치 정의
position 프로퍼티: position 프로퍼티는 요소의 위치를 정의한다. top, bottom, left, right 프로퍼티와 함께 사용하여 위치를 지정한다.
- static (기본위치): static은 position 프로퍼티의 기본값으로 position 프로퍼티를 지정하지 않았을 때와 같다. 기본적인 요소의 배치 순서에 따라 위에서 아래로, 왼쪽에서 오른쪽으로 순서에 따라 배치되며 부모 요소 내에 자식 요소로서 존재할 때는 부모 요소의 위치를 기준으로 배치된다. 기본적으로 이 값을 지정할 일은 없지만 이미 설정된 position을 무력화하기 위해 사용될 수 있다. 좌표 프로퍼티(top, bottom, left, right)를 같이 사용할 수 없으며 사용할 경우에는 무시된다.
- relative (상대위치): 기본 위치(static으로 지정되었을 때의 위치)를 기준으로 좌표 프로퍼티(top, bottom, left, right)를 사용하여 위치를 이동시킨다. static을 선언한 요소와 relative를 선언한 요소의 차이점은 좌표 프로퍼티의 동작 여부뿐이며 그외는 동일하게 동작한다.
- absolute (절대위치): 부모 요소 또는 가장 가까이 있는 조상 요소(static 제외)를 기준으로 좌표 프로퍼티(top, bottom, left, right)만큼 이동한다. 즉, relative, absolute, fixed 프로퍼티가 선언되어 있는 부모 또는 조상 요소를 기준으로 위치가 결정된다. 만일 부모 또는 조상 요소가 static인 경우, document body를 기준으로 하여 좌표 프로퍼티대로 위치하게 된다. 따라서 부모 요소를 배치의 기준으로 삼기 위해서는 부모 요소에 relative를 정의하여야 한다.
이때 다른 요소가 먼저 위치를 점유하고 있어도 뒤로 밀리지 않고 덮어쓰게 된다. (이런 특성을 부유 또는 부유 객체라 한다)
absolute 선언 시, block 레벨 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.
relative 프로퍼티와 absolute 프로퍼티의 차이점은 아래와 같다.
relative 프로퍼티는 기본 위치(static으로 지정되었을 때의 위치)를 기준으로 좌표 프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킨다. 따라서 무조건 부모를 기준으로 위치하게 된다.
absolute 프로퍼티는 부모에 static 이외의 position 프로퍼티가 지정되어 있을 경우에만 부모를 기준으로 위치하게 된다. 만일 부모, 조상이 모두 static 프로퍼티인 경우, document body를 기준으로 위치하게 된다.
따라서 absolute 프로퍼티 요소는 부모 요소의 영역을 벗어나 자유롭게 어디든지 위치할 수 있다.
- fixed (고정위치): 부모 요소와 관계없이 브라우저의 viewport를 기준으로 좌표프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킨다. 스크롤이 되더라도 화면에서 사라지지 않고 항상 같은 곳에 위치한다.
fixed 프로퍼티 선언 시, block 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.
z-index 프로퍼티: z-index 프로퍼티에 큰 숫자값을 지정할수록 화면 전면에 출력된다. positon 프로퍼티가 static 이외인 요소에만 적용된다.
overflow 프로퍼티: overflow 프로퍼티는 자식 요소가 부모 요소의 영역를 벗어났을 때 처리 방법을 정의한다.
- visible	영역을 벗어난 부분을 표시한다. (기본값)
- hidden	영역을 벗어난 부분을 잘라내어 보이지 않게 한다.
- scroll	영역을 벗어난 부분이 없어도 스크롤 표시한다.(현재 대부분 브라우저는 auto과 동일하게 작동한다)
- auto	영역을 벗어난 부분이 있을때만 스크롤 표시한다.
특정 방향으로만 스크롤을 표시하고자 할 때는 overflow-x 또는 overflow-y 프로퍼티를 사용한다.

9. 요소 정렬
float 프로퍼티는 주로 레이아웃을 구성할 때 블록 레벨 요소를 가로 정렬하기 위해 사용되는 중요한 기법이다. flexbox 레이아웃를 사용한다면 더욱 간단하게 정렬을 구현할 수도 있지만 flexbox 레이아웃을 지원하지 않는 IE를 고려해야 한다면 float 프로퍼티를 사용해야 한다. float 프로퍼티는 본래 이미지와 텍스트가 있을 때, 이미지 주위를 텍스트로 감싸기 위해 만들어진 것이다.
float 프로퍼티는 해당 요소를 다음 요소 위에 떠 있게(부유하게) 한다. 여기서 떠 있다(float)는 의미는 요소가 기본 레이아웃 흐름에서 벗어나 요소의 모서리가 페이지의 왼쪽이나 오른쪽에 이동하는 것이다. float 프로퍼티를 사용할 때 요소의 위치를 고정시키는 position 프로퍼티의 absolute를 사용하면 안된다.
- None	요소를 떠 있게 하지 않는다. (기본값)
- right	요소를 오른쪽으로 이동시킨다 
- left	요소를 왼쪽으로 이동시킨다.
정렬: float 프로퍼티를 사용하지 않은 블록 요소들은 수직으로 정렬된다. float:left; 프로퍼티를 사용하면 왼쪽부터 가로 정렬되고, float:right; 프로퍼티를 사용하면 오른쪽부터 가로 정렬된다.
오른쪽 가로 정렬의 경우, 먼저 기술된 요소가 가장 오른쪽에 출력되므로 출력 순서가 역순이 된다.
float 프로퍼티는 좌측, 우측 가로 정렬만 할 수 있다. 중앙 가로 정렬은 margin 프로퍼티를 사용해야 한다.
width: width 프로퍼티의 기본값은 100%이므로 width 프로퍼티값을 지정하지 않은 block 요소는 부모 요소의 가로폭을 가득 채운다.
width 프로퍼티를 선언하지 않은 block 레벨 요소에 float 프로퍼티가 선언되면 width가 inline 요소와 같이 content에 맞게 최소화되고 다음 요소 위에 떠 있게(부유하게) 된다.
위 예제를 살펴보면 d1 클래스 요소에는 float: left;를 선언하였고 d2 클래스 요소에는 float를 선언하지 않았다. 이때 d1 클래스 요소는 width가 inline 요소와 같이 content에 맞게 최소화되고 다음 요소인 d2 클래스 요소 위에 떠 있게(부유하게) 된다.
주의할 것은 d1 클래스 요소가 d2 클래스 요소 위에 떠 있게 되어도 d2 클래스 요소의 width는 d1 클래스 요소가 차이한 width만큼 줄어들지 않고 100%를 유지한다는 것이다. 이는 d2 클래스 요소는 float를 선언하지 않았기 때문에 본래의 width를 유지하기 때문이다. 따라서 d2 클래스 요소는 본래의 width(100%)를 유지한 상태에서 d1 클래스 요소가 그 위에 위치한다.
float 프로퍼티 관련 문제 해결 방법: 
- float 프로퍼티가 선언된 요소와 float 프로퍼티가 선언되지 않은 요소간 margin이 사라지는 문제: 
위 예제를 보면 두 요소는 차례대로 정렬된 것처럼 보이지만 사실은 float 프로퍼티가 선언된 요소가 다음 요소 위에 떠 있는(부유하고 있는) 상태이다. 따라서 두 요소간의 margin은 제대로 표현되지 않는다.
이것은 두번째 요소에 float 프로퍼티를 선언하지 않았기 때문에 발생하는 박스 모델 상의 문제이다. 이 문제를 해결하는 가장 쉬운 방법은 float 프로퍼티를 선언하지 않은 요소(.d2)에 overflow: hidden 프로퍼티를 선언하는 것이
overflow: hidden 프로퍼티는 자식 요소가 부모 요소의 영역보다 클 경우 넘치는 부분을 안보이게 해주는 역할을 하는데 여기서는 float 프로퍼티가 없어서 제대로 표현되지 못하는 요소를 제대로 출력해준다.
두번째 요소에도 float 프로퍼티를 선언하면 overflow: hidden 프로퍼티는 선언하지 않아도 되지만 너비가 최소화된다.
- float 프로퍼티가 선언된 자식 요소를 포함하는 부모 요소의 높이가 정상적으로 반영되지 않는 문제: 
아래 예제를 보면 float 프로퍼티가 선언된 두개의 자식 요소를 포함하는 부모 요소의 높이가 정상적인 값을 가지지 못하는 문제가 발생한다. float 요소는 일반적인 흐름 상에 존재하지 않기 때문에 float 요소의 높이를 알 수 없기 때문인데 이 문제는 부모 요소 이후에 위치하는 요소의 정렬에 문제를 발생시킨다.
이 문제를 해결하는 가장 쉬운 방법은 float 프로퍼티가 선언된 자식 요소의 부모 요소(.container)에 overflow: hidden 프로퍼티를 선언하는 것이다.
다른 방법으로 부모 요소(.container)에 float 프로퍼티를 선언하는 방법도 있다. 하지만 부모 요소의 너비는 float된 두개의 자식요소의 콘텐츠를 표현할 수 있는 만큼만으로 작게 줄어들게 된다. 권장할 수 있는 방법은 아니다.
container 영역이 끝나기 직전 빈 요소를 만들고 clear:both를 설정하는 방법도 가능하다. 하지만 의미 없는 빈 요소를 사용하여야 하기 때문에 이 방법 역시 권장할 수 있는 방법은 아니다.
overflow: hidden;과 함께 많이 사용되는 방법은 ::after 가상 요소 선택자를 이용하는 것이다. 가상 요소 선택자는 CSS2 문법(:after)과 CSS3 문법(::after)이 있는데 IE8까지 지원하는 CSS2 문법을 사용하는 편이 좋다.
부모 요소에 위 예제와 같이 사전에 작성한 clearfix 클래스만 추가하거나, 해당 요소를 선택하여 클리어 문법을 선언하면 되기 때문에 가장 깔끔하고 간편하다. 이 방법을 사용하는 것을 추천한다.
또 다른 방법은 float 프로퍼티 대신 display: inline-block;을 선언하는 것이다. 주의해야야 점은 inline-block 프로퍼티 요소를 연속 사용하는 경우, 두 요소 사이에 정의하지 않은 공백(4px)가 자동 지정되는 것이다.
위 예제를 보면 .d1, .d2 요소에 display: inline-block;을 선언하여 텍스트와 같이 배치되도록 하였지만 두 요소 사이에 정의하지 않은 공백(4px)이 자동 지정되어 부모 요소의 width를 초과하여 가로 정렬이 되지 않았다.
이 현상을 회피하기 위해 부모 요소에 font-size: 0;을 선언하여 두 요소 사이에 정의하지 않은 공백을 제거한다.
좀 더 자세한 회피 방법은 https://css-tricks.com/fighting-the-space-between-inline-block-elements/를 참조하기 바란다.

10. 스타일의 상속과 적용 우선 순위
상속(Inheritance): 상속이란 상위(부모, 조상) 요소에 적용된 프로퍼티를 하위(자식, 자손) 요소가 물려 받는 것을 의미한다. 상속 기능이 없다면 각 요소의 Rule set에 프로퍼티를 매번 각각 지정해야 한다.
하지만 모든 프로퍼티가 상속되는 것은 아니다. 프로퍼티 중에는 상속이 되는 것과 되지 않는 것이 있다.(https://poiemaweb.com/css3-inheritance-cascading)
color는 상속되는 프로퍼티로서 자식 요소는 물론 자손 요소까지 적용된다. 하지만 button처럼 요소에 따라 상속 받지 않는 경우도 존재한다.
border, padding은 상속되지 않는 요소로 하위 요소에 적용되지 않는다. W3C가 제공하는 Full property table의 Inherited?가 yes인 프로퍼티만 상속된다 
상속되지 않는 경우(상속받지 않는 요소 또는 상속되지 않는 프로퍼티), inherit 키워드를 사용하여 명시적으로 상속받게 할 수 있다.
캐스캐이딩(Cascading): 요소는 하나 이상의 CSS 선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위해 CSS 적용 우선순위가 필요한데 이를 캐스캐이딩(Cascading Order)이라고 한다.
캐스캐이딩에는 다음과 같이 세가지 규칙이 있다.
- 중요도: CSS가 어디에 선언 되었는지에 따라서 우선순위가 달라진다.
- 명시도: 대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
- 선언순서: 선언된 순서에 따라 우선 순위가 적용된다. 즉, 나중에 선언된 스타일이 우선 적용된다.
중요도: CSS가 어디에 선언 되었는지에 따라서 우선순위가 달라진다.
1. head 요소 내의 style 요소
2. head 요소 내의 style 요소 내의 @import 문
3. <link> 로 연결된 CSS 파일
4. <link> 로 연결된 CSS 파일 내의 @import 문
5. 브라우저 디폴트 스타일시트
명시도: 대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
!important > 인라인 스타일 > 아이디 선택자 > 클래스/어트리뷰트/가상 선택자 > 태그 선택자 > 전체 선택자 > 상위 요소에 의해 상속된 속성
선언순서: 선언된 순서에 따라 우선 순위가 적용된다. 즉, 나중에 선언된 스타일이 우선 적용된다.

11. 벤더 프리픽스
CSS3 표준으로 확정되기 이전 또는 브라우저 개발사가 실험적으로 제공하는 기능을 사용하기 위해서는 벤더 프리픽스(Vendor Prefix)를 사용하여야 한다.
Can I use?에서 제공하는 브라우저별 CSS 지원 정보를 보면 텍스트와 요소의 선택을 방지하는 user-select 프로퍼티는 모든 브라우저에 벤더 프리픽스를 사용하여야 한다. 브라우저의 버전이 올라감에 따라 벤더 프리픽스를 사용하지 않아도 될 수 있다. 그러나 구형 브라우저를 지원하기 위하여 벤더 프리픽스를 사용하여야 할 필요가 있다.
브라우저 별 벤더 프리픽스는 다음과 같다.(https://poiemaweb.com/css3-vendor-prefix)
많은 브라우저를 위한 벤더 프리픽스를 사용하는 것은 코드의 양을 늘게 하고 또한 브라우저는 거의 매달 업데이트가 이루어지고 있어 불필요한 벤더 프리픽스를 사용할 가능성이 크다. 사용하지 않아도 되는 벤더 프리픽스를 사용하는 것은 성능에도 영향을 주기 때문에 Prefix Free 라이브러리 를 사용하는 것은 매우 유용한 방법이다.
사용법은 매우 간단하다. Prefix Free 사이트에서 라이브러리를 다운로드하고 include 하기만 하면 이 후에는 벤더 프리픽스없이 모든 CSS를 사용할 수 있다.

12. 그림자
텍스트나 요소에 그림자(Shadow) 효과를 부여하기 위한 프로퍼티를 선언한다.
text-shadow: 텍스트에 그림자 효과를 부여하는 프로퍼티이다.
선택자 { text-shadow: Horizontal-offset Vertical-offset Blur-Radius Shadow-Color; }
Horizontal-offset	px	그림자를 텍스트의 오른쪽으로 지정값만큼 이동시킨다
Vertical-offset	px	그림자를 텍스트의 아래로 지정값만큼 이동시킨다 
Blur-Radius	px	그림자의 흐림정도를 지정한다. 지정값만큼 그림자가 커지고 흐려진다. (양수) (생략가능)
Shadow-Color	color	그림자의 색상을 지정한다 (생략가능)
box-shadow: 요소에 그림자 효과를 부여하는 프로퍼티이다.
선택자 { box-shadow: Inset Horizontal-offset Vertical-offset Blur-Radius Spread Shadow-Color; }
Inset	inset	inset 키워드를 지정하면 그림자가 요소 안쪽에 위치한다.	생략가능
Horizontal-offset	px	그림자를 텍스트의 오른쪽으로 지정값만큼 이동시킨다	 
Vertical-offset	px	그림자를 텍스트의 아래로 지정값만큼 이동시킨다	 
Blur-Radius	px	그림자의 흐림정도를 지정한다. 지정값만큼 그림자가 커지고 흐려진다. (양수)	생략가능
Spread	px	그림자를 더 크게 확장시킨다. (음수, 양수)	생략가능
Shadow-Color	color	그림자의 색상을 지정한다	생략가능

13. 그레이디언트
그레이디언트(Gradient)는 2가지 이상의 색상을 혼합하여 부드러운 색감의 배경 등을 생성하는 것이다. CSS3가 이 기능을 제공하기 이전에는 포토샵 등의 소프트웨어를 사용하여 그레이디언트 효과의 이미지를 제작하여 사용하였다. 그러나 이러한 방법은 이미지 다운로드에 시간이 소요되는 문제와 이미지를 확대하였을 때 해상도가 나빠지는 문제 등을 내포하고 있었다.
그레이디언트는 2가지 종류가 있다.
- 선형 그레이디언트 (Linear Gradient: goes down/up/left/right/diagonally)
- 방사형 그레이디언트 (Radial Gradient: defined by their center)
그레이디언트는 CSS3가 비교적 최근부터 제공하는 기술로서 대부분의 브라우저에 벤더프리픽스를 사용하여야 하고 브라우저에 따라 조금씩 문법이 상이하여 다루기가 수월하지 않다. 따라서 그레이디언트를 직접 작성하는 것보다 작성 툴을 이용하는 것이 보편적이다.(https://www.colorzilla.com/gradient-editor/)

14. 트랜지션
트랜지션(transition)은 CSS 프로퍼티의 값이 변화할 때, 프로퍼티 값의 변화가 일정 시간(duration)에 걸쳐 일어나도록 하는 것이다. 예를 들어 아래의 예제를 살펴보자. div 요소는 기본 상태에서 hover 상태로 변화할 때, CSS 프로퍼티 border-radius와 background 프로퍼티의 값이 변화한다.
상태 변화에 따라 CSS 프로퍼티가 변경되면 프로퍼티 변경에 따른 표시의 변화(transition)는 지체없이 즉시 발생한다. 위 예제의 경우, div 요소에 마우스가 올라가서 hover 상태가 되면 div 요소의 border-radius, background 프로퍼티의 값이 즉시 변경된다.
트랜지션(transition)은 상태 변화에 동반하여 변경되는 CSS 프로퍼티 값에 의한 표시의 변화를 부드럽게 하기 위해 애니메이션 속도를 조절한다. 즉, 프로퍼티 값의 변경이 표시의 변화에 즉시 영향을 미치게 하는 대신 그 프로퍼티 값의 변화가 일정 시간(duration)에 걸쳐 일어나도록 하는 것이다.
위 예제에 트랜지션 효과를 부여해 보자.
위 예제에서는 div 요소에 마우스가 올라갈 때(hover on)와 마우스가 내려올 때(hover off) border-radius, background 프로퍼티 값의 변화가 발생한다. 그리고 이들 프로퍼티 값의 변화를 2초에 걸쳐 이루어지도록 설정한 것이다.
div 셀렉터의 룰셋에 트랜지션을 설정하면 마우스가 올라갈 때(hover on)와 마우스가 내려올 때(hover off) 모두 트랜지션이 발동한다. 하지만 div:hover 셀렉터의 룰셋에 트랜지션을 설정하면 마우스가 올라갈 때(hover on)는 트랜지션이 발동하지만 마우스가 내려올 때(hover off)는 트랜지션이 발동하지 않는다.
transition은 자동으로 발동되지 않는다. :hover와 같은 가상 클래스 선택자(Pseudo-Classes) 또는 JavaScript의 부수적인 액션에 의해 발동한다. 위 예제의 div 요소에 적용된 트랜지션은 이와 같은 부수적 액션없이는 어떤 효과도 볼 수 없다.
만약 트랜지션이 자동 발동(self-invoking transition)하도록 하고 싶다면 CSS 애니메이션을 사용하도록 한다.
transition의 프로퍼티는 아래와 같다.
- transition-property	트랜지션의 대상이 되는 CSS 프로퍼티를 지정한다	기본값: all
- transition-duration	트랜지션이 일어나는 지속시간(duration)을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다	기본값: 0s
- transition-timing-function	트랜지션 효과를 위한 수치 함수를 지정한다. 기본값: ease
- transition-delay	프로퍼티가 변화한 시점과 트랜지션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다	기본값: 0s
- transition	모든 트랜지션 프로퍼티를 한번에 지정한다 (shorthand syntax)
- transition-property: transition-property 프로퍼티는 트랜지션의 대상이 되는 CSS 프로퍼티명을 지정한다. 지정하지 않는 경우 모든 프로퍼티가 트랜지션의 대상이 된다. 복수의 프로퍼티를 지정하는 경우 쉼표(,)로 구분한다.
주의해야 할 사항은 모든 CSS 프로퍼티가 트랜지션의 대상이 될 수 없다는 것이다. 예를 들어 width, font-size, background-color 등은 하나의 범주(width, font-size는 크기, background-color는 색상)안에서 값이 변화하지만 display 프로퍼티는 그렇지 않다.
트랜지션의 대상이 될 수 있는 CSS 프로퍼티는 다음과 같다.
// Box model
width height max-width max-height min-width min-height
padding margin
border-color border-width border-spacing
// Background
background-color background-position
// 좌표
top left right bottom
// 텍스트
color font-size font-weight letter-spacing line-height
text-indent text-shadow vertical-align word-spacing
// 기타
opacity outline-color outline-offset outline-width
visibility z-index
또한 요소의 프로퍼티 값이 변화하면 브라우저는 프로퍼티 값의 변화에 영향을 받는 모든 요소의 기하값(위치와 크기)를 계산하여 layout 작업을 수행한다. 이것은 브라우저에게 스트레스를 주어 성능 저하의 요인이 된다. 심지어 다수의 자식 요소를 가지고 있는 요소(예를 들어 body 요소)가 변경되면 모든 자식 요소의 기하값이 재계산될 수도 있다. 따라서 layout에 영향을 주는 트랜지션 효과는 회피하도록 노력해야 한다.
width height padding margin border
display position float overflow
top left right bottom
font-size font-family font-weight
text-align vertical-align line-height
clear white-space
transition-duration: transition-duration 프로퍼티는 트랜지션에 일어나는 지속시간(duration)을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. 프로퍼티값을 지정하지 않을 경우 기본값 0s이 적용되어 어떠한 트랜지션 효과도 볼 수 없다.
transition-duration 프로퍼티값은 transition-property 프로퍼티값과 1:1 대응한다. 아래의 경우, width 프로퍼티는 2초의 지속시간을 갖는다(2초에 걸쳐 변화한다).
transition-timing-function: 트랜지션 효과의 변화 흐름, 시간에 따른 변화 속도와 같은 일종의 변화의 리듬을 지정한다.
대부분의 타이밍 함수는 큐빅 베이지어(cubic bezier)를 정의하는 네 점에 의해 정의되므로 상응하는 함수의 그래프로 제공해서 명시할 수 있다. transition-timing-function 프로퍼티값으로 미리 정해둔 5개의 키워드가 제공된다. 기본값은 ease이다.
ease	기본값. 느리게 시작하여 점점 빨라졌다가 느리지면서 종료한다.
linear	시작부터 종료까지 등속 운동을 한다.
ease-in	느리게 시작한 후 일정한 속도에 다다르면 그 상태로 등속 운동한다.
ease-out	일정한 속도의 등속으로 시작해서 점점 느려지면서 종료한다.
transition-delay: 프로퍼티가 변화한 시점과 트랜지션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. 즉, transition-delay로 대기 사간을 지정하여 프로퍼티의 값이 변화하여도 즉시 트랜지션이 실행되지 않고, 일정 시간 대기한 후 트랜지션이 실행되도록 한다.
transition: 모든 트랜지션 프로퍼티를 한번에 지정할 수 있는 shorthand이다. 값을 지정하지 않은 프로퍼티에는 기본값이 지정된다. 지정 방법은 다음과 같다.
transition: property duration function delay
transition-duration은 반드시 지정해야 한다. 지정하지 않는 경우 기본값 0이 셋팅되어 어떠한 트랜지션도 실행되지 않는다. 기본값은 아래와 같다.
all 0 ease 0

15. 애니메이션
애니메이션(Animation) 효과는 HTML 요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 변화시킨다. 애니메이션은 애니메이션을 나타내는 CSS 스타일과 애니메이션의 sequence를 나타내는 복수의 키프레임(@keyframes) 들로 이루어진다
transition으로도 어느 정도의 애니메이션 효과를 표현할 수 있으나 animation보다는 제한적이다. 일반적으로 트랜지션 효과는 요소 프로퍼티값이 다른 값으로 변화할 때 주로 사용하며 요소의 로드와 함께 자동으로 발동되지 않는다. :hover 와 같은 가상 클래스 선택자(Pseudo-Class Selector) 또는 자바스크립트의 이벤트와 같은 부수적 액션에 의해 발동된다.
즉 transition 프로퍼티는 단순히 요소의 프로퍼티 변화에 주안점이 있다면 animation 프로퍼티는 하나의 줄거리를 구성하여 줄거리 내에서 세부 움직임을 시간 흐름 단위로 제어할 수 있고 전체 줄거리의 재생과 정지, 반복까지 제어할 수 있다.
일반적으로 CSS 애니메이션을 사용하면 기존의 JavaScript 기반 애니메이션 실행과 비교하여 더 나은 렌더링 성능을 제공한다고 알려져 있다. 그러나 경우에 따라서는 JavaScript를 사용하는 것이 나을 수도 있다. jQuery 등의 애니메이션 기능은 CSS보다 간편하게 애니메이션 효과를 가능케 한다.
- 비교적 작은 효과나 CSS만으로도 충분한 효과를 볼 수 있는 것은 CSS를 사용한다. 예를 들어 요소의 width 변경 애니메이션은 자바스크립트를 사용하는 것보다 훨씬 간편하며 효과적이다.
- 세밀한 제어를 위해서는 자바스크립트 사용이 바람직하다. 예를 들어 바운스, 중지, 일시 중지, 되감기 또는 감속과 같은 고급 효과는 자바스크립트가 훨씬 유용하다.
가장 중요한 것은 브라우저에서 애니메이션 효과가 부드럽게 실행되는 것이다. 그리고 애니메이션 효과 작성에 소요되는 시간과 수고이다. 여러 사항들을 고려하여 자바스크립트를 사용하여야 할지 CSS를 사용하여야 할지 결정하여야 한다.
animation-name	@keyframes 애니메이션 이름을 지정한다
animation-duration	한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다.	기본값: 0s
animation-timing-function	애니메이션 효과를 위한 타이밍 함수를 지정한다.	기본값: ease
animation-delay	요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다	기본값: 0s
animation-iteration-count	애니메이션 재생 횟수를 지정한다.	기본값: 1
animation-direction	애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정한다.	기본값: normal
nimation-fill-mode	애니메이션 미실행 시(종료 또는 대기) 요소의 스타일을 지정한다.
animation-play-state	애니메이션 재생 상태(재생 또는 중지)를 지정한다.	기본값: running
animation	모든 애니메이션 프로퍼티를 한번에 지정한다 (shorthand syntax)
1. @keyframes: CSS 애니메이션과 트랜지션 방식의 주된 차이는 @keyframes rule에 있다. 이 rule을 사용하면 애니메이션의 흐름(sequence) 중의 여러 시점(breakpoint)에서 CSS 프로퍼티값을 지정할 수 있다.
@keyframes rule은 시간의 흐름에 따라 애니메이션을 정의한다. 여러 개의 키프레임을 정의하거나 애니메이션 중에 특정 CSS 프로퍼티에 값을 지정하는 지점을 정의할 수 있다.
위 예제를 보면 @keyframes 뒤에 애니메이션을 대표하는 임의의 이름를 부여하였다.
from, to 키워드를 사용하여 애니메이션의 시작과 끝 시점을 정의하였다. 그리고 애니메이션의 시작 시점을 의미하는 from 키프레임 내에는 left 프로퍼티에 값 0을, 애니메이션의 끝 시점을 의미하는 to 키프레임 내에는 left 프로퍼티에 값 300px을 지정하였다. 그 결과, 정지 상태에서 오른쪽으로 300px 이동하는 애니메이션이 실행된다.
from, to 키워드 대신 %를 사용할 수 있다. 또한 시작과 끝 키프레임 사이에 % 단위로 키프레임을 삽입할 수 있다.
2. animation-name: 위 예제를 보면 @keyframes 뒤에 애니메이션을 대표하는 임의의 이름를 부여하였다.
이 이름을 animation-name 프로퍼티값으로 지정하여 사용하고자 하는 @keyframes rule을 선택한다. 하나 이상의 애니메이션 이름을 지정할 수 있다.
3. animation-duration: 한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다.
animation-duration은 반드시 지정해야 한다. 지정하지 않는 경우 기본값 0s가 셋팅되어 어떠한 애니메이션도 실행되지 않는다.
4. animation-timing-function: 애니메이션 효과를 위한 수치 함수를 지정한다. 수치 함수에 대한 설명은 트랜지션 transition-timing-function 프로퍼티를 참조하기 바란다.
5. animation-delay: 요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다.
6. animation-iteration-count: 애니메이션 주기의 재생 횟수를 지정한다. 기본값은 1이며 infinite로 무한반복 할 수 있다.
7. animation-direction: 애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정한다.
normal	기본값으로 from(0%)에서 to(100%) 방향으로 진행한다.
reverse	to에서 from 방향으로 진행한다.
alternate	홀수번째는 normal로, 짝수번째는 reverse로 진행한다.
alternate-reverse	홀수번째는 reverse로, 짝수번째는 normal로 진행한다.
8. animation-fill-mode: 애니메이션 미실행 시(대기 또는 종료) 요소의 스타일을 지정한다.
none	대기	시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
      종료	애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.
forwards	대기	시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
 	        종료	종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.
backwards	대기	시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
 	        종료	애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.
both	대기	시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
 	    종료	종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.        
9. animation-play-state: 애니메이션 재생 상태(재생 또는 중지)를 지정한다. 기본값은 running이다.
10. animation: 모든 애니메이션 프로퍼티를 한번에 지정한다. 값을 지정하지 않은 프로퍼티에는 기본값이 지정된다. 지정 방법은 다음과 같다.
animation: name duration timing-function delay iteration-count direction fill-mode play-state   
animation-duration은 반드시 지정해야 한다. 지정하지 않는 경우 기본값 0s가 셋팅되어 어떠한 애니메이션도 실행되지 않는다. 기본값은 아래와 같다.
none 0 ease 0 1 normal none running

16. 트랜스폼
트랜지션은 CSS 스타일 변경을 부드럽게 표현하기 위해 duration(지속시간)을 부여하여 속도를 조절한다.
애니메이션은 하나의 줄거리(@keyframes)를 구성하여 줄거리 내에서 세부 움직임을 시간 흐름 단위로 제어하여 요소의 움직임을 표현한다.
트랜스폼(Transform)은 요소에 이동(translate), 회전(rotate), 확대축소(scale), 비틀기(skew) 효과를 부여하기 위한 함수를 제공한다. 단 애니메이션 효과를 제공하지는 않기 때문에 정의된 프로퍼티가 바로 적용되어 화면에 표시된다. 트랜스폼은 애니메이션 효과를 위해 사용하여야 하는 것은 아니지만 애니메이션 효과를 부여할 필요가 있다면 트랜지션이나 애니메이션과 함께 사용한다.
1. 2D 트랜스폼 (2D Transform): 2D 트랜스폼은 프로퍼티값으로 변환함수(transform function)를 사용한다. 변환함수는 다음과 같다.
- translate(x,y)	요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동시킨다.	px, %, em 등
- translateX(n)	요소의 위치를 X축으로 x만큼 이동시킨다.	px, %, em 등
- translateY(n)	요소의 위치를 Y축으로 y만큼 이동시킨다.	px, %, em 등
- scale(x,y)	요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다.	0과 양수
- scaleX(n)	요소의 크기를 X축으로 x배 확대 또는 축소 시킨다.	0과 양수
- scaleY(n)	요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다.	0과 양수
- skew(x-angle,y-angle)	요소를 X축으로 x 각도만큼, Y축으로 y 각도만큼 기울인다.	+/- 각도(deg)
- skewX(x-angle)	요소를 X축으로 x 각도만큼 기울인다.	+/- 각도(deg)
- skewY(y-angle)	요소를 Y축으로 y 각도만큼 기울인다.	+/- 각도(deg)
- rotate(angle)	요소를 angle만큼 회전시킨다.	+/- 각도(deg)
1.1 transform: 변환함수를 프로퍼티값으로 쉼표없이 나열한다. 나열순서에 따라 차례대로 효과가 적용된다.
transform: func1 func2 func3 ...;
1.2 transform-origin: 요소의 기본기준점을 설정할 때 사용된다. 기본기준점은 요소의 정중앙이다(50%,50%). 이동은 기준점을 변경하여도 일정 거리만큼 이동하므로 의미가 없다. 설정값으로 %, px, top left, bottom right을 사용할 수 있다. 0, 0은 top left, 100% 100%는 bottom right과 같은 값이다.
2. 3D 트랜스폼 (3D Transform): 3D 트랜스폼은 프로퍼티값으로 변환함수(transform function)를 사용한다. 사용할 수 있는 변환함수는 다음과 같다.
translate3d(x,y,z)	요소의 위치를 X축으로 x만큼, Y축으로 y만큼 Z축으로 z만큼 이동시킨다.	px, %, em 등
translateX(n)	요소의 위치를 X축으로 x만큼 이동시킨다.	px, %, em 등
translateY(n)	요소의 위치를 Y축으로 y만큼 이동시킨다.	px, %, em 등
translateZ(n)	요소의 위치를 Z축으로 z만큼 이동시킨다.	px, %, em 등
scale3d(x,y)	요소의 크기를 X축으로 x배, Y축으로 y배, Z축으로 z배 확대 또는 축소 시킨다.	0과 양수
scaleX(n)	요소의 크기를 X축으로 x배 확대 또는 축소 시킨다.	0과 양수
scaleY(n)	요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다.	0과 양수
scaleZ(n)	요소의 크기를 Z축으로 z배 확대 또는 축소 시킨다.	0과 양수
rotate3d(x,y,z)	요소를 X축으로 x각도, Y축으로 y각도, Z축으로 z각도 회전시킨다.	+/- 각도(deg)
rotateX(x)	요소를 X축으로 x각도 회전시킨다.	+/- 각도(deg)
rotateY(y)	요소를 Y축으로 y각도 회전시킨다.	+/- 각도(deg)
rotateZ(z)	요소를 Z축으로 z각도 회전시킨다.	+/- 각도(deg)

17. 웹디자인 타이포그래피(Typography)
웹디자인 관점에서 폰트의 선택은 중요한 의미를 갖는다. 대부분의 정보는 텍스트와 이미지로 전달되고 아직은 텍스트가 주를 이루기 때문에 더욱 그러하다. 이전에는 웹에서 사용할 수 있는 아름다운 한글 폰트가 적어 포토샵 등으로 로컬 폰트를 사용하여 텍스트를 이미지로 만들어 사용하였다. 이것은 많은 트래픽을 유발하고 웹크롤러가 정보를 수집할 수 없어 SEO관점에서도 바람직하지 않다. 아름답고 정돈된 폰트를 사용한다면 그 자체만으로도 훌륭한 웹디자인이 가능하다.웹 브라우저는 로컬 소프트웨어이므로 당연한 이야기이지만 로컬 환경의 리소스만 사용 가능하다. 폰트는 로컬 환경에 존재하는 리소스의 하나로 로컬 환경에 있지 않은 폰트는 사용할 수 없다.
웹페이지는 불특정 사용자를 위해 제작되기 때문에 어떤 디바이스의 어떤 OS를 사용하는 사용자가 웹페이지에 접근할 지 알 수 없다. 웹페이지를 구성하는 html, css, javascript 파일이 사용자의 요청에 의해 서버에서 클라이언트로 다운로드되어 실행되는 것과 같이 폰트 또한 서버에서 클라이언트로 다운로드되어 실행될 수 있다면 이 문제는 해결될 수 있다.
이러한 문제를 해결할 수 있는 방법이 바로 웹폰트이다. 웹폰트는 사용자가 웹페이지를 요청한 순간 CSS에 기술된 필요 폰트가 서버에서 클라이언트로 전송된다. 좀 더 구체적으로 말하면 매번 다운로드되는 것은 아니고 클라이언트에 해당 폰트가 존재하지 않을 경우 전송된다.
1. CDN(Content Delivery Network) 링크 방식: 웹폰트를 사용하는 방법 중 가장 간단한 방법은 CDN 링크를 사용하는 것이다. 다음은 구글에서 제공하는 웹폰트를 사용하는 방법이다.
Google Font 에서 사용하고자 하는 웹폰트를 선택한다. 한글 웹페이지에 자주 사용되는 나눔고딕은 Google Font Early Access에서 찾을 수 있다. 아래 구문을 CSS 파일에 추가한다.
@import url(http://fonts.googleapis.com/earlyaccess/nanumgothic.css);
* { font-family: 'Nanum Gothic', sans-serif; }
@import rule의 url 함수는 서버에서 혹은 지정된 url에서 파일을 찾아 다운로드한다.
2. 서버 폰트 로딩 방식: Google Font를 사용하기 위해 CDN 링크를 사용하는 방법은 간편한 방법이지만 로딩 속도가 느린 단점이 있다.(로컬 폰트를 사용하는 것에 비해 느리다는 의미이다. 서버 폰트 로딩 방식보다는 빠를수 있다.) 여러 개의 폰트를 사용한다면 로딩에 더욱 시간이 걸릴 것이다. 또한 CDN 링크를 제공하지 않는 폰트는 사용할 방법이 없다. 이러한 단점을 보완한 방법이 서버 폰트 로딩 방식이다.
폰트 파일을 서버에 두고 요청이 오면 클라이언트로 전송하는 방식이다. 하지만 문제는 여전히 존재한다. 브라우저에 따라 지원하는 폰트 파일 형식이 다르다는 문제가 있다.
아래 코드는 일반적으로 사용되는 검증된 웹폰트 사용 방법이다. 브라우저에 따라 필요한 폰트만을 다운로드할 수 있다.
영문과 한글을 혼용하는 경우 먼저 영문 폰트, 그 다음 한글 폰트를 지정하여야 한다. 한글 폰트부터 지정하면 영문에도 한글 폰트가 지정된다.

18. 레이아웃
이전에는 table을 사용하여 layout을 만들기도 하였으나 html과 css의 본연의 취지와도 맞지 않을 뿐더러 반응형 웹 페이지 작성이 곤란하며 코드의 양 또한 많아져 현재는 거의 사용하지 않는다. 모던한 웹 페이지는 style과 layout을 담당하는 CSS를 사용하여 layout을 구성하는 것이 바람직하다. layout의 핵심은 블록 레벨 요소들을 원하는 위치에 배열하는 것이다.
모바일 사용자가 데스크탑 사용자보다 많은 상황을 감안하여 화면의 크기에 따라 적절히 화면 구성을 변화시키는 반응형 웹 디자인(Responsive Web Design) 또한 모던 웹 사이트의 필수 사항이 되었다.
CSS를 사용하여 layout을 구성할 때에 자주 사용되는 핵심 기술은 float이다. 다음은 전형적인 웹사이트의 layout이다.

layout이란 웹사이트를 구성하는 요소들을 배치할 공간을 분할하고 정렬하는 것이다. 공간을 분할할 때는 먼저 행을 구분한 후, 행 내부 요소를 분리하는 것이 일반적이다.
아래 예제는 2 column layout의 일반적인 골격이다.
1. Header & Navigation Bar: 대부분의 웹사이트는 Navigation Bar를 가지고 있다. Navigation Bar는 웹사이트의 필수 구성 요소라고 할 수 있을 것이다.
Navigation Bar는 기본적으로 링크들의 리스트이다. 따라서 ul, li tag를 이용하여 작성하는 것이 일반적이다.
다음은 최소한의 Reset CSS를 추가한 링크들의 리스트이다. 주의할 점은 직관적인 box model을 위해 box-sizing: border-box;을 사용했다는 것이다.
실제 웹사이트를 구축할 시에는 Reset CSS를 좀 더 정교하게 초기화할 필요가 있다.
header 요소에 화면폭 만큼의 width와 고정 height를 지정한다. background-color와 box-shadow 효과를 추가한다.
이제 float 프로퍼티를 이용하여 Navigation bar를 우측정렬한다.
아래의 logo image를 수직으로 중앙 정렬한다.
logo image를 포함하는 a tag(.logo)의 height를 logo image와 같은 height인 36px로 지정하고 상하 margin을 12px씩 부여하면 logo 요소의 높이는 60px이 되고 header의 height와 같아져 이미지는 수직 중앙 정렬된다.
a tag는 inline 요소이므로 margin을 정의하기 위해서 display: inline-block;을 설정한다. 또한 img tag에 부여한 height 어트리뷰트를 css로 옮긴다.
수직 정렬되어 있는 Navigation bar를 수평 정렬한다. block 요소인 li에 display: inline-block;를 설정하여 inline 요소와 같이 가로로 정렬케 한다.
수평 정렬된 Navigation bar 수직 중앙 정렬한다. line-height: 60px;으로 텍스트의 높이를 header의 height와 동일하게 60px로 고정시킨다. 그리고 텍스트 간 적당한 간격 유지를 위해 padding을 정의한다.
마우스가 Navigation bar 위에 올라오면 Navigation item의 텍스트 색상이 변경되도록 한다.
아래는 완성된 Navigation bar의 예제 코드이다.
2. Section & Aside:  콘텐츠의 영역을 Section, 콘텐츠에 대한 Navigation item이나 부가 정보 영역을 Aside라 한다. Section 영역은 다시 article 영역으로 구분할 수 있다.
이 두개의 영역은 float 프로퍼티를 사용하여 수평 정렬하는 것이 일반적이다. header 요소 뒤에 aside, section, article을 포함하는 content-wrap 요소를 정의한다.
aside을 좌측정렬, section을 우측 정렬한다. 이때 float 프로퍼티 요소를 감싸는 wrap 요소에 clearfix을 부여하여 float 프로퍼티가 선언된 두개의 자식 요소를 포함하는 부모 요소의 높이가 정상적인 값을 가지지 못하는 문제를 해결해야 한다.
2개의 블록 영역이 수평 정렬되었고 wrap 요소도 정상적인 높이를 가지게 되었다. 그런데 아래 그림처럼 화면을 아래로 스크롤하면 header 영역도 따라 올라가 버려 navigation bar가 사라져 버리는 현상이 발생한다. navigation bar가 화면에 없으면 조작이 불편할 수 있으므로 navigation bar를 화면 상단에 고정시키도록 한다.
fixed 프로퍼티를 사용하여 header 요소를 상단에 고정시킨다.
fixed 프로퍼티은 부모 요소와 관계없이 브라우저의 viewport를 기준으로 좌표 프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킨다. 스크롤이 되더라도 화면에서 사라지지 않고 항상 같은 곳에 위치한다.
contents 영역 상단이 header 영역과 겹치므로 contents 영역을 header의 height 만큼 아래로 끌어 내린다.
다음은 aside navigation의 style을 정리한다. 현재 active한 item을 컬러로 구분할 수 있게 하고 마우스 hover상태일 때도 컬러로 구분할 수 있게 한다. 또한 텍스트의 style도 정리한다.
heading tag(h1)의 크기가 위치한 영역에 따라 다름에 주의하여야 한다. 즉, header내의 h1은 section내의 h1 보다 크다. 이것을 방지하기 위해서는 다음을 Rest CSS에 추가할 필요가 있다. 크기는 적당히 조절하면 된다. 다른 텍스트 태그의 style도 정리한다. 자세한 사항은 (https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) 참조
3. footer: content-wrap 영역 다음에 footer를 배치한다.
footer도 고정되어 있을 필요가 있지만 본문을 가리는 것은 곤란하다. 따라서 fixed 프로퍼티를 설정해서는 않된다. fixed 프로퍼티는 스크롤이 되어도 언제나 그자리를 고수하기 때문이다.
footer는 absolute 프로퍼티를 설정한다. absolute를 사용하면 다른 요소가 먼저 위치를 점유하고 있어도 뒤로 밀리지 않고 덮어쓰게 된다. (이런 특성을 부유 또는 부유 객체라 한다)
footer의 style 정의는 다음과 같다.
다음은 지금까지 작성한 예제의 전체 코드이다.
사실 위의 예제에는 몇가지 문제가 숨겨져 있다. 그 문제를 해결할 열쇠는 바로 Responsive Web Design이다.

19. 반응형 레이아웃
앞에서 살펴본 layout 에는 사실 몇가지 문제가 숨겨져 있다. 그 문제를 해결할 열쇠는 바로 Responsive Web Design이다.
먼저 어떤 문제가 있는지 알아본다. 화면폭을 좁히면 아래 그림과 같이 화면이 망가지는데 이것는 HTML 요소에 고정폭을 지정하여 가로 스크롤을 발생시키지 않으면 해결이 어렵다.
그리고 모바일과 같이 작은 해상도의 디바이스에서 접근했을 때 화면이 너무 작아져 가시성에 문제가 발생한다.
1. Responsive Web Design 개요
사용자가 어떤 디바이스로 웹사이트를 방문할 지 알 수 없다. layout은 방문자의 화면 해상도를 고려하여야 한다. 가로폭이 너무 큰 layout을 작성하면 작은 해상도 모니터로 방문하였을 때 가로 스크롤이 생겨서 사용이 불편할 수도 있다.
또한 스마트폰이나 태블릿 등 모바일 기기는 화면이 작기 때문에 가독성에 더욱 신경써야 한다. 보통 웹사이트가 축소되어 가로 스크롤 없이 콘텐츠를 볼 수 있으나 글자가 너무 작아지기 때문이다. 데스크탑용, 테블릿용, 모바일용 웹사이트를 별도 구축할 수도 있지만 One Source Multi Use의 관점에서 올바른 해결책은 아니다.
이러한 문제를 해결하는 방법 중의 하나가 반응형 웹디자인(Responsive Web Design)이다. 화면 해상도에 따라 가로폭이나 배치를 변경하여 가독성을 높이는 것이다. 즉, 하나의 웹사이트를 구축하여 다양한 디바이스의 화면 해상도에 최적화된 웹사이트를 제공하는 것이다.
또한 최근 모바일 웹페이지는 대부분 애플리케이션의 형태로 진화하고 있어 앱인지 웹인지 구분이 어려울 정도이다. HTML5/CSS3/Javascript만으로 네이티브 앱과 차이를 느낄 수 없는 앱을 만들 수 있다. 다음은 최근 관심을 끌고 있는 Web App Framework이다. ionic, Electron, PhoneGap, Sencha Touch
1.1 viewport meta tag
viewport란 웹페이지의 가시영역을 의미한다. viewport는 디바이스에 따라 차이가 있다. 예를 들어 모바일 브라우저는 주화면이 세로 화면이고 윈도우 resize가 불가하며 화면 터치를 사용하는 등 데스크탑 브라우저와 구성이나 형태가 다르다. 또한 모바일의 화면은 데스크탑 화면보다 훨씬 작으므로 데스크탑용 웹페이지를 그대로 모바일에 출력하면 가독성이 현저히 나빠진다. 따라서 viewport를 이용하여 디바이스의 특성과 디바이스의 화면 크기 등을 고려하여 각종 디바이스 사용자에게 최적화된 웹페이지를 제공할 수 있다.
meta tag는 브라우저 혹은 검색엔진최적화(SEO)를 위해 검색엔진에게 메타데이터를 전달하기 위해 사용된다.
viewport meta tag는 브라우저의 화면 설정과 관련된 정보를 제공한다
width	viewport 너비(px). 기본값: 980px	ex. width=240, width=device-width
height	viewport 높이(px)	ex. height=800, width=device-height
initial-scale	viewport초기 배율	ex. initial-scale=1.0
user-scale	확대 축소 가능 여부	ex. user-scale=no
maximum-scale	viewport 최대 배율	ex. maximum-scale=2.0
minimum-scale	viewport 최소 배율	ex. minimum-scale=1.0
meta tag에서는 px단위를 사용하며 단위 표현은 생략한다. 복수개의 프로퍼티를 사용할 때는 쉼표(,)로 구분한다.
일반적으로 viewport meta tag는 모바일 디바이스에서만 적용된다.
<meta name="viewport" content="width=device-width, initial-scale=1.0">
위 예제는 가장 일반적인 viewport 설정이다. 가로폭을 디바이스의 가로폭에 맞추고 초기 화면 배율을 100%로 설정하는 것을 의미한다.
1.2 @media
이것은 서로 다른 미디어 타입(print, screen…)에 따라 각각의 styles을 지정하는 것을 가능하게 한다. 다음은 일반 화면(screen)과 인쇄장치 별로 서로 다른 style을 지정하는 예이다.
반응형 웹디자인에 사용되는 핵심 기술은 @media이다.
@media을 사용하여 미디어 별로 style을 지정하는 것을 Media Query라 한다. 디바이스를 지정하는 것뿐만 아니라 디바이스의 크기나 비율까지 구분할 수 있다.
다음은 Media Query의 문법이다.
@media not|only mediatype and (expressions) {
  CSS-Code;
}
아래의 표는 Media Query의 표현식에서 사용할 수 있는 프로퍼티이다.
width	viewport 너비(px)
height	viewport 높이(px)
device-width	디바이스의 물리적 너비(px)
device-height	디바이스의 물리적 높이(px)
orientation	디바이스 방향 (가로 방향: landscape, 세로방향: portrait)
device-aspect-ratio	디바이스의 물리적 width/height 비율
color	디바이스에서 표현 가능한 최대 색상 비트수
monochrome	흑백 디바이스의 픽셀 당 비트수
resolution	디바이스 해상도
orientation을 제외한 모든 프로퍼티는 min/max 접두사를 사용할 수 있다.
일반적으로 반응형 웹 디자인은 viewport 너비(width 프로퍼티)를 기준으로 한다.
viewport의 width 프로퍼티를 이용하여 viewport 너비에 따라 반응하는 범위(breakpoint)를 지정할 수 있다.
다음은 임의로 해상도를 3단계로 구분하여 breakpoint를 정의한 예제이다.
다음은 화면이 세로일 때, 가로일 때를 구분하는 예제이다. 주의할 점은 데스크탑은 언제나 가로 화면이기 때문에 device-width로 스마트폰의 해상도를 지정하지 않으면 데스크탑에서도 가로화면 시 style이 적용되는 문제가 발생한다.
2. Responsive Navigation Bar
이제까지의 내용을 바탕으로 앞서 만들어본 예제를 Responsive Web Design에 맞추어 수정해 보자.
디바이스 해상도에 따라 반응할 수 있도록 viewport meta tag와 media query를 추가한다.
스마트폰, 태블릿, 데스크탑 그룹의 3단계로 구분하여 breakpoint를 정의하였다. Non Mobile First Method로 정의하였기 때문에 Media Query로 정의하지 않은 스타일은 데스크탑 그룹을 위한 코드가 된다.
최대 viewport width를 800px로 한정하였다는 것은 화면 크기가 800px 이하인 디바이스(태블릿)를 위한 정의란 의미가 된다. 위 예제 내에 정의 되는 스타일은 화면 크기가 800px 이하인 디바이스에서 웹사이트가 표시될 때 실행된다.
최대 viewport width를 480px로 한정하였다는 것은 화면 크기가 480px 이하인 디바이스(스마트폰)를 위한 정의란 의미가 된다. 위 예제 내에 정의 되는 스타일은 화면 크기가 480px 이하인 디바이스에서 웹사이트가 표시될 때 실행된다.
CSS 적용 우선 순위 (Cascading Order)에 따라 나중에 선언된 스타일이 우선 적용된다. 따라서 Media Query는 기술 순서에 의미가 있다. 만일 스마트폰용 스타일을 태블릿용 스타일보다 먼저 기술하면 최종적으로 태블릿용 스타일이 적용된다. 따라서 Non Mobile First 방식의 경우, max-width의 값이 큰 것부터 기술하여 한다.  
일반적으로 Mobile-first 방식은 해상도가 작은 순서로, Non Mobile-first 방식은 해상도가 큰 순서로 기술한다.
2.1 Responsive Navigation Bar - Tablet
데스크탑 layout에서 화면이 작아질 때 header navigation bar가 header 영역 아래로 내려오는 현상이 발생하였다. 이를 보완하기 위해 다음과 같이 태블릿에서의 layout을 정의한다.
viewport width가 800px 이하가 되면 header 영역을 2단(logo영역과 navigation bar영역)으로 구분하기 위하여 header 영역의 높이를 현재(60px)의 2배로 넓힌다. 그리고 logo image과 navigation bar를 centering한다.
이때 aside, section영역도 header의 height만큼 내려가야 한다.
가로로 나란히 정렬되어 있던 logo image과 navigation bar를 상단과 하단으로 분리 배치하기 위하여 navigation bar의 float: right; 프로퍼티를 해제한다. 그러면 navigation bar는 block 프로퍼티를 가지게 되어 logo image의 아래 영역으로 내려가게 된다.
2.2 Responsive Navigation Bar - Smartphone
태블릿 layout에서는 header 영역을 2단으로 분리하여 navigation bar는 header 하단 영역에 배치하였다. 하지만 스마트폰의 viewport width는 가로로 나란히 정렬되어 있는 navigation bar를 모두 담기에는 너무 좁다. 다음과 같이 스마트폰 layout을 정의한다.
우측 navigation icon을 클릭하면 navigation bar가 수직 정렬되어 화면에 나타나도록 한다. 한번 더 클릭하면 화면에서 사라지도록 한다. 이때 navigation icon에 animation 효과를 부여한다.
nav 요소 내에 클릭할 수 있는 navigation icon을 만들기 위한 html tag를 추가한다. label tag의 for 프로퍼티값과 input tag의 id 프로퍼티값이 일치하여야 한다.
위의 코드는 checkbox의 기본 외관을 사용하지 않고 커스텀 navigation icon을 사용하기 위한 방법이다.
input checkbox 요소의 id 프로퍼티값과 label 요소의 for 프로퍼티값을 일치시켜 연동하면 label 요소를 클릭하여도 input checkbox 요소가 클릭된다.
이것을 이용하여 label 요소의 콘텐츠를 커스텀 navigation icon으로 만들어 주고 input checkbox 요소의 기본 외관을 비표시하는 방법이다.
navigation icon은 input checkbox 요소와 연동되어야 하므로 label 요소를 사용하였다. 즉, navigation icon을 클릭하면 checkbox input tag도 checked 상태가 된다.
navigation icon의 style은 다음과 같이 정의한다.
navigation icon은 header 우측의 절대 위치에 배치되어야 하므로 position: absolute;를 지정한다.
absolute 프로퍼티는 부모 요소 또는 가장 가까이 있는 조상 요소(static 제외)를 기준으로 좌표 프로퍼티(top, bottom, left, right)만큼 이동한다. 즉, relative, absolute, fixed 프로퍼티가 선언되어 있는 부모 또는 조상 요소를 기준으로 위치가 결정된다. 만일 부모 또는 조상 요소가 static인 경우, document body를 기준으로 하여 좌표 프로퍼티대로 위치하게 된다.
이 경우, navigation icon은 body를 기준으로 위치하면 되므로 부모 요소에 별도의 처리가 필요없다.
다음은 label tag 내의 span tag의 style을 정의한다. span tag는 navigation icon의 내부 막대 3개(클릭 시에는 X 표시)를 표현하기 위해 정의하였다.
위 그림과 같이 navigation icon의 내부 막대 1개가 표기된다.
가상 요소 선택자 (Pseudo-Element Selector)를 사용하여 navigation icon의 내부 막대 앞뒤 공간에 내부 막대를 추가한다.
절대 위치를 지정하기 위해 position: absolute;를 사용하였으므로 가상 요소의 부모 요소인 span 요소(.navicon-bar)에 position: relative;를 추가한다.
아직 navigation icon을 클릭하여도 아무런 반응이 없다. navigation icon을 클릭하면 클릭되었음을 사용자가 확인할 수 있도록 navigation icon의 style을 변화시킨다.
input checkbox tag의 가상 클래스 선택자 checked를 이용하여 클릭되었을 때(input:checked)와 그렇지 않을 때를 구분할 수 있다.
먼저 중간에 위치한 막대를 없앤다. 그리고 상하 막대를 45도 회전시킨다. 이때 위치가 틀어지므로 top: 0;로 보정한다.
navigation icon에 transition 효과를 부여하여 좀더 부드럽게 움직이도록 한다.
transition 프로퍼티는 property, duration, delay 순으로 정의한다.
navigation icon을 클릭하면 의도하지 않게 이미지가 선택되는 현상이 발생할 수 있다.
이것은 navigation icon이 텍스트이기 때문에 발생하는 문제이다. 이 문제는 텍스트 선택을 차단하는 방법인 user-select: none; 프로퍼티를 지정하여 회피할 수 있다. user-select 프로퍼티는 현재 W3C(World Wide Web 컨소시엄) CSS 사양에 포함되어 있지 않기 때문에 벤더프리픽스(vendor prefix)를 사용하여야 한다.
navigation icon과 checkbox input tag는 스마트폰 layout 이외의 경우, 화면에 표시되어서는 않된다. 따라서 display: none;으로 화면에 표시되지 않도록 한다. display: none;은 해당 공간조차 점유하지 않지만 visibility: hidden;을 사용하면 해당 공간은 남아있고 표시만 되지 않는다. 
CSS 적용 우선 순위 (Cascading Order)를 고려하여 가장 마지막에 정의하는 것이 안전하다. 일반적으로 media query를 가장 마지막에 정의하므로 media query 정의부 직전에 위치시킨다.
tablet용 layout에서 header height를 2배로 하였으므로 mobile용 layout을 위해 다시 60px로 되돌린다.
스마트폰 layout에서는 navigation bar가 초기상태에서 비표시되어야 한다. 그리고 navigation icon은 표시되어야 한다. 아직 navigation icon을 완성하지 않았으므로 표시되지 않는다.
콘텐츠 영역이 아직 tablet layout에 맞추어 아래로 내려가 있다. header 영역 바로 아래로 다시 끌어 올린다.
마지막으로 navigation icon을 클릭하면 navigation item이 표시되도록 한다.
다음은 완성된 Responsive Navigation Bar의 소스코드이다.
3. Section & Aside & Footer
현재 article은 layout에 상관없이 1행에 1개씩 배치되었다. responsive web design의 효과를 좀더 체감하기 위하여 1행에 2열로 배치한다.
article을 2열로 배치하기 위해서 width 값을 지정하여야 한다. %로 width 값을 지정하여 viewport에 상대적인 너비를 갖도록 한다. 이때 margin도 %로 지정한다. 그리고 float: left;를 지정하여 2열로 정렬되도록 한다.
짝수번째 배치되는 article의 좌측 마진과 3번째부터 등장하는 article의 위측 마진을 0로 하여 가운데 마진이 2배가 되는 것을 방지한다.
tablet layout을 작성한다. 800px 이하로 화면이 작아지면 2열 배치되어 있던 article을 1열로 배치한다.
mobile layout을 작성한다. 480px 이하로 화면이 작아지면 고정 배치되어 있던 aside를 article 위로 올려 배치한다.
완성된 코드는 아래와 같다.

20. 플렉스 박스 레이아웃
1. Introduction
Flexbox는 모던 웹을 위하여 제안된 기존 layout보다 더 세련된 방식의 니즈에 부합하기 위한 CSS3의 새로운 layout 방식이다.
요소의 사이즈가 불명확하거나 동적으로 변화할 때에도 유연한 레이아웃을 실현할 수 있다. 복잡한 레이아웃이라도 적은 코드로 보다 간단하게 표현할 수 있다.
div 요소는 block 요소이므로 수직 정렬된다. 이를 수평 정렬하려면 자식요소(flex-item)를 inline-block으로 지정하거나 float 프로퍼티를 지정한다.
이때 각 자식 요소을 부모 요소 내에서 정렬하기 위해서는 각 자식 요소의 너비를 %로 지정하는 등 번거로운 처리가 필요하다. 자식 요소의 사이즈가 불명확하거나 동적으로 변화할 때에는 더욱 처리가 복잡해 진다. grid 시스템을 사용할 수 도 있으나 이 또한 새로운 학습이 필요하고 라이브러리를 로드해야하는 번거로움이 존재한다.
Flexbox를 사용하여 위 예제를 부모 요소 내에서 균등 수평 정렬해 보자. 부모 요소에 아래와 같이 2행을 추가하면 된다.
Flexbox를 사용하면 기존에 방식에 비해 매우 간단히 레이아웃을 처리할 수 있다. 그 결과는 아래와 같다.
Flexbox의 장점을 정리해 보면 아래와 같다.
- 1줄의 코드 추가로 수평 정렬이 가능하다.
- 요소의 상하좌우 정렬, 순서 변경이 간단하다.
- 요소가 간격 조절이 간단하다.
- 서로 다른 height를 갖는 요소의 수평정렬 시, 간단히 상하중앙 정렬이 가능하다.
- 비교적 최신 브라우저가 아니면 벤더 프리픽스를 사용하여야 하고 IE계열은 IE8,9의 경우 지원하지 않고 IE10,11의 경우도 일부 지원하므로 주의가 필요하다. IE계열에서 Flexbox를 사용하기 위해서는 flexibility.js를 사용하면 편리하다.
2. Usage
Flexbox 레이아웃은 flex item이라 불리는 복수의 자식 요소와 이들을 내포하는 flex-container 부모 요소로 구성된다.
flexbox를 사용하기 위해서 HTML 부모 요소의 display 속성에 flex를 지정한다
부모 요소가 inline 요소인 경우 inline-flex을 지정한다.
flex 또는 inline-flex는 부모 요소에 반드시 지정해야하는 유일한 속성이며 자식 요소는 자동적으로 flex item이 된다.
3. Flexbox container 속성
3.1 flex-direction
flex-direction 속성은 flex 컨테이너의 주축(main axis) 방향을 설정한다.
좌에서 우로(ltr) 수평 배치된다. flex-direction 속성의 기본값이다.
우에서 좌로(rtl) 수평 배치된다.
위에서 아래로 수직 배치된다.
아래에서 위로 수직 배치된다.
3.2 flex-wrap
flex-wrap 속성은 flex 컨테이너의 복수 flex item을 1행으로 또는 복수행으로 배치한다. flex-wrap 속성은 flex 컨테이너의 width보다 flex item들의 width의 합계가 더 큰 경우, 한줄로 표현할 것인지, 여러줄로 표현할 것인지를 지정한다.
flex item을 개행하지 않고 1행에 배치한다. flex-wrap 속성의 기본값이다.
각 flex item의 폭은 flex container에 들어갈 수 있는 크기로 축소된다.
하지만 flex item들의 width의 합계가 flex 컨테이너의 width보다 큰 경우 flex 컨테이너를 넘치게 된다. 이때 overflow: auto;를 지정하면 가로 스크롤이 생기며 컨테이너를 넘치지 않는다.
flex item들의 width의 합계가 flex 컨테이너의 width보다 큰 경우, flex item을 복수행에 배치한다. 기본적으로 좌에서 우로, 위에서 아래로 배치된다.
flex-wrap: wrap;과 동일하나 아래에서 위로 배치된다.
3.3 flex-flow
flex-flow 속성은 flex-direction 속성과 flex-wrap 속성을 설정하기 위한 shorthand이다. 기본값은 row nowrap이다.
3.4 justify-content
flex container의 main axis를 기준으로 flex item을 수평 정렬한다.
main start(좌측)를 기준으로 정렬한다. justify-content 속성의 기본값이다.
main end(우측)를 기준으로 정렬한다.
flex container의 중앙에 정렬한다.
첫번째와 마지막 flex item은 좌우 측면에 정렬되고 나머지와 균등한 간격으로 정렬된다.
모든 flex item은 균등한 간격으로 정렬된다.
3.5 align-items
flex item을 flex container의 수직 방향(cross axis)으로 정렬한다. align-items 속성은 모든 flex item에 적용된다.
모든 flex item은 flex container의 높이(cross start에서 cross end까지의 높이)에 꽉찬 높이를 갖는다. align-items 속성의 기본값이다.
모든 flex item은 flex container의 cross start 기준으로 정렬된다.
모든 flex item은 flex container의 cross end 기준으로 정렬된다.
모든 flex item은 flex container의 cross axis의 중앙에 정렬된다.
모든 flex item은 flex container의 baseline을 기준으로 정렬된다.
3.6 align-content
flex container의 cross axis를 기준으로 flex item을 수직 정렬한다.
참고로 justify-content 속성은 flex container의 main axis를 기준으로 flex item을 수평 정렬한다.
모든 flex item은 flex item의 행 이후에 균등하게 분배된 공간에 정렬되어 배치된다. align-content 속성의 기본값이다.
모든 flex item은 flex container의 cross start 기준으로 stack 정렬된다.
모든 flex item은 flex container의 cross end 기준으로 stack 정렬된다.
모든 flex item은 flex container의 cross end 기준으로 stack 정렬된다.
첫번째 flex item의 행은 flex container의 상단에 마지막 flex item의 행은 flex container의 하단에 배치되며 나머지 행은 균등 분할된 공간에 배치 정렬된다.
모든 flex item은 균등 분할된 공간 내에 배치 정렬된다.
4. Flexbox item 속성
float, clear, vertical-align 속성은 flex item에 영향을 주지 않는다.
4.1 order
flex item의 배치 순서를 지정한다. HTML 코드를 변경하지 않고 order 속성값을 지정하는 것으로 간단히 재배치할 수 있다. 기본 배치 순서는 flex container에 추가된 순서이다. 기본값은 0이다.
4.2 flex-grow
flex item의 너비에 대한 확대 인자(flex grow factor)를 지정한다. 기본값은 0이고 음수값은 무효하다.
모든 flex item이 동일한 flex-grow 속성값을 가지면 모든 flex item은 동일한 너비를 갖는다.
두번째 flex item의 flex-grow 속성값을 3으로 지정하면 다른 flex item보다 더 넓은 너비를 갖는다.
4.3 flex-shrink
flex item의 너비에 대한 축소 인자(flex shrink factor)를 지정한다. 기본값은 1이고 음수값은 무효하다. 0을 지정하면 축소가 해제되어 원래의 너비를 유지한다.
기본적으로 모든 flex item은 축소된 상태로 지정(기본값 1)하고 두번째 flex item만 축소를 해제(flex-shrink: 0;)하면 원래의 너비를 유지한다.
4.4 flex-basis
flex item의 너비 기본값을 px, % 등의 단위로 지정한다. 기본값은 auto이다.
4.5 flex
flex-grow, flex-shrink, flex-basis 속성의 shorthand이다. 기본값은 0 1 auto이다.
W3C에서는 이 속성을 사용하는 것 보다 개별적으로 기술하는 것을 추천하고 있다.
4.6 align-self
align-items 속성(flex container속성으로 flex item을 flex container의 수직 방향(cross axis)으로 정렬한다.)보다 우선하여 개별 flex item을 정렬한다. 기본값은 auto이다.
3번째, 4번째 flex item은 align-self 속성값이 우선 적용되어 정렬된다.
5. Flexbox playground
(https://codepen.io/enxaneta/full/adLPwv)

21. 수평/수직 중앙 정렬
1. 수평 정렬(Horizontal Align)
1.1 inline/inline-block 요소
정렬 대상 요소(텍스트 또는 링크 등의 inline 레벨 요소 또는 inline-block 레벨 요소)의 부모 요소에 text-align: center;를 지정한다.
1.2 block 요소
정렬 대상 요소에 너비를 명시적으로 지정하고 margin-right와 margin-left 프로퍼티에 auto를 지정한다.
정렬 대상 요소에 너비를 명시적으로 지정하지 않으면 너비는 full width가 되므로 중앙 정렬이 필요없다.
1.3 복수의 block 요소
복수의 block 요소는 기본적으로 수직 정렬된다. 이것을 수평정렬하기 위해서는 정렬 대상 block 요소를 inline-block 요소로 변경한 후 부모 요소에 text-align: center;를 지정한다.
정렬 대상 요소에 width를 지정하지 않으면 콘텐츠에 너비에 맞추어 너비가 결정되므로 명시적으로 너비를 지정한다.
1.4 Flexbox
flexbox를 사용할 수도 있다. 정렬 대상의 부모 요소에 아래의 룰셋을 선언한다.
2. 수직 정렬(Vertical Align)
2.1 inline/inline-block 요소
2.1.1 Single line
정렬 대상의 부모 요소에 padding-top과 padding-bottom 프로퍼티값을 동일하게 적용한다.
padding을 사용할 수 없는 경우, 요소의 height와 line-height 프로퍼티값을 동일하게 적용한다. 단 이 방법은 행간이 지나치게 넓어지거나 Click Dead Zone 이슈가 발생하는 등 여러 줄의 텍스트에는 사용할 수 없다.
2.1.2 Multiple lines
여러 줄의 텍스트의 경우, padding-top과 padding-bottom 프로퍼티값을 동일하게 적용하는 방법도 가능하다.
또 다른 방법으로 vertical-align 프로퍼티를 사용한 방법도 가능하다. 이 방법은 table 속성을 사용하여야 한다.
2.1.3 Flexbox
vertical-align 프로퍼티를 사용하는 방법은 table 프로퍼티를 사용하여야 하므로 번거로울 수 있다. 좀 더 간단한 방법은 flexbox를 사용하는 것이다.
2.2 block 요소
2.2.1 요소의 높이가 고정되어 있는 경우
부모 요소를 기준으로 절대 위치를 지정한다.
2.2.2 요소의 높이가 불확정 상태의 경우
부모 요소를 기준으로 절대 위치를 지정한다.
2.2.3 Flexbox
부모 요소에 Flexbox layout을 지정한다.
3. 수평/수직 정렬(Horizontal & Vertical Align)
요소의 너비와 높이가 고정되어 있는 경우, 요소의 너비와 높이가 불확정 상태의 경우 모두 사용 가능한 방법이다
Flexbox를 사용한 방법은 아래와 같다.

22. image 요소 아래에 패딩된 여분의 공간 제거하기
컨테이너 요소로 img 요소를 래핑하면 img 요소 아래에 의도하지 않은 여분의 공간이 패딩된다.
이 문제가 발생하는 이유에 대해 살펴보자. 단순히 문제 해결 방법을 외우지 않고 문제가 발생하는 이유를 이해하면 문제 해결 방법을 기억하는 것에 도움이 된다.
image 요소는 inline 요소이다. 다시 말해 image 요소는 텍스트로 취급된다. 브라우저는 요소 내의 텍스트를 렌더링할 때 나름의 방식이 있는데 이를 이해하려면 타이포그래피(Typography)에 대해 어느 정도 이해해야 한
image 요소는 inline 요소이며 텍스트로 취급된다고 하였다. 이것은 image 요소 또한 위 그림과 같이 타이포그래피를 따른다는 것을 의미한다. 정말 그런지 텍스트와 image 요소를 같이 배치해 확인해보자
위 그림과 같이 image 요소에도 디센더가 적용되어 여분의 공간이 발생한다. 원인을 알았으니 이 문제에 대한 해결 방법에 대해 생각해보자.
첫번째, image 요소를 블록 요소로 전환하면 더 이상 텍스트로 취급되지 않는다.
하지만 이 방법은 image 요소를 블록 요소로 전환할 수 없는 레이아웃에서는 사용할 수 없다.
두번째, inline 요소에 사용할 수 있는 vertical-align 프로퍼티를 사용하는 방법이 있다. vertical-align 프로퍼티의 기본값은 baseline인데 이를 변경하여 이미지 표시 위치를 조정하는 것이다.
