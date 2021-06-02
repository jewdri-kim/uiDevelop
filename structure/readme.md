# 가이드 만들기



- 모든 항목은 가이더가 주도적으로 하되, 프로젝트 TF 작업자 간 논의와 협업이 중요하다. 
- 작업하는 시간과 속도보다 가이드 만드는 작업이 오래 걸리나, 추 후 효율성과 업무 프로세스, 
- 체계를 위해 가이드를 만드는 작업은 중요
- 작업 중간중간에 가이드에 항목을 추가하는 일은 작업자 모두에게 주어진 일 (가이더만 하는게 아니다.)
- 내가 하는 작업에 공통으로 쓰일만한 (재사용될만한) 작업이 있다면 협의후 추가하자!!



## 구조 

- 폴더구조
- html 구조 ( 공통, 컨텐츠 부분)
- css 구조 ( 공통과 페이지 부분)
- js 구조 
- 가이드 구성
- 공통 선별하기 
- 구조 또한, 서로간의 협의가 중요하다. 특히  폴더구조와 html 구조는 다른 파트와도 협의 (공통부분, 컨텐츠부분 등)



### 폴더구조

 : 프로젝트 업무 특성에 따라 , 파트 별 R&R에 맞게 폴더구조 수립 

#### AHC (예시)

- app

  - css
  - html
  - images
  - js

- asset

  - css
    - _font.scss
    - font.css
  - favicon
  - font
    - NotoSans-Bold.otf
    - ....
  - js
    - jquery-3.1.1.min.js
    - jquery-ui.js
    - slick.js
    - TweenMax.min.js

- list

- mail

- mo

- pc

  - shop

  - brand

    - css  : css 구조에서 설명

    - html

      - bestseller

      - brand

      - cart

      - etc

      - community

      - event

      - guide

      - layout

        - footer.html
        - header.html
        - meta.html

      - main

      - member

      - mypage

      - shopping

      - popup

        



#### AHC /  SKT Tplace / aero_k

- 폴더구조 다른점 
- 프로젝트 범위, 특성에 따라 폴더구조 정한다.
- 개발파트와 협의 필요



### html 구조

- 공통 부분 include로 분리하기 
- 공통 헤더, 푸터, 주로 사용
- 가운데 페이자마다 변동될 수 있는 컨텐츠 영역
- 개발자와 협의 필요



#### AHC

http://code.d2.co.kr/2019/ahc/pc/shop/html/guide/layout.html

```html
<!DOCTYPE html>
<!--[if IE 9]> <html lang="ko" class="ie9"> <![endif]-->
<!--[if !IE]><!--><html lang="ko"><!--<![endif]-->
<head>
	<?php include '../layout/meta.html'?>
</head>
<body>
	<div id="wrap">
		<?php include '../layout/header.html'?>
		
		<div id="container">
			<!--<nav id="lnb">
				LNB
			</nav>-->
			<section id="content">
				<div class="inner-box "><!-- 해당페이지 대표하는 클래스 이름 넣기 : 예시 : event, join , login-->
					
					<div class="depth-area">
						<a href="#" lang="en">HOME</a>
						<span>타이틀</span>
					</div>
					<div class="page-title">
						<h2 class="title-type">타이틀</h2>
						<p class="sub-type">서브텍스트</p>
					</div>
					
				</div>
			</section>
			
		</div>
		
		<?php include '../layout/footer.html'?>
	</div>
</body>
</html>
```





### css 구조

- scss 사용

- **css** 

  - **common**
    - _animation.scss
    - _base.scss
    - _board.scss
    - _button.scss
    - _component.scss
    - _form.scss
    - _icon.scss
    - _layout.scss
    - _mixin.scss
    - _popup.scss
    - _slider.scss
    - _table.scss
    - _text.scss
    - _variable.scss
  - **sub**
    - _bestseller.scss
    - _brand.scss
    - _cart.scss
    - _clusiv.scss
    - _community.scss
    - _etc.scss
    - _event.scss
    - _member.scss
    - _mypage.scss
    - _shopping.scss
  - **common.scss**

  ```scss
  @charset "UTF-8";
  
  @import 'common/base',
  'common/variable',
  'common/mixin';
  
  @import 'common/layout',
  'common/popup',
  'common/button',
  'common/icon',
  'common/text',
  'common/table',
  'common/board',
  'common/slider',
  'common/component',
  'common/animation',
  'common/form';
  ```

  

  - main.scss
  - sub.scss
    - html 내에 뎁스 나타내는 폴더명과 같은 파일명으로 sub폴더에 scss

  ```scss
  @charset "UTF-8";
  
  //page
  @import
  'sub/shopping',
  'sub/member',
  'sub/cart',
  'sub/community',
  'sub/mypage',
  'sub/brand',
  'sub/clusiv',
  'sub/bestseller',
  'sub/etc',
  'sub/zone',
  'sub/event';
  // 'sub/brand';
  
  /*
  sub.scss
      - shopping.scss (상품리스트/상세, new, best, review???)
      - member.scss (로그인/회원가입 , 멤버십혜택)
      - cart.scss (장바구니/주문/결제)
      - mypage.scss (마이페이지)
      - main.scss (메인)
      - community.scss (이벤트/공지사항/고객센터/FAQ reivew???)
      - brand.scss (브랜드)
      - event.scss (이벤트)
      - zone.scss (뷰티클래스/스파서비스)
      */
  
  ```

  



