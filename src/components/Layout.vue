<template>
    <div class='container'>
      <div class="header">
          <div class="header_left">
              <img :src="logoSrc" alt="">
          </div>
          <div class="header_right">
            <div v-for="(val,key) in logoList">
            <a href="" v-bind:key="key">{{val}}</a> 
            </div>
          </div>
      </div>
      <!-- content -->
      <div>
            <router-view></router-view>
      </div>
      <div class="footer"><p>版权所有: 52xunyi.com</p></div>
    </div>
</template>

<script>
export default {
  name :"Layout",
  data: function (){
    return {
      logoSrc : require("../assets/logo.png"),
      logoList:["退出","登录","关于"]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
      
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
  display: block;
}
body {
  line-height: 1;
}
ol, ul {
  list-style: none;
}
blockquote, q {
  quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
  content: '';
  content: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
a {
  color: inherit;
  text-decoration: none;
}
body {
  background: #fff;
  font-family: "Helvetica Neue",Helvetica,Arial,"Hiragino Sans GB","Hiragino Sans GB W3","Microsoft YaHei UI","Microsoft YaHei","WenQuanYi Micro Hei",sans-serif;
  font-size: 14px;
  color: #222;
}
.container {
    width: 100%;
  .header {
    
  &::after{
    content:'';
    height: 0px;
    display:block;
    visibility: hidden;
    clear:both;
  }
    background: #dee;
    marging-left: 10%;
    marging-right: 10%;
    height: 100px;
    width: 100%;
    .header_left {
       float: left;
      img {
        width: 100px;
        height: 100px;
      }
    }
    .header_right {
    height: 100px;

      float: right;
       
    
    }
  }
  .footer {
     height: 100px;
     background: #dee;
      text-align: center;
      width: 100%;
    p {
     height: 100px;
     
      line-height:100px;
    }
  }
}


</style>
