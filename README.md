# HTML-MovieBox

## 목차

-   [개요](#개요)
-   [제작과정](#제작과정)
-   [개발 환경](#개발-환경)
-   [주요 기술](#주요-기술)
-   [세부내용](#세부내용)
    -   [초기 기획안](#초기-기획안)
    -   [웹 사이트 구조](#웹-사이트-구조)
    -   [전체 Process](#전체-Process)
    -   [주요 기능](#주요-기능)
-   [실행 방법](#실행-방법)

## 개요

-   영화 정보를 보여주는 웹 사이트

## Show Case

- [https://competent-bohr-f71db3.netlify.app/project/main/main.htm](https://competent-bohr-f71db3.netlify.app/project/main/main.htm)

## 제작과정

-   프로젝트 명 : Movie Box
-   수행기간 : 2014년 5월
-   프로젝트 인원 : 1명
-   나의 기여도 : 100%
-   담당 :
    -   영화정보 수집
        -   포스터, 줄거리, 평점 등
    -   프로젝트 폴더 구조 구상
    -   개발

## 개발 환경

-   **OS** : Windows 7
-   **IDE** : Notepad++
-   **Browser** : Chrome
-   **Programming Languages**
    - HTML, CSS, JavaScript

## 주요 기술

-   frame을 이용한 header, Content Layout
-   marquee Tag
-   DropDown Menu
-   window object를 이용한 포스터 확대보기 Popup

## 세부내용

### 초기 기획안

![초기 기획안](./etc/first.jpg)

> 초기 기획안은 Header, SideMenu, Content로 세개의 frame으로 나누는 것이었지만  
> Header 메뉴를 드롭다운으로 구현하는 것으로 방식을 변경하였다.

### 웹 사이트 구조

![Website Architecture](./etc/website-architecture.JPG)

### 전체 Process

![process](./etc/process.gif)

### 주요 기능

-   **Door 화면**

    ![Door 화면](./etc/Door.jpg)

    > table을 이용하여 구현하였다.

-   **Main**

    ![Main 화면](./etc/main-moving.gif)

    `project/frame_contents/home_contents.htm`

    ```html
    <marquee behavior="alternate" width="1000">
        <table>
            ...
        </table>
    </marquee>
    ```

    > marquee 태그를 이용하여 좌우로 움직이도록 만들었다.

-   **Menu hover**

    ![Menu hover](./etc/menu-mouse-over2.gif)

    > css로 드롭다운 메뉴 구현  
    > code : `Project/frame_menu/menu.htm`

-   **View Poster Big Size**

    ![View Poster Big Size](./etc/poster-click.gif)

    `project/movie/표적.htm`

    ```html
    <script language="javascript" src="movie.js"></script>
    ... 
    <img src="img/표적포스터.jpg" onClick="openWin(this.src)" />
    ```

    `project/movie/국내/movie.js`

    ```javascript
    function openWin(src) {
        win = window.open('' + src + '', 'win', 'width=1024 height=768 directories=no');
        win.document.write('<html><head>');
        win.document.write('<title>포스터 확대보기</title>');
        win.document.write("</head><body leftmargin=0 topmargin=0 onclick='self.close()'>");
        win.document.write("<img src='" + src + "' width=100% height=100%>");
        win.document.write('</body></html>');
    }
    ```

    > 영화 상세 페이지에서 포스터 클릭 시 팝업창으로 포스터를 크게 볼 수 있다.

## 실행 방법

1.   DownLoad Zip
2.   Execute `project/door/door.htm`