### js 구조

- ui.js 공통으로 쓰이는 메쏘드나 이벤트 (레이아웃관련)
- var UI 라는 변수안에 다 넣는다
- 메쏘드는 UI. 으로 접근 ( 개발에서 쓰이는 함수와 겹치지 않게 식별 하기 위함)

```javascript
var UI = (function () {
    return {
        init: function () {
            this.event();
        },
        element: {
            layout: {
                header: '.header-wrap',
                quick: '.quick-wrap',
                top: '.quick-wrap .item-top a'
            },
            gnb: {
                wrap: '.gnb-area',
                top: '.top-area',
                sub: '.gnb-sub-wrap',
                sub2depth: '.sub-depth2',
                btnAll: '.mnu-all a',
                btnMypage: '.link-mypage',
                mypageInfo: '.user-info-box'
            },
            layer: {
                name: '.pop-layer',
                wrap: '.pop-wrap',
                btn: '.btn-close, .dim'
            }
        },
        event: function () {
            var lThiz = this.element;
            var nPos = $(window).scrollTop();
            //searchForm
            var searchForm = $('.search-form');
            var searchInput = searchForm.find("input[type='text']");
            var searchClear = searchForm.find(".btn-clear");

            searchInput.on('input change', function () {
                var $this = $(this);
                var visible = Boolean($this.val());
                $(this).parents('.search-form').find('.btn-clear').toggleClass('hidden', !visible);
                $(this).parents('.search-form').toggleClass('active', visible);
            }).trigger('propertychange');

            searchForm.each(function () {
                if ($(this).find("input[type='text']").attr('value')) {
                    $(this).find(".btn-clear").removeClass('hidden');
                    // $(this).removeClass('active');
                }
            });

            searchInput.focus(function () {
                $(this).parents('.search-form').addClass('active');
            });
            searchInput.blur(function () {
                $(this).parents('.search-form').removeClass('active');
            });

            searchClear.on('click', function () {
                $(this).siblings('input[type=\'text\']').val('').trigger('change').focus();
                $(this).toggleClass('hidden', true);
            });

            //----------------------searchForm
            //GNB
            $(lThiz.gnb.wrap).find('.inner-box>ul>li').on('mouseover', function () {
                if ($(this).hasClass('mnu-all')) {
                    $(lThiz.gnb.sub).addClass('active');
                    if ($(lThiz.gnb.sub).hasClass('active')) {
                        $(lThiz.gnb.wrap).find('.inner-box>ul>li.mnu-all').addClass('active');
                    }
                    return false;
                } else {
                    $(this).addClass('active').siblings('li').removeClass('active');
                }
            });

            $(lThiz.gnb.wrap).find('.inner-box>ul>li').on('mouseleave', function (e) {
                if ($(this).hasClass('mnu-all')) {
                    $(lThiz.gnb.sub).removeClass('active');
                    if (!$(lThiz.gnb.sub).hasClass('active')) {
                        $(this).removeClass('active');
                    }
                    return false;
                } else {
                    $(this).removeClass('active');
                }
            });

            $(lThiz.gnb.sub).hover(function (e) {
                $(this).addClass('active');
                $(lThiz.gnb.wrap).find('.inner-box>ul>li.mnu-all').addClass('active');
            }, function () {
                $(this).removeClass('active');
                $(lThiz.gnb.wrap).find('.inner-box>ul>li.mnu-all').removeClass('active');

            });

            $(lThiz.gnb.btnMypage).on('mouseover', function () {
                $(this).next(lThiz.gnb.mypageInfo).fadeIn();
                $(this).addClass('active');
            });

            $(lThiz.gnb.top).on('mouseleave', function () {
                $(lThiz.gnb.mypageInfo).fadeOut();
                $(lThiz.gnb.btnMypage).removeClass('active');
            });


            $('.banner-slide').slick({
                arrows: false,
                dots: true
            });

            $(lThiz.layout.top).on('click', function (e) {
                e.preventDefault();
                $('html,body').animate({scrollTop: 0});
            });

            var productIdx = $('.clusiv-product-nav li.active').index();
            $('.clusiv-product-nav li a').on('mouseover', function () {
                $(this).parent('li').addClass('active').siblings('li').removeClass('active');
            });
            $('.clusiv-product-nav').on('mouseleave', function () {
                $('.clusiv-product-nav li').eq(productIdx).addClass('active').siblings('li').removeClass('active');
            });
            //--------------GNB

            $(document).ready(function () {
                var lNtop = $(window).scrollTop();
                var asidePay = $('.pay-total-wrap, .selected-wrap');
                var asideWrap = $('.order-area, .product-decs');
                var productMenu = $('.product-decs .tab-type5');
                var quickPos = $(window).height() - $(lThiz.layout.quick).offset().top;

                gnbFix(lNtop);//gnb
                quickFix(lNtop);//quick

                if (asidePay.length > 0) {
                    var asideTop = asidePay.offset().top - 100;//사이드바 상단 위치

                    chkFixed(lNtop);

                    function resetFixed() {//사이드바 위치 리셋
                        asidePay.removeClass("fixed");
                    }

                    function chkFixed(nTop) {
                        if (asideWrap.outerHeight() > asidePay.outerHeight()) {//컨텐츠 영역이 사이드바보다 길면

                            if (nTop > asideTop) {//중간에 새로고침했을때 위치 재설정
                                asidePay.addClass("fixed");
                                productMenu.addClass("fixed");
                            } else {
                                resetFixed();
                                productMenu.removeClass("fixed");
                            }

                            if (asidePay.hasClass("fixed")) {//사이드바 fixed됬을때
                                var scrollHeight = $(document).height();
                                var scrollPosition = $(window).height() + $(window).scrollTop();

                                if ((scrollHeight - scrollPosition) <= scrollHeight - (asideWrap.outerHeight() + asideWrap.offset().top)) {//컨텐츠영역 하단위치일때 사이드바 고정
                                    asidePay.removeClass("fixed");
                                    asidePay.addClass("bottom");
                                } else {//컨텐츠영역 하단위치 벗어나면 사이드바 고정품
                                    asidePay.addClass("fixed");
                                    asidePay.removeClass("bottom");
                                }
                            }
                        } else {
                            resetFixed();//컨텐츠 영역이 사이드바보다 짧으면 리셋
                        }
                    }
                }

                function gnbFix(lNtop) {
                    if (lNtop > 10) {
                        var h = -($(lThiz.layout.header).outerHeight() - $(lThiz.gnb.wrap).outerHeight()) + 'px';
                        $(lThiz.layout.header).css({
                            'transform': 'translateY(' + h + ')'
                        });
                    } else if (lNtop < $(lThiz.layout.header).find('.top-area').outerHeight()) {
                        $(lThiz.layout.header).css({
                            'transform': 'translateY(0)'
                        });
                    }
                }

                function quickFix(lNtop) {
                    if ($('.section-main').length > 0) {
                        if (lNtop > quickPos) {
                            $(lThiz.layout.quick).addClass('fixed');
                        } else {
                            $(lThiz.layout.quick).removeClass('fixed');
                        }
                    } else {
                        $(lThiz.layout.quick).addClass('fixed');
                    }
                }

                //tab
                $('.js_tab').find('a').on('click', function (e) {
                    e.preventDefault();
                    if (asidePay.length > 0) {
                        if (asidePay.hasClass('bottom')) {
                            asidePay.removeClass("bottom");
                        }
                        $('html,body').animate({scrollTop: asideWrap.offset().top + 'px'}, 0);
                        asidePay.addClass("fixed");
                    }
                    $(this).parent('li').addClass('active').siblings('li').removeClass('active');
                    $($(this).attr('href')).addClass('active').siblings('div').removeClass('active');
                });


                //toggle
                $('.btn-toggle-close').each(function () {
                    var parent = $(this).parent();
                    var toggleBox = $(this).parents().children('.js_toggle_box');
                    if (toggleBox.hasClass('close')) {
                        toggleBox.hide();
                        parent.addClass('close');
                    }
                });

                $('.btn-toggle-close').on('click', function (e) {
                    var parent = $(this).parent();
                    var toggleBox = $(this).parents().children('.js_toggle_box');
                    e.preventDefault();

                    if (parent.hasClass('close')) {
                        parent.removeClass('close');
                        toggleBox.removeClass('close');
                        toggleBox.show();
                    } else {
                        parent.addClass('close');
                        toggleBox.addClass('close');
                        toggleBox.hide();
                    }

                    bottomPosControll();
                });

                function bottomPosControll() {
                    if (asidePay.length > 0) {
                        $('html,body').animate({scrollTop: $(this).scrollTop() - 1 + 'px'}, 100);
                    }
                }

                //스크롤 컨트롤
                $(window).scroll(function (e) {
                    var lNtop = $(this).scrollTop();

                    e.preventDefault();

                    if (asidePay.length > 0) {
                        var scroll = $(window).scrollTop();
                        chkFixed(scroll);//스크롤 움질일때 위치값 넘김
                    }
                    gnbFix(lNtop);
                    quickFix(lNtop);
                });


            });
            //radio,checkbox
            $("input[type='checkbox'],input[type='radio']").each(function () {
                if ($(this).attr('checked')) {
                    $(this).parent().addClass('selected');
                } else {
                    $(this).parent().removeClass('selected');
                }
            });

            // checkbox
            $("input[type='checkbox']").change(function () {
                if ($(this).is(':checked')) {
                    $(this).parent().addClass('selected');
                    $(this).attr('checked', true);
                } else {
                    $(this).parent().removeClass('selected');
                    $(this).attr('checked', false);
                }
            });

            // radio
            $("input[type='radio']").change(function () {
                $('input:radio[name=' + $(this).attr('name') + ']').parent().removeClass('selected');
                $(this).parent().addClass('selected');
            });

            //select
            $("[class^='select-type'] select").on('change', function () {
                $(this).addClass('selected');
            });
            //hover
            $('.js_hover').hover(function () {
                var productBox = $(this).parent('.product-box');
                if (productBox.hasClass('active')) {
                    productBox.removeClass('active');
                } else {
                    productBox.addClass('active');
                }
            });
            $('.btn-tool-tip').hover(function () {
                $(this).toggleClass('active')
            });


            $('.time-sale-popup .slider').slick({
                dots: true
            });

        },
        layerPopUp: function (pOption) {
            /*   pOption
            *  {
            *  	 state : 'open'  OR  'close'
            *  	 selId : Layer Selector
            *  }
            */
            var lThiz = this;
            var lLayer = $(pOption.selId);
            var lLayerBox = $(pOption.selId).find(lThiz.element.layer.wrap);
            var playAre = lLayerBox.find('.pop-player');
            var iframe = playAre.html();

            if (pOption.st !== 'close') {
                if (playAre) {
                    playAre.html(iframe);
                    lLayer.find('iframe').attr('src', pOption.src);
                }
                lLayer.fadeIn();
                lLayer.find('.slick-slider').slick('setPosition');//slideSet
                lLayerBox.css('margin-left', '-' + lLayerBox.outerWidth() / 2 + 'px');
                if (lLayerBox.outerHeight() < $(document).height()) {
                    lLayerBox.css('margin-top', '-' + lLayerBox.outerHeight() / 2 + 'px');
                } else {
                    lLayerBox.css('top', '0');
                }
                if (pOption.st !== 'noDim') {
                    $('body').addClass('fixed');
                }
                if (pOption.st == 'full') {
                    lLayerBox.css('margin-top', '0');
                }
            } else {
                playAre.html('');
                $('body').removeClass('fixed');
                lLayer.fadeOut();
                playAre.html(iframe);
            }


            function layerClose(closeThiz) {

            }

            lLayer.find(lThiz.element.layer.btn).click(function (e) {
                e.preventDefault();
                playAre.html('');
                $('body').removeClass('fixed');
                $(this).closest(lThiz.element.layer.name).fadeOut();
                playAre.html(iframe);
            });


        }
    }
})();


$(document).ready(function () {
    UI.init();
});
```



