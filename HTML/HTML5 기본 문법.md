출처: https://poiemaweb.com/

1.HTML5 기본 문법
HTML (HyperText Markup Language): 웹페이지를 기술하기 위한 마크업 언어. 조금 더 자세히 말하면 웹페이지의 내용(content)과 구조(structure)을 담당하는 언어로써 HTML 태그를 통해 정보를 구조화하는 것이다.
- HTML5 문서는 반드시 <!DOCTYPE html>으로 시작하여 문서 형식(document type)을 HTML5로 지정
- 실제적인 HTML document은 2행부터 시작되는데 <html>과 </html> 사이에 기술
- <head>와 </head> 사이에는 document title, 외부 파일의 참조, 메타데이터의 설정 등이 위치하며 이 정보들은 브라우저에 표시되지 않음
- 웹브라우저에 출력되는 모든 요소는 <body>와 </body> 사이에 위치
요소(Element): 시작 태그(start tag)와 종료 태그(end tag) 그리고 태그 사이에 위치한 content로 구성
요소의 중첩 (Nested Element): 요소는 다른 요소를 포함할 수 있다. 이때 부자관계가 성립된다. 이러한 부자관계로 정보를 구조화하는 것
빈 요소(Empty Element): content를 가질 수 없는 요소를 빈 요소(Empty element or Self-Closing element)라 한다. 아래의 예와 같이 빈 요소는 content가 없으며(필요가 없다) 어트리뷰트(Attribute)만을 가질 수 있다.
어트리뷰트 (Attribute): 요소의 성질, 특징을 정의하는 명세이다. 요소는 어트리뷰트를 가질 수 있으며 어트리뷰트는 요소에 추가적 정보(예를 들어 이미지 파일의 경로, 크기 등)를 제공한다. 어트리뷰트는 시작 태그에 위치해야 하며 이름과 값의 쌍을 이룬다. (e.g. name=”value”)
글로벌 어트리뷰트 (HTML Global Attribute): 글로벌 어트리뷰트는 모든 HTML 요소가 공통으로 사용할 수 있는 어트리뷰트다. 몇몇 요소에는 효과가 적용되지 않을 수 있지만, 글로벌 어트리뷰트는 대체로 모든 요소에 사용될 수 있다. ex. id, class, hidden, lang, style
주석 (Comments): <!-- -->

2. 시맨틱 요소와 검색 엔진
검색엔진은 로봇(Robot)이라는 프로그램을 이용해 매일 전세계의 웹사이트 정보를 수집한다.(이것을 크롤링이라 하며 검색엔진의 크롤러가 이를 수행한다.) 
이용자가 검색할 만한 키워드를 미리 예상하여 검색 키워드에 대응하는 인덱스(색인)을 만들어 둔다. .(이것을 인덱싱이라 하며 검색엔진의 인덱서가 이를 수행한다.)
검색 엔진은 HTML 코드 만으로 그 의미를 인지하여야 하는데 이때 시맨틱 요소(Semantic element)를 해석하게 된다. 즉 시맨틱 요소는 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확히 설명하는 역할을 한다.
이는 웹에 존재하는 수많은 웹페이지들에 메타데이터(Metadata)를 부여하여, 기존의 잡다한 데이터 집합이었던 웹페이지를 ‘의미’와 ‘관련성’을 가지는 거대한 데이터베이스로 구축하고자 하는 발상이다. ex. form, table, img

3. 웹페이지를 구성하는 기본 태그
문서 형식 정의 tag: <!DOCTYPE html>
html tag: 모든 HTML 요소의 부모 요소이며 웹페이지에 단 하나만 존재
head tag: 메타데이터(HTML 문서의 title, style, link, script에 대한 데이터)를 포함하기 위한 요소이며 웹페이지에 단 하나만 존재, head 요소에는 메타데이터 이외의 화면에 표시되는 일체의 요소를 포함시킬 수 없음
title tag: 문서의 제목을 정의한다. 정의된 제목은 브라우저의 탭에 표시
style tag: HTML 문서를 위한 style 정보를 정의
ink tag: 외부 리소스와의 연계 정보를 정의한다. 주로 HTML과 외부 CSS 파일을 연계에 사용
script tag: client-side JavaScript를 정의
meta tag: description, keywords, author, 기타 메타데이터 정의에 사용된다. 메타데이터는 브라우저, 검색엔진(keywords) 등에 의해 사용
body tag: HTML 문서의 내용을 나타내며 웹페이지에 단 하나만 존재한다. 메타데이터를 제외한 웹페이지를 구성하는 대부분의 요소가 body 요소 내에 기술

