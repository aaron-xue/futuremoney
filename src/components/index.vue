<template>
  <div id="index_wrap">
    <div id="main_nav">
      <div id="main_logo_top">
        <div id="main_logo_top_inner"></div>
      </div>
      <div id="main_nav_ck">
        <div @click="openOrCloseNav" :class="[navIsOpen?'main_nav_ck_open':'','main_nav_ck_inner']"></div>
      </div>
      <div id="change_language">
        <div id="change_language_inner">
          <span @click="changeToENG">ENG</span>
          <i></i>
          <span @click="changeToCN">CN</span>
          <div id="lang_posi"></div>
        </div>
      </div>
      <ul :class="[navIsOpen?'open_nav':'','main_navs']">
        <li :class="currentIdex==index?'active':''" v-for="(item, index) in navs" :key="index" @click="changeCurrentIndex(index)">{{item}}</li>
        <div id="main_navs_posi"></div>
      </ul>
    </div>
    <div class="tab_panel_wrap">
      <div class="tab_panel" id="tab_panel1">
        <div class="content"></div>
      </div>
      <div class="tab_panel" id="tab_panel2">
        <div class="content">
          <img class="con_tags" src="../assets/img/about.png"/>
          <span class="line1 tab_pane2_line"></span>
          <span class="line2 tab_pane2_line"></span>
          <h2>ABOUT FUTUREMONEY VENTURES</h2>
          <div class="scrollbar-rail_wrap">
            <div class="scrollbar-rail">
              <p>A pioneer and global-leading investment institution focused exclusively on Blockchain technology. We have multi-layer business division including Future Money Research Institute, and all kinds of Blockchain assets fund such as Equity Fund, Cryptocurrency Investment Fund, Quantitative Fund ,etc.</p>
              <br>
              <p>Our research&investment are mainly focusing on public blockchain, application protocol and financial services in the blockchain eco-system. A full range of post-investment services for invested projects will be provided, especially on community management and other scalable solutions.</p>
              <br>
              <p>We built up a Primary - secondary market linkage investment strategy to meet the investment needs of all kinds of investors.</p>
              <br>
              <p>With our diversified investment network where distributed in San Francisco, Seoul, Singapore, Moscow, Beijing and Shanghai, we have established consolidated strategic cooperation relationships with top projects and institutions.  </p>
              <br>
              <p>We possess the comprehensive strength of investing management of cryptographic digital asset investment，which lead us stand out among many investment institutions.</p>
            </div>
          </div>
          
        </div>
      </div>
      <div class="tab_panel" id="tab_panel3">
        <div class="content">
          <img class="con_tags" src="../assets/img/team.png"/>
          <div id="eo">
            <div class="eo_img"></div>
            <div id="eo_des">
              <h2>EO Hao</h2>
              <h3>Partner</h3>
              <p>Former investment banker and fixed income derivatives trader. He is a serial entrepreneur who has started multiple Fintech and Bitcoin startups in China & Indonesia.</p>
            </div>
          </div>
          <div id="steven">
            <div id="steven_des">
              <h2>Steven Li</h2>
              <h3>Partner</h3>
              <p>Former Investment Head at Ventech Capital, Qihu 360. Steven is experienced with equity financing, investor relations and  has invested in many unicorns.</p>
            </div>
            <div class="steven_img"></div>
          </div>
          <div id="tang">
            <div class="tang_img"></div>
            <div id="tang_des">
              <h2>Francis Tang</h2>
              <h3>Partner</h3>
              <p>Founder & CEO of Ziggurat Tech; Managing partner of Jenga Blockchain Capital. Francis is also an initiator of numbers of blockchain technology institution based in multiple Chinese Top Universities.</p>
            </div>

          </div>
          <div id="sam">
            <div id="sam_des">
              <h2>Sam Li</h2>
              <h3>Partner</h3>
              <p>Quant trader, used to work for UBS and Barclays trading department. He has more than 10 years of trading experiences.</p>
            </div>
            <div class="sam_img"></div>
          </div>
        </div>
      </div>
      <div class="tab_panel" id="tab_panel4">
        <div class="content">
          <img class="con_tags" src="../assets/img/highlights.png"/>
          <div class="logos"></div>
        </div>
      </div>
      <div class="tab_panel" id="tab_panel5">
        <div class="content">
          <img class="con_tags" src="../assets/img/runds.png"/>
          <div class="runds_wrap runds1">
            <h2>FUTUREMONEY VENTURES - PRIMARY MARKET FUND</h2>
            <p>As a globalized investment institution, we aim to achieve Full-cycle investment management capability. That’s why we are focusing on acquire rich resources on overseas and mainland projects, strong partnerships in the whole industry and building a top-listed research team. And we pride ourselves on being an acute investor and having a sharp business sense. Only in order to accelerate the future of Blockchain economy by supporting those Blockchain enabled companies with great potential.</p>
          </div>
          <div class="runds_wrap runds2">
            <h2>FUTUREMONEY QUANT - SECONDARY MARKET FUND</h2>
            <p>FutureMoney Quant is powered by Mobius - a quantitative trading solution developed by FutureMoney.  Mobius’s quantitative strategies team seeks to generate beta by combining rigorous fundamental research with mathematical and statistical models to identify and execute on investment opportunities. With our multiple investment strategies across market arbitrage and cross-variety arbitrage etc, we are seeking a stable asset growth in the relatively unsettled market.</p>
          </div>
        </div>
      </div>
      <div class="tab_panel" id="tab_panel6">
        <div class="content">
          <div class="bottom_logo"></div>
          <ul class="links">
            <li>
               <a href="javascript:;" class='icon-weixin'></a>
            </li>
            <li>
               <a href="javascript:;" class='icon-twitter'></a>
            </li>
            <li>
               <a href="javascript:;" class='icon-facebook'></a>
            </li>
            <li>
               <a href="javascript:;" class='icon-github'></a>
            </li>
            <li>
               <a href="javascript:;" class='icon-xinxi'></a>
            </li>
          </ul>
          <div class="copy_right">
            <p>E-mail:</p>
            <small>cooperation@futuremoneyventures.com</small>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "../assets/css/jquery.scrollbar.css";