- 예시 : 레이어 팝업

​    http://code.d2.co.kr/2019/ahc/pc/shop/html/guide/popup.html

```javascript
UI.layerPopUp({selId:'#join-result'});
```

- 그 페이지안에서 쓰는 플러그인이나, 이벤트들은 그 페이지내 html 하단에 작성



### 가이드 만들기

- 보통 한 프로젝트 내에서 공통으로 항상 쓰이는 것들을 컴포넌트화 
- 항목
  - color
  - font
  - text : title , list, 등
  - button
  - form
  - popup
  - icon
  - table
  - board
  - 상품관련 ( 쇼핑몰일 경우)
  - sub layout
- 페이지 마다 작업하면서 , sub 폴더 안에서 이루어지는 요소는 그 해당 scss 작업
- But, 다른 폴더의 서브페이지와 겹치면 공통화 하는게 낫지 않을까?
- 공통 뽑아 내는건, 처음에 가이더의 역할!! 후에는 프로젝트 하면서 서로간의 협업이 중요!
- 처음 하나의 프로젝트를 만들어 놓으면 그 이후에는 편리해지면서 점점 develop~
- 예시
  - 슬라이드
    - http://code.d2.co.kr/2019/ahc/pc/shop/html/main/main.html
    - http://code.d2.co.kr/2019/ahc/pc/shop/html/shopping/product_detail.html
  - 테이블예시
    - http://code.d2.co.kr/2019/ahc/pc/shop/html/mypage/mypage_wishlist.html
    - http://code.d2.co.kr/2019/ahc/pc/shop/html/mypage/mypage_review_list_able.html