4. 텍스트 관련 태그
제목 (Headings) 태그: 제목을 나타낼 때 사용하며 h1에서 h6까지의 태그가 있음
글자 형태 (Text Formatting) 태그: 
- b: bold체를 지정한다. 제목 태그와 같이 의미론적(Semantic) 중요성의 의미는 없다.
- strong: b tag와 동일하게 bold체를 지정한다. 하지만 의미론적(Semantic) 중요성의 의미를 갖는다.
- i: Italic체를 지정한다. 의미론적(Semantic) 중요성의 의미는 없다.
- em: emphasized(강조, 중요한) text를 지정한다. i tag와 동일하게 Italic체로 표현된다. 의미론적(Semantic) 중요성의 의미를 갖는다.
- small: small text를 지정한다.
- mark: highlighted text를 지정한다.
- del: deleted (removed) text(취소선)를 지정한다.
- ins: inserted (added) text(밑줄)를 지정한다.
- sub / sup: sub 태그는 subscripted(아래에 쓰인) text를 sup 태그는 superscripted(위에 쓰인) text를 지정한다.
본문 태그:
- p: 단락 (Paragraphs)을 지정한다.
- br:  (강제)개행 (line break)을 지정한다. br tag는 빈 요소(empty element)로 종료태그가 없다. HTML에서는 1개 이상의 연속된 공백(space)을 삽입하여도 1개의 공백으로 표시된다. 
1개 이상의 연속된 줄바꿈(enter)도 1개의 공백으로 표시된다. 연속적 공백을 삽입하는 방법은 &nbsp; 이용.
- pre: 형식화된(preformatted) text를 지정한다. pre 태그 내의 content는 작성된 그대로 브라우저에 표시된다.
- hr: 수평줄을 삽입한다.
- q: 짧은 인용문(quotation)을 지정한다. 브라우저는 인용부호(큰따옴표/quotation marks)로 q 요소를 감싼다. 
- blockquote: 긴 인용문 블록을 지정한다. 브라우저는 blockquote 요소를 들여쓰기한다. css를 이용하여 다양한 style을 적용할 수 있다.

5. HTML의 핵심 개념인 Hyperlink
HyperText의 Hyper는 컴퓨터 용어로서 텍스트 등의 정보가 동일 선상에 있는 것이 아니라 다중으로 연결되어 있는 상태를 의미
이것은 HTML의 가장 중요한 특징인 link의 개념과 연결되는데 기존 문서나 텍스트의 선형성, 고정성의 제약에서 벗어나 사용자가 원하는 순서대로 원하는 정보를 취득할 수 있는 기능을 제공한다. 
한 텍스트에서 다른 텍스트로 건너뛰어 읽을 수 있는 이 기능을 하이퍼링크(hyper link)라 한다.
href 어트리뷰트: 이동하고자 하는 파일의 위치(경로)를 값으로 받는다. 경로(path)란 파일 시스템 상에서 특정 파일의 위치를 의미
- 디렉터리(Directory): 파일과 다른 디렉터리를 갖는 파일 시스템 내의 존재물로서 폴더라고도 불리운다.
- 파일 경로(File path): 파일 시스템에서 파일의 위치를 나타내는 방법이다. 경로에는 절대경로와 상대경로가 있다.
- 사용 가능한 값: 절대경로, 상대경로, fragment identifier, 메일, script
target 어트리뷰트: 링크를 클릭했을 때 윈도우를 어떻게 오픈할 지를 지정한다.
- target="_blank"(탭오픈)를 사용해 외부 페이지를 오픈하는 경우, 이동한 외부 페이지에서 자바스크립트 코드를 사용해 악의적인 페이지로 리다이렉트할 수 있는 보안 취약점(Tabnabbing 피싱 공격)이 있다. 
따라서 rel="noopener noreferrer"를 추가해 Tabnabbing 피싱 공격에 대비할 것을 권장한다. 참고로 noopener 속성은 성능 상 이점도 있는 것으로 알려져 있다. 

6. 목록(List)와 표(Table) 형식 표현을 위한 태그
목록 (List): 네비게이션 메뉴 만들 때 사용, 중첩 목록도 가능
- 순서없는 목록 (Unordered List): <ul>
- 순서있는 목록 (Ordered List): <ol>, type 어트리뷰트를 사용하여 순서를 나타내는 문자를 지정할 수 있다
테이블: 표(table)를 만들 때 사용하는 태그, 과거에는 테이블 태그를 사용하여 레이아웃을 구성하기도 하였으나 모던 웹에서는 주로 공간 분할 태그인 div 태그를 사용하여 레이아웃을 구성
- table: 표를 감싸는 태그
- tr: 표 내부의 행 (table row) 
- th: 행 내부의 제목 셀 (table heading)
- td: 행 내부의 일반 셀 (table data)
- border(CSS에서 지정하는 것이 일반적)
- rowspan: 해당 셀이 점유하는 행의 수 지정
- colspan: 해당 셀이 점유하는 열의 수 지정