import "../assets/js/jquery.scrollbar.min.js";
export default {
  name: "HelloWorld",
  data() {
    return {
      navIsOpen: false,
      navs: [
        "HOME",
        "ABOUT",
        "TEAM",
        "PORTFOLIO",
        "FUNDS",
        "CONTACT"
      ],
      currentIdex: 0
    };
  },
  mounted() {
    $(".scrollbar-rail").scrollbar();
    let tab_panels = $('.tab_panel')
    window.addEventListener('scroll', () => {
      let that = this;
      let scrollTop = $(document).scrollTop();
      tab_panels.each(function (index, element) {
        let contentItem = $(this);
        let offsetTop = contentItem.offset().top;
        if (scrollTop > offsetTop - 200) {
          that.currentIdex = index;
           $("#main_navs_posi").css("transform", `translateY(${44 * index}px)`);
        }
      });

    })
  },
  methods: {
    openOrCloseNav() {
      this.navIsOpen = !this.navIsOpen;
    },
    changeToENG() {
      $("#lang_posi").css("transform", "translateX(0) scaleX(1)");
    },
    changeToCN() {
      $("#lang_posi").css("transform", "translateX(44px) scaleX(.7)");
    },
    changeCurrentIndex(index) {
      this.currentIdex = index;
      $("#main_navs_posi").css("transform", `translateY(${44 * index}px)`);
      $('body,html').animate({ scrollTop: $('.tab_panel:eq(' + index + ')').offset().top - 50 }, 200);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang='less'>
#index_wrap {
  width: 100%;
  min-width: 1376px;
  #main_nav {
    width: 100%;
    height: 77px;
    background-color: #1b1b1b;
    position: fixed;
    left: 0;
    top: 0;
    z-index: 10;
    #main_nav_ck {
      float: left;
      width: 145px;
      height: 100%;
      margin-left: -100%;
      line-height: 77px;
      .main_nav_ck_inner {
        background: url(../assets/img/nav_open.png) no-repeat;
        cursor: pointer;
        width: 19px;
        height: 19px;
        display: inline-block;
        vertical-align: middle;
        margin-left: 126px;
        transition: all 0.3s;
        transform: rotateY(0deg);
      }
      .main_nav_ck_open {
        background: url(../assets/img/nav_close.png) no-repeat;
        transform: rotateY(360deg);
      }
    }
    #main_logo_top {
      float: left;
      width: 100%;
      height: 100%;
      #main_logo_top_inner {
        padding: 0 145px;
        height: 100%;
        background: url(../assets/img/logo_top.png) no-repeat;
        background-position: center;
      }
    }
    #change_language {
      float: left;
      width: 184px;
      height: 100%;
      margin-left: -184px;
      #change_language_inner {
        height: 100%;
        line-height: 77px;
        width: 78px;
        position: relative;
        span {
          display: inline-block;
          font-family: Roboto-Medium;
          font-size: 12px;
          font-weight: normal;
          font-stretch: normal;
          letter-spacing: 0px;
          color: #dcbf9e;
          cursor: pointer;
        }
        i {
          display: inline-block;
          width: 1px;
          height: 10px;
          background-color: #dcbf9e;
        }
        #lang_posi {
          position: absolute;
          bottom: 0;
          width: 24px;
          height: 2px;
          background-color: #dcbf9e;
          transition: all 0.5s;
        }
      }
    }
    .main_navs {
      position: absolute;
      height: 270px;
      width: 359px;
      left: 0;
      bottom: -270px;
      transition: all 0.5s 0.3s;
      transform: translateX(-100%);
      li {
        width: 230px;
        height: 44px;
        margin-left: 129px;
        cursor: pointer;
        font-family: Roboto-Medium;
        font-size: 15px;
        font-weight: normal;
        font-stretch: normal;
        line-height: 44px;
        letter-spacing: 0px;
        color: #584b3c;
        transition: color 0.5s;
        &:hover {
          color: #dcbf9e;
        }
      }
      .active {
        color: #dcbf9e;
      }
      #main_navs_posi {
        position: absolute;
        top: 19px;
        left: 0;
        width: 106px;
        height: 2px;
        background-color: #dcbf9e;
        transition: all 0.5s;
      }
    }
    .open_nav {
      transform: translateX(0);
    }
  }
  .tab_panel_wrap {
    background: #1b1b1b;
    .tab_panel {
      .content {
        position: relative;
        width: 1367px;
        margin: 0 auto;
        height: 100%;
        box-sizing: border-box;
        overflow: hidden;
        .con_tags {
          position: absolute;
          right: 0;
          top: 0;
          width: 12px;
        }
      }
    }
    #tab_panel1 {
      height: 850px;
      background: #000;
      .content {
        background: url(../assets/img/banner.jpg) no-repeat;
        background-position: center;
      }
    }
    #tab_panel2 {
      height: 720px;
      width: 1279px;
      margin: 0 auto;
      overflow: hidden;
      .content {
        margin: 102px 0 102px 106px;
        width: 1173px;
        height: 516px;
        background: url(../assets/img/F.jpg) no-repeat;
        background-position: center;
        background-size: cover;
        .tab_pane2_line {
          position: absolute;
          width: 43px;
          height: 3px;
          background-color: #dcbf9e;
        }
        .line1 {
          left: 196px;
          top: 57px;
        }
        .line2 {
          left: 196px;
          bottom: 0;
        }
        h2 {
          height: 30px;
          font-family: SourceHanSansCN-Bold;
          font-size: 30px;
          font-weight: normal;
          font-stretch: normal;
          letter-spacing: 0px;
          color: #dcbf9e;
          margin-top: 86px;
          margin-left: 196px;
        }
        .scrollbar-rail_wrap {
          width: 866px;
          height: 288px;
          font-family: SourceHanSansCN-Normal;
          font-size: 18px;
          font-weight: normal;
          font-stretch: normal;
          line-height: 27px;
          letter-spacing: 0px;
          color: rgba(220, 191, 158, 0.8);
          margin-left: 198px;
          margin-top: 49px;
          .scrollbar-rail {
            padding-right: 105px;
          }
          div {
            max-height: 288px;
          }
        }
      }
    }
    #tab_panel3 {
      height: 2208px;
      width: 1279px;
      margin: 0 auto;
      overflow: hidden;
      .content {
        margin: 200px 0 305px;
        width: 1279px;
        height: 1803px;
        #eo {
          height: 403px;
          width: 1174px;
          background: url(../assets/img/eo_bg.png) no-repeat;
          background-size: cover;
          background-position: center;
          margin: 36px 0 61px 105px;
          .eo_img {
            display: inline-block;
            height: 100%;
            background: url(../assets/img/eo.png) no-repeat;
            width: 275px;
            background-size: cover;
            background-position: center;
          }
          #eo_des {
            position: relative;
            display: inline-block;
            width: 730px;
            height: 270px;
            margin-left: 120px;
            vertical-align: bottom;
            padding-top: 55px;
            box-sizing: border-box;
            &::before {
              content: "";
              position: absolute;
              left: 0;
              top: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            &::after {
              content: "";
              position: absolute;
              left: 0;
              bottom: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            h2 {
              height: 33px;
              font-family: SourceHanSansCN-Bold;
              font-size: 25px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
            }
            h3 {
              height: 33px;
              font-family: SourceHanSansCN-Normal;
              font-size: 20px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
            }
            p {
              font-family: SourceHanSansCN-Normal;
              font-size: 18px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 27px;
              letter-spacing: 0px;
              color: #dcbf9e;
              margin-top: 32px;
            }
          }
        }
        #steven {
          height: 387px;
          width: 1170px;
          background: url(../assets/img/steven_bg.png) no-repeat;
          background-size: cover;
          background-position: 0 0;
          margin: 0 0 83px 0;
          .steven_img {
            display: inline-block;
            height: 100%;
            background: url(../assets/img/steven.png) no-repeat;
            width: 285px;
            background-size: cover;
            background-position: center;
          }
          #steven_des {
            position: relative;
            display: inline-block;
            width: 669px;
            height: 270px;
            margin-right: 100px;
            margin-left: 110px;
            vertical-align: bottom;
            padding-top: 55px;
            box-sizing: border-box;
            &::before {
              content: "";
              position: absolute;
              right: 0;
              top: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            &::after {
              content: "";
              position: absolute;
              right: 0;
              bottom: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            h2 {
              height: 33px;
              font-family: SourceHanSansCN-Bold;
              font-size: 25px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
              text-align: right;
            }
            h3 {
              height: 33px;
              font-family: SourceHanSansCN-Normal;
              font-size: 20px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
              text-align: right;
            }
            p {
              font-family: SourceHanSansCN-Normal;
              font-size: 18px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 27px;
              letter-spacing: 0px;
              color: #dcbf9e;
              margin-top: 32px;
            }
          }
        }
        #tang {
          height: 374px;
          width: 1174px;
          background: url(../assets/img/tang_bg.png) no-repeat;
          background-size: cover;
          background-position: center;
          margin: 0 0 76px 105px;
          .tang_img {
            display: inline-block;
            height: 100%;
            background: url(../assets/img/tang.png) no-repeat;
            width: 274px;
            background-size: cover;
            background-position: center;
          }
          #tang_des {
            position: relative;
            display: inline-block;
            width: 730px;
            height: 270px;
            margin-left: 120px;
            vertical-align: bottom;
            padding-top: 55px;
            box-sizing: border-box;
            &::before {
              content: "";
              position: absolute;
              left: 0;
              top: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            &::after {
              content: "";
              position: absolute;
              left: 0;
              bottom: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            h2 {
              height: 33px;
              font-family: SourceHanSansCN-Bold;
              font-size: 25px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
            }
            h3 {
              height: 33px;
              font-family: SourceHanSansCN-Normal;
              font-size: 20px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
            }
            p {
              font-family: SourceHanSansCN-Normal;
              font-size: 18px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 27px;
              letter-spacing: 0px;
              color: #dcbf9e;
              margin-top: 32px;
            }
          }
        }
        #sam {
          height: 381px;
          width: 1165px;
          background: url(../assets/img/sam_bg.png) no-repeat;
          background-size: cover;
          background-position: 0 0;
          margin: 0 114px 0 0;
          .sam_img {
            display: inline-block;
            height: 100%;
            background: url(../assets/img/sam.png) no-repeat;
            width: 280px;
            background-size: cover;
            background-position: center;
          }
          #sam_des {
            position: relative;
            display: inline-block;
            width: 669px;
            height: 270px;
            margin-right: 100px;
            margin-left: 110px;
            vertical-align: bottom;
            padding-top: 55px;
            box-sizing: border-box;
            &::before {
              content: "";
              position: absolute;
              right: 0;
              top: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            &::after {
              content: "";
              position: absolute;
              right: 0;
              bottom: 0;
              width: 90px;
              height: 2px;
              background-color: #dcbf9e;
            }
            h2 {
              height: 33px;
              font-family: SourceHanSansCN-Bold;
              font-size: 25px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
              text-align: right;
            }
            h3 {
              height: 33px;
              font-family: SourceHanSansCN-Normal;
              font-size: 20px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 33px;
              letter-spacing: 0px;
              color: #dcbf9e;
              text-align: right;
            }
            p {
              font-family: SourceHanSansCN-Normal;
              font-size: 18px;
              font-weight: normal;
              font-stretch: normal;
              line-height: 27px;
              letter-spacing: 0px;
              color: #dcbf9e;
              margin-top: 32px;
            }
          }
        }
      }
    }
    #tab_panel4 {
      width: 100%;
      background: #000;
      height: 415px;
      overflow: hidden;
      .content {
        width: 1277px;
        height: 256px;
        margin: 34px auto 0;
        .logos {
          width: 973px;
          height: 179px;
          background: url(../assets/img/logos.png) no-repeat;
          margin: 77px auto 0;
          background-size: contain;
        }
      }
    }
    #tab_panel5 {
      height: 1043px;
      width: 1275px;
      margin: 0 auto;
      overflow: hidden;
      .content {
        margin: 202px 0 0;
        width: 1275px;
        height: 563px;
        .runds_wrap{
          width: 1056px;
          height: 196px;
          margin-top: 88px;
          padding-left: 97px;
          position: relative;
          h2{
            height: 30px;
            font-family: SourceHanSansCN-Bold;
            font-size: 30px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 30px;
            letter-spacing: 0px;
            color: #dcbf9e;
          }
          p{
            font-family: SourceHanSansCN-Normal;
            font-size: 18px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 27px;
            letter-spacing: 0px;
            color: rgba(220, 191, 158, 0.8);
            margin-top: 44px;
          }
        }
        .runds1{
          &::before{
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 40px;
            height: 40px;
            background: url(../assets/img/main_icon2.png) no-repeat;
          }
        }
        .runds2{
          &::before{
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 40px;
            height: 40px;
            background: url(../assets/img/main_icon1.png) no-repeat;
          }
        }
      }
    }
    #tab_panel6{
      width: 100%;
      background: #000;
      height: 371px;
      overflow: hidden;
      .content {
        width: 1061px;
        height: 242px;
        margin: 48px auto 0;
        .bottom_logo{
          width: 285px;
          height: 41px;
          background: url(../assets/img/logo_bottom.png) no-repeat;
          background-position: center;
          float: left;
        }
        .links{
          width: 365px;
          height: 31px;
          float: right;
          li {
            display: inline-block;
            margin-right: 44px;
            font-size: 33px;
            a:link::before{
              color: #bcbcbb;
            }
            a:active::before{
              color: #fff;
            }
            a:hover::before{
              color: #fff;
            }
          }
          li:last-of-type {
            margin-right: 0;
          }
        }
        .copy_right{
          margin-top: 155px;
          p{
            font-family: Roboto-Medium;
            font-size: 18px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 46px;
            letter-spacing: 0px;
            color: #b79471;
          }
          small{
            font-family: Roboto-Medium;
            font-size: 20px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 46px;
            letter-spacing: 0px;
            color: #dcbf9e;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 960px) {
  #index_wrap {
    min-width: auto;
    #main_nav {
      width: 100%;
      height: 45px;
      #main_nav_ck {
        float: none;
        overflow: hidden;
        margin-left: 0;
        line-height: 45px;
        padding-right: 19px;
        background-color: #1b1b1b;
        width: auto;
        .main_nav_ck_inner {
          float: right;
          width: 10px;
          height: 10px;
          background-size: contain;
          margin: 19px 0 0 0;
        }
      }
      #main_logo_top {
        float: left;
        width: 200px;
        padding-left: 20px;
        background-color: #1b1b1b;
        #main_logo_top_inner {
          padding: 0;
          height: 100%;
          width: 85px;
          height: 45px;
          background: url(../assets/img/logo_top.png) no-repeat;
          background-size: contain;
          background-position: center;
        }
      }
      #change_language {
        display: none;
      }
      .main_navs {
        position: absolute;
        height: 270px;
        width: 100%;
        left: 0;
        bottom: -272px;
        transition: all 0.5s 0.3s;
        transform: translateY(-100%);
        z-index: -2;
        li {
          width: 100%;
          height: 45px;
          margin-left: 0;
          cursor: pointer;
          font-family: Roboto-Medium;
          font-size: 15px;
          font-weight: normal;
          font-stretch: normal;
          line-height: 45px;
          letter-spacing: 0px;
          color: #584b3c;
          transition: color 0.5s;
          text-align: right;
          padding-right: 19px;
          border-bottom: 1px solid rgba(220, 191, 158, 0.5);
          box-sizing: border-box;
          background-color: #020202;
          &:hover {
            color: #dcbf9e;
          }
          &:first-of-type {
            border-top: 2px solid #dcbf9e;
          }
        }
        .active {
          color: #dcbf9e;
        }
        #main_navs_posi {
          display: none;
        }
      }
      .open_nav {
        transform: translateY(0);
      }
    }
    .tab_panel_wrap {
      .tab_panel {
        min-width: 355px;
        .content {
          width: 355px;
          margin: 0 auto;
          height: 100%;
          .con_tags {
            right: 0;
            top: 0;
            width: 5px;
          }
        }
      }
      #tab_panel1 {
        height: 225px;
        background: #000;
        .content {
          background: url(../assets/img/banner.jpg) no-repeat;
          background-position: center;
          background-size: cover;
        }
      }
      #tab_panel2 {
        height: 328px;
        width: 355px;
        background: #1b1b1b;
        overflow: hidden;
        .content {
          margin: 32px auto;
          width: 355px;
          height: 246px;
          background: url(../assets/img/F.jpg) no-repeat;
          // background-position: center;
          background-size: contain;
          .tab_pane2_line {
            position: absolute;
            width: 14px;
            height: 2px;
            background-color: #dcbf9e;
          }
          .line1 {
            left: 59px;
            top: 17px;
          }
          .line2 {
            left: 59px;
            bottom: 0;
          }
          h2 {
            height: 20px;
            font-family: SourceHanSansCN-Bold;
            font-size: 12px;
            font-weight: normal;
            font-stretch: normal;
            letter-spacing: 0px;
            color: #dcbf9e;
            margin-top: 41px;
            margin-left: 60px;
          }
          .scrollbar-rail_wrap {
            width: 265px;
            height: 150px;
            font-family: SourceHanSansCN-Normal;
            font-size: 12px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 14px;
            letter-spacing: 0px;
            color: rgba(220, 191, 158, 0.8);
            margin-top: 12px;
            margin-left: 60px;
            .scrollbar-rail {
              padding-right: 25px;
            }
            div {
              max-height: 150px;
            }
          }
        }
      }
      #tab_panel3 {
        height: 804px;
        width: 100%;
        background: #1b1b1b;
        overflow: hidden;
        .content {
          margin: 0 auto;
          width: 355px;
          #eo {
            height: 144px;
            width: auto;
            background: url(../assets/img/eo_bg_mobile.png) no-repeat;
            background-size: contain;
            margin: 0 0 41px 0;
            .eo_img {
              display: inline-block;
              height: 100%;
              background: url(../assets/img/eo.png) no-repeat;
              width: 95px;
              background-size: cover;
              background-position: center;
            }
            #eo_des {
              position: relative;
              display: inline-block;
              width: 230px;
              height: 120px;
              margin-left: 20px;
              vertical-align: bottom;
              padding-top: 16px;
              box-sizing: border-box;
              &::before {
                content: "";
                position: absolute;
                left: 0;
                top: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              &::after {
                content: "";
                position: absolute;
                left: 0;
                bottom: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              h2 {
                height: 17px;
                font-family: SourceHanSansCN-Bold;
                font-size: 15px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
              }
              h3 {
                height: 17px;
                font-family: SourceHanSansCN-Normal;
                font-size: 12px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
              }
              p {
                width: 120%;
                font-family: SourceHanSansCN-Normal;
                font-weight: normal;
                font-stretch: normal;
                line-height: 14px;
                letter-spacing: 0px;
                color: #dcbf9e;
                margin-top: 5px;
                font-size: 10px;
                -webkit-transform: scale(0.8);
                transform-origin: left center;
              }
            }
          }
          #steven {
            height: 138px;
            width: auto;
            background: url(../assets/img/steven_bg_mobile.png) no-repeat;
            background-size: contain;
            margin: 0 0 50px 0;
            .steven_img {
              display: inline-block;
              height: 100%;
              background: url(../assets/img/steven.png) no-repeat;
              width: 95px;
              background-size: cover;
              background-position: center;
            }
            #steven_des {
              position: relative;
              // display: inline-block;
              width: 230px;
              height: 120px;
              margin-left: 20px;
              margin-right: 0;
              vertical-align: bottom;
              padding-top: 16px;
              box-sizing: border-box;
              float: right;
              margin-top: 20px;
              &::before {
                content: "";
                position: absolute;
                left: 0;
                top: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              &::after {
                content: "";
                position: absolute;
                left: 0;
                bottom: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              h2 {
                height: 17px;
                font-family: SourceHanSansCN-Bold;
                font-size: 15px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
                text-align: left;
              }
              h3 {
                height: 17px;
                font-family: SourceHanSansCN-Normal;
                font-size: 12px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
                text-align: left;
              }
              p {
                width: 120%;
                font-family: SourceHanSansCN-Normal;
                font-weight: normal;
                font-stretch: normal;
                line-height: 14px;
                letter-spacing: 0px;
                color: #dcbf9e;
                margin-top: 5px;
                font-size: 10px;
                -webkit-transform: scale(0.8);
                transform-origin: left center;
              }
            }
          }
          #tang {
            height: 127px;
            width: auto;
            background: url(../assets/img/tang_bg_mobile.png) no-repeat;
            background-size: contain;
            margin: 0 0 51px 0;
            .tang_img {
              display: inline-block;
              height: 100%;
              background: url(../assets/img/tang.png) no-repeat;
              width: 90px;
              background-size: cover;
              background-position: center;
            }
            #tang_des {
              position: relative;
              display: inline-block;
              width: 230px;
              height: 120px;
              margin-left: 30px;
              vertical-align: bottom;
              padding-top: 16px;
              box-sizing: border-box;
              &::before {
                content: "";
                position: absolute;
                left: 0;
                top: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              &::after {
                content: "";
                position: absolute;
                left: 0;
                bottom: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              h2 {
                height: 17px;
                font-family: SourceHanSansCN-Bold;
                font-size: 15px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
              }
              h3 {
                height: 17px;
                font-family: SourceHanSansCN-Normal;
                font-size: 12px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
              }
              p {
                width: 120%;
                font-family: SourceHanSansCN-Normal;
                font-weight: normal;
                font-stretch: normal;
                line-height: 14px;
                letter-spacing: 0px;
                color: #dcbf9e;
                margin-top: 5px;
                font-size: 10px;
                -webkit-transform: scale(0.8);
                transform-origin: left center;
              }
            }
          }
          #sam {
            height: 128px;
            width: auto;
            background: url(../assets/img/sam_bg_mobile.png) no-repeat;
            background-size: contain;
            margin: 0;
            .sam_img {
              display: inline-block;
              height: 100%;
              background: url(../assets/img/sam.png) no-repeat;
              width: 95px;
              background-size: cover;
              background-position: center;
            }
            #sam_des {
              position: relative;
              // display: inline-block;
              width: 230px;
              height: 120px;
              margin-left: 20px;
              margin-right: 0;
              vertical-align: bottom;
              padding-top: 16px;
              box-sizing: border-box;
              float: right;
              margin-top: 20px;
              &::before {
                content: "";
                position: absolute;
                left: 0;
                top: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              &::after {
                content: "";
                position: absolute;
                left: 0;
                bottom: 0;
                width: 29px;
                height: 1px;
                background-color: #dcbf9e;
              }
              h2 {
                height: 17px;
                font-family: SourceHanSansCN-Bold;
                font-size: 15px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
                text-align: left;
              }
              h3 {
                height: 17px;
                font-family: SourceHanSansCN-Normal;
                font-size: 12px;
                font-weight: normal;
                font-stretch: normal;
                line-height: 17px;
                letter-spacing: 0px;
                color: #dcbf9e;
                text-align: left;
              }
              p {
                width: 120%;
                font-family: SourceHanSansCN-Normal;
                font-weight: normal;
                font-stretch: normal;
                line-height: 14px;
                letter-spacing: 0px;
                color: #dcbf9e;
                margin-top: 5px;
                font-size: 10px;
                -webkit-transform: scale(0.8);
                transform-origin: left center;
              }
            }
          }
        }
      }
      #tab_panel4 {
        width: 100%;
        background: #000;
        height: 130px;
        overflow: hidden;
        .content {
          width: 355px;
          height: 81px;
          margin: 8px auto 0;
          .logos {
            width: 292px;
            height: 54px;
            background: url(../assets/img/logos.png) no-repeat;
            margin: 27px auto 0;
            background-size: contain;
          }
        }
      }
      #tab_panel5 {
      height: 530px;
      width: 100%;
      margin: 0 auto;
      overflow: hidden;
      background: #1b1b1b;
      .content {
        margin: 51px auto 0;
        width: 355px;
        background: #1b1b1b;
        // height: 211px;
        .runds_wrap{
          width: 331px;
          // height: 74px;
          margin-top: 19px;
          padding-left: 30px;
          position: relative;
          h2{
            height: 14px;
            font-family: SourceHanSansCN-Bold;
            font-size: 12px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 14px;
            letter-spacing: 0px;
            color: #dcbf9e;
          }
          p{
            font-family: SourceHanSansCN-Normal;
            font-size: 12px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 14px;
            letter-spacing: 0px;
            color: rgba(220, 191, 158, 0.8);
            margin-top: 11px;
          }
        }
        .runds1{
          &::before{
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 12px;
            height: 12px;
            background: url(../assets/img/main_icon2.png) no-repeat;
            background-size: cover;
          }
        }
        .runds2{
          &::before{
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 12px;
            height: 12px;
            background: url(../assets/img/main_icon1.png) no-repeat;
             background-size: cover;
          }
        }
      }
    }
    #tab_panel6{
      width: 100%;
      background: #000;
      height: 155px;
      overflow: hidden;
      .content {
        width: 100%;
        height: 100%;
        margin: 0;
        .bottom_logo{
          width: 91px;
          height: 13px;
          background: url(../assets/img/logo_bottom.png) no-repeat;
          background-position: center;
          background-size: cover;
          float: none;
          margin: 25px auto 0;
        }
        .links{
          width: 141px;
          height: 12px;
          margin: 33px auto 18px;
          float: none;
          li {
            display: inline-block;
            margin-right: 15px;
            font-size: 12px;
            a:link::before{
              color: #bcbcbb;
            }
            a:active::before{
              color: #fff;
            }
            a:hover::before{
              color: #fff;
            }
          }
          li:last-of-type {
            margin-right: 0;
          }
        }
        .copy_right{
          margin-top: 18px;
          p{
            display: none;
          }
          small{
            font-family: Roboto-Medium;
            font-size: 12px;
            font-weight: normal;
            font-stretch: normal;
            line-height: 23px;
            letter-spacing: 0px;
            color: #dcbf9e;
            text-align: center;
            display: block;
          }
        }
      }
    }
    }
  }
}
</style>