7. 이미지의 표현과 동영상, 음악 등 멀티미디어를 지원하는 태그
이미지: 웹페이지에 이미지를 삽입하는 경우, img tag를 사용
- src: 이미지 파일 경로
- alt: 이미지 파일이 없을 경우 표시되는 문장
- width: 이미지의 너비 (CSS에서 지정하는 것이 일반적)
- height: 이미지의 높이 (CSS에서 지정하는 것이 일반적)
미디어: 웹브라우저 별로 지원하는 음악 파일 형식이 다르다. 파일 형식에 따라 재생되지 않는 브라우저가 존재한다는 뜻
source 태그를 사용하여 파일 형식의 차이 문제를 해결 할 수 있다. type 어트리뷰트는 생략 가능
- src: 음악 파일 경로
- preload: 재생 전에 음악 파일을 모두 불러올 것인지 지정
- autoplay: 음악 파일을 자동의 재생 개시할 것인지 지정
- loop: 음악을 반복할 것인지 지정
- controls: 음악 재생 도구를 표시할 것인지 지정. 재생 도구의 외관은 브라우저마다 차이가 있다.
비디오: audio 태그와 마찬가지로 파일 형식의 차이 문제가 발생할 수 있다. source 태그를 사용하여 형식 차이 문제를 해결한다. type 어트리뷰트는 생략 가능
- src: 동영상 파일 경로
- preload: 재생 전에 동영상 파일을 모두 불러올 것인지 지정
- autoplay: 동영상 파일을 자동의 재생 개시할 것인지 지정
- loop: 동영상을 반복할 것인지 지정
- controls: 동영상 재생 도구를 표시할 것인지 지정. 재생 도구의 외관은 브라우저마다 차이가 있다.
- poster: 동영상 준비 중에 표시될 이미지 파일 경로
- width: 동영상의 너비를 지정
- height: 동영상의 높이를 지정

8. 사용자와의 커뮤니케이션을 위한 폼 태그
form: 사용자가 입력한 데이터를 수집하기 위해 사용되며 input, textarea, button, select, checkbox, radio button, submit button 등의 입력 양식 태그를 포함할 수 있다
- action: 입력 데이터(form data)가 전송될 URL 지정
- method: 	입력 데이터(form data) 전달 방식(get/post) 지정
input: form 태그 중에서 가장 중요한 태그로 사용자로부터 데이터를 입력받기 위해 사용된다. 
input 태그는 다양한 종류가 있는데 type 어트리뷰트에 의해 구분된다. form 태그 내에 존재하여야 입력 데이터를 전송할 수 있으나 ajax를 사용할 시에는 form 태그 내에 존재하지 않아도 된다.
서버에 전송되는 데이터는 name 어트리뷰트를 키로, value 어트리뷰트를 값으로하여 key=value의 형태로 전송된다.
- 어트리뷰트: 링크 참조 (https://poiemaweb.com/html5-tag-forms)
select: 복수개의 리스트에서 복수개의 아이템을 선택할 때 사용한다. 서버에 전송되는 데이터는 select 요소의 name 어트리뷰트를 키로, option 요소의 value 어트리뷰트를 값으로하여 key=value의 형태로 전송된다.
- select: select form 생성
- option: option 생성
- optgroup: option을 그룹화한다.
textarea: 여러 줄의 글자를 입력할 때 사용한다
button: 클릭할 수 있는 버튼을 생성, <input type="button">과 유사하지만 input 태그는 빈 태그인 반면 button 태그는 그렇지 않다. 따라서 button 요소에는 텍스트나 이미지 같은 콘텐츠를 사용할 수 있다.
type 어트리뷰트는 반드시 지정하는 것이 바람직하며 어트리뷰트값으로 button, reset, submit를 지정할 수 있다.
button 태그는 어트리뷰트만을 받아들이는 input 태그와 달리 콘텐츠로 문자열은 물론 HTML 요소를 받을 수도 있다는 장점이 있다. 주의할 것은 IE의 경우, submit되는 값이 다를 수 있는 것이다.
fieldset / legend: fieldset 태그는 관련된 입력 양식들을 그룹화할 때 사용한다. legend 태그는 fieldset 태그 내에서 사용되야 하며 그룹화된 fieldset의 제목을 정의한다.

9. 웹페이지의 레이아웃을 구성하기 위해 공간을 분할하는 태그
공간을 분할할 수 있는 태그는 div, span, table 등이 있는데, 과거에는 table 태그를 사용하여 레이아웃을 구성하기도 하였으나 모던 웹에서는 주로 div를 사용하여 레이아웃을 구성
div 태그는 의미론적으로 어떠한 의미도 가지고 있지 않기 때문에 아래와 같이 HTML5에서 새롭게 추가된 시맨틱 태그를 사용하는 것이 더 나은 방법이나 IE에서 작동하지 않기 때문에 주의가 필요
- header: 헤더를 의미한다
- nav: 내비게이션을 의미한다
- aside: 사이드에 위치하는 공간을 의미한다
- section: 본문의 여러 내용(article)을 포함하는 공간을 의미한다
- article: 분문의 주내용이 들어가는 공간을 의미한다
- footer: 푸터를 의미한다
이와 같은 공간 분할 태그는 일반적으로 다른 요소를 포함하는 컨테이너 역할을 하게 된다.
div와 span의 차이는 block 레벨 요소와 inline 레벨 요소를 이해하여야 한다.


