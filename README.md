![](http://i.v2ex.co/kNlD5E2c.png)

## 前言
多说是一款社会化评论系统，她改变了网站与用户之间，用户与用户之间的互动方式。当然Disqus在大家心目中可能更加具有影响力，而我选择多说的原因也很简单，一句话概括来说就是“接地气的本地化评论托管服务”。之前看到很多朋友自豪的使用WordPress时会选择多说作为第三方评论插件，民间的高手们也根据官方的API开发出一些十分有趣的隐藏属性。因为现在自己使用GitHub+Hexo搭建的静态Blog，也希望通过多说自定义CSS和多说评论显示User Agent让评论动感起来，文章记录了自己所执行的真实步骤，扩展阅读和原文中也会标注参考链接和注意点，embed.default.css和embed.js文件托管在GitHub上，欢迎大家分享自己的经验，我们一起完善这些简单而有趣的小功能。

>感谢多说团队和那些无私的开发者们

---

## 更新历史

2015年04月25日 - 修复Font Awesome图标显示，增加动态效果图展示
2015年04月24日 - 初稿

阅读原文 - http://wsgzao.github.io/post/duoshuo/

扩展阅读

- duoshuo-mod - https://github.com/wsgzao/duoshuo-mod
- 出色的自定义效果展示 - http://dev.duoshuo.com/docs/4ff1cfd0397309552c000017
- HelloDog Index - http://wsgzao.github.io/index/#Hexo

---

## 多说自定义CSS

>主要参考@V说，他的文章中还分享了额外9种特效，满足大家Duang的欲望哈

多说自定义CSS 让你的多说评论动感起来 - http://www.vsay.cn/one-more-custom-css-lets-you-say-comments-city.html

![](http://ww3.sinaimg.cn/large/7207510dgw1erhrcp15bzg20dj0bm7l2.gif)

### 头像水平翻转

``` css
/*Head Start*/
#ds-thread #ds-reset ul.ds-comments-tabs li.ds-tab a.ds-current {
    border: 0px;
    color: #6D6D6B;
    text-shadow: none;
    background: #F3F3F3;
}

#ds-thread #ds-reset .ds-highlight {
    font-family: Microsoft YaHei, "Helvetica Neue", Helvetica, Arial, Sans-serif;
    ;font-size: 100%;
    color: #6D6D6B !important;
}

#ds-thread #ds-reset ul.ds-comments-tabs li.ds-tab a.ds-current:hover {
    color: #696a52;
    background: #F2F2F2;
}

#ds-thread #ds-reset a.ds-highlight:hover {
    color: #696a52 !important;
}

#ds-thread {
    padding-left: 30px;
}

#ds-thread #ds-reset li.ds-post,#ds-thread #ds-reset #ds-hot-posts {
    overflow: visible;
}

#ds-thread #ds-reset .ds-post-self {
    padding: 10px 0 10px 10px;
}

#ds-thread #ds-reset li.ds-post,#ds-thread #ds-reset .ds-post-self {
    border: 0 !important;
}

#ds-reset .ds-avatar, #ds-thread #ds-reset ul.ds-children .ds-avatar {
    top: 15px;
    left: -20px;
    padding: 5px;
    width: 36px;
    height: 36px;
    box-shadow: -1px 0 1px rgba(0,0,0,.15) inset;
    border-radius: 46px;
    background: #FAFAFA;
}

#ds-thread .ds-avatar a {
    display: inline-block;
    padding: 1px;
    width: 32px;
    height: 32px;
    border: 1px solid #b9baa6;
    border-radius: 50%;
    background-color: #fff !important;
}

#ds-thread .ds-avatar a:hover {
}

#ds-thread .ds-avatar > img {
    margin: 2px 0 0 2px;
}

#ds-thread #ds-reset .ds-replybox {
    box-shadow: none;
}

#ds-thread #ds-reset ul.ds-children .ds-replybox.ds-inline-replybox a.ds-avatar,
#ds-reset .ds-replybox.ds-inline-replybox a.ds-avatar {
    left: 0;
    top: 0;
    padding: 0;
    width: 32px !important;
    height: 32px !important;
    background: none;
    box-shadow: none;
}

#ds-reset .ds-replybox.ds-inline-replybox a.ds-avatar img {
    width: 32px !important;
    height: 32px !important;
    border-radius: 50%;
}

#ds-reset .ds-replybox a.ds-avatar,
#ds-reset .ds-replybox .ds-avatar img {
    padding: 0;
    width: 50px !important;
    height: 50px !important;
    border-radius: 5px;
}

#ds-reset .ds-avatar img {
    width: 32px !important;
    height: 32px !important;
    border-radius: 32px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.22);
    -webkit-transition: .8s all ease-in-out;
    -moz-transition: .4s all ease-in-out;
    -o-transition: .4s all ease-in-out;
    -ms-transition: .4s all ease-in-out;
    transition: .4s all ease-in-out;
}

.ds-post-self:hover .ds-avatar img {
    -webkit-transform: rotateX(360deg);
    -moz-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    transform: rotate(360deg);
}

#ds-thread #ds-reset .ds-comment-body {
    -webkit-transition-delay: initial;
    -webkit-transition-duration: 0.4s;
    -webkit-transition-property: all;
    -webkit-transition-timing-function: initial;
    background: #F7F7F7;
    padding: 15px 15px 15px 47px;
    border-radius: 5px;
    box-shadow: #B8B9B9 0 1px 3px;
    border: white 1px solid;
}

#ds-thread #ds-reset ul.ds-children .ds-comment-body {
    padding-left: 15px;
}

#ds-thread #ds-reset .ds-comment-body p {
    color: #787968;
}

#ds-thread #ds-reset .ds-comments {
    border-bottom: 0px;
}

#ds-thread #ds-reset .ds-powered-by {
    display: none;
}

#ds-thread #ds-reset .ds-comments a.ds-user-name {
    font-weight: normal;
    color: #3D3D3D !important;
}

#ds-thread #ds-reset .ds-comments a.ds-user-name:hover {
    color: #D32 !important;
}

#ds-thread #ds-reset #ds-bubble {
    display: none !important;
}

#ds-thread #ds-reset #ds-hot-posts {
    border: 0;
}

#ds-reset #ds-hot-posts .ds-gradient-bg {
    background: none;
}

#ds-thread #ds-reset .ds-comment-body:hover {
    background-color: #F1F1F1;
    -webkit-transition-delay: initial;
    -webkit-transition-duration: 0.4s;
    -webkit-transition-property: all;
    -webkit-transition-timing-function: initial;
}
/*Head End*/
```

### 多说后台自定义CSS

>设置步骤超级简单，登录多说后台->设置->基本设置->自定义CSS

![](http://ww1.sinaimg.cn/large/7207510dgw1ergrzty3c5j20mm0i4dj7.jpg)

## 多说评论显示UA(User Agent)

>主要参考@myhloli和@搜索客，灰常感谢

多说评论框UA显示/博主标记 - http://myhloli.com/duoshuo-ua-and-admin-tab.html

多说回复后显示浏览器及操作系统信息（Useragent） - http://ssk.91txh.com/209

### 本地化embed.js

1.下载embed.js

多说官方 - http://static.duoshuo.com/embed.js

偷懒可以下载我当前使用的 - http://wsgzao.github.io/embed.js

2.获取多说ID

方法一：在文章下方登录后评论点击头像可获取多说ID

方法二：访问多说后台，http://duoshuo.com/settings/ ，点击你的用户名，地址栏中会出现如如下的ID地址
http://duoshuo.com/profile/867394/

3.本地修改embed.js

>注意修改e.user_id多说ID，可以自定义ssk前端显示昵称

``` js
//移动客户端判断开始
function checkMobile() {
    var isiPad = navigator.userAgent.match(/iPad/i) != null;
    if (isiPad) {
        return false;
    }
    var isMobile = navigator.userAgent.match(/iphone|android|phone|mobile|wap|netfront|x11|java|opera mobi|opera mini|ucweb|windows ce|symbian|symbianos|series|webos|sony|blackberry|dopod|nokia|samsung|palmsource|xda|pieplus|meizu|midp|cldc|motorola|foma|docomo|up.browser|up.link|blazer|helio|hosin|huawei|novarra|coolpad|webos|techfaith|palmsource|alcatel|amoi|ktouch|nexian|ericsson|philips|sagem|wellcom|bunjalloo|maui|smartphone|iemobile|spice|bird|zte-|longcos|pantech|gionee|portalmmm|jig browser|hiptop|benq|haier|^lct|320x320|240x320|176x220/i) != null;
    if (isMobile) {
        return true;
    }
    return false;
}
//移动客户端判断结束
//管理员判断开始
function sskadmin(e) {
    var ssk = '';
    if (e.user_id == 867394) {
        if (checkMobile()) {
            ssk = '<span class="ua"><span class="sskadmin">R00T</span></span><br><br>';
        } else {
            ssk = '<span class="ua"><span class="sskadmin">R00T</span></span>';
        }
    } else {
        if (checkMobile()) {
            ssk = '<br><br>';
        }
    }
    return ssk;
}
//管理员判断结束
//显UA开始
function ua(e) {
    var r = new Array;
    var outputer = '';
    if (r = e.match(/FireFox\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_firefox"><i class="fa fa-globe"></i> Mozilla FireFox' + ' ' + r1[1]
    } else if (r = e.match(/Maxthon([\d]*)\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_maxthon"><i class="fa fa-globe"></i> Maxthon' + ' ' + r1[1]
    } else if (r = e.match(/BIDUBrowser([\d]*)\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_ucweb"><i class="fa fa-globe"></i> 百度浏览器' + ' ' + r1[1]
    } else if (r = e.match(/UBrowser([\d]*)\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_ucweb"><i class="fa fa-globe"></i> UCBrowser' + ' ' + r1[1]
    } else if (r = e.match(/UCBrowser([\d]*)\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_ucweb"><i class="fa fa-globe"></i> UCBrowser' + ' ' + r1[1]
    } else if (r = e.match(/MetaSr/ig)) {
        outputer = '<span class="ua_sogou"><i class="fa fa-globe"></i> 搜狗浏览器'
    } else if (r = e.match(/2345Explorer/ig)) {
        outputer = '<span class="ua_2345explorer"><i class="fa fa-globe"></i> 2345王牌浏览器'
    } else if (r = e.match(/2345chrome/ig)) {
        outputer = '<span class="ua_2345chrome"><i class="fa fa-globe"></i> 2345加速浏览器'
    } else if (r = e.match(/LBBROWSER/ig)) {
        outputer = '<span class="ua_lbbrowser"><i class="fa fa-globe"></i> 猎豹安全浏览器'
    } else if (r = e.match(/MicroMessenger\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_qq"><i class="fa fa-weixin"></i> 微信' + ' ' + r1[1]
        /*.split('/')[0]*/
    } else if (r = e.match(/QQBrowser\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_qq"><i class="fa fa-globe"></i> QQ浏览器' + ' ' + r1[1]
        /*.split('/')[0]*/
    } else if (r = e.match(/QQ\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_qq"><i class="fa fa-globe"></i> QQ浏览器' + ' ' + r1[1]
        /*.split('/')[0]*/
    } else if (r = e.match(/MiuiBrowser\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_mi"><i class="fa fa-globe"></i> Miui浏览器' + ' ' + r1[1]
        /*.split('/')[0]*/
    } else if (r = e.match(/Chrome([\d]*)\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_chrome"><i class="fa fa-globe"></i> Chrome' + ' ' + r1[1]
        /*.split('.')[0]*/
    } else if (r = e.match(/safari\/([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_apple"><i class="fa fa-globe"></i> Apple Safari' + ' ' + r1[1]
    } else if (r = e.match(/Opera[\s|\/]([^\s]+)/ig)) {
        var r1 = r[0].split("/");
        outputer = '<span class="ua_opera"><i class="fa fa-globe"></i> Opera' + ' ' + r1[1]
    } else if (r = e.match(/Trident\/7.0/gi)) {
        outputer = '<span class="ua_ie"><i class="fa fa-globe"></i> Internet Explorer 11'
    } else if (r = e.match(/MSIE\s([^\s|;]+)/gi)) {
        outputer = '<span class="ua_ie"><i class="fa fa-globe"></i> Internet Explorer' + ' ' + r[0]
        /*.replace('MSIE', '').split('.')[0]*/
    } else {
        outputer = '<span class="ua_other"><i class="fa fa-globe"></i> 其它浏览器'
    }
    if (checkMobile()) {
        Mobile = '<br><br>';
    } else {
        Mobile = '';
    }
    return outputer + "</span>" + Mobile;
}
function os(e) {
    var os = '';
    if (e.match(/win/ig)) {
        if (e.match(/nt 5.1/ig)) {
            os = '<span class="os_xp"><i class="fa fa-desktop"></i> Windows XP'
        } else if (e.match(/nt 6.1/ig)) {
            os = '<span class="os_7"><i class="fa fa-desktop"></i> Windows 7'
        } else if (e.match(/nt 6.2/ig)) {
            os = '<span class="os_8"><i class="fa fa-desktop"></i> Windows 8'
        } else if (e.match(/nt 6.3/ig)) {
            os = '<span class="os_8_1"><i class="fa fa-desktop"></i> Windows 8.1'
        } else if (e.match(/nt 10.0/ig)) {
            os = '<span class="os_8_1"><i class="fa fa-desktop"></i> Windows 10'
        } else if (e.match(/nt 6.0/ig)) {
            os = '<span class="os_vista"><i class="fa fa-desktop"></i> Windows Vista'
        } else if (e.match(/nt 5/ig)) {
            os = '<span class="os_2000"><i class="fa fa-desktop"></i> Windows 2000'
        } else {
            os = '<span class="os_windows"><i class="fa fa-desktop"></i> Windows'
        }
    } else if (e.match(/android/ig)) {
        os = '<span class="os_android"><i class="fa fa-android"></i> Android'
    } else if (e.match(/ubuntu/ig)) {
        os = '<span class="os_ubuntu"><i class="fa fa-desktop"></i> Ubuntu'
    } else if (e.match(/linux/ig)) {
        os = '<span class="os_linux"><i class="fa fa-linux"></i> Linux'
    } else if (e.match(/mac/ig)) {
        os = '<span class="os_mac"><i class="fa fa-desktop"></i> Mac OS X'
    } else if (e.match(/unix/ig)) {
        os = '<span class="os_unix"><i class="fa fa-desktop"></i> Unix'
    } else if (e.match(/symbian/ig)) {
        os = '<span class="os_nokia"><i class="fa fa-mobile"></i> Nokia SymbianOS'
    } else {
        os = '<span class="os_other"><i class="fa fa-desktop"></i> 其它操作系统'
    }
    return os + "</span>";
}
//显UA结束
```

4.上传embed.js

我的做法上传到GitHub，其它类似七牛或者云主机的方法都可以
http://wsgzao.github.io/embed.js

5.修改多说调用地址

>其它平台以此类推，我自己的做法ds.src = '//wsgzao.github.io/embed.js';

``` js
<script type="text/javascript">
  var duoshuoQuery = {short_name:"<%= theme.duoshuo_shortname %>"};
  (function() {
    var ds = document.createElement('script');
    ds.type = 'text/javascript';ds.async = true;
    ds.src = '//wsgzao.github.io/embed.js';
    ds.charset = 'UTF-8';
    (document.getElementsByTagName('head')[0]
    || document.getElementsByTagName('body')[0]).appendChild(ds);
  })();
</script>
```

6.增加Font Awesome

官方下载压缩包 - http://fontawesome.io/
解压其中的fonts和css，根据你的Blog类型上传至指定目录引入CSS链接即可生效

7.多说后台自定义CSS

>请参考上文方法加入多说自定义CSS

``` css
/*UA Start*/
span.ua {
    margin: 0 1px!important;
    color: #FFFFFF!important;
    /*text-transform: Capitalize!important;
    float: right!important;
    line-height: 18px!important;*/;
}

.ua_other.os_other {
    background-color: #ccc!important;
    color: #fff;
    border: 1px solid #BBB!important;
    border-radius: 4px;
}

.ua_ie {
    background-color: #428bca!important;
    border-color: #357ebd!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_firefox {
    background-color: #f0ad4e!important;
    border-color: #eea236!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_maxthon {
    background-color: #7373B9!important;
    border-color: #7373B9!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_ucweb {
    background-color: #FF740F!important;
    border-color: #d43f3a!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_sogou {
    background-color: #78ACE9!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_2345explorer {
    background-color: #2478B8!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_2345chrome {
    background-color: #F9D024!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_mi {
    background-color: #FF4A00!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_lbbrowser {
    background-color: #FC9D2E!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_chrome {
    background-color: #EE6252!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_qq {
    background-color: #3D88A8!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_apple {
    background-color: #E95620!important;
    border-color: #4cae4c!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.ua_opera {
    background-color: #d9534f!important;
    border-color: #d43f3a!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_vista,.os_2000,.os_windows,.os_xp,.os_7,.os_8,.os_8_1 {
    background-color: #39b3d7!important;
    border-color: #46b8da!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_android {
    background-color: #98C13D!important;
    border-color: #01B171!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_ubuntu {
    background-color: #DD4814!important;
    border-color: #01B171!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_linux {
    background-color: #3A3A3A!important;
    border-color: #1F1F1F!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_mac {
    background-color: #666666!important;
    border-color: #1F1F1F!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_unix {
    background-color: #006600!important;
    border-color: #1F1F1F!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.os_nokia {
    background-color: #014485!important;
    border-color: #1F1F1F!important;
    border-radius: 4px;
    padding: 0 5px!important;
}

.sskadmin {
    background-color: #00a67c!important;
    border-color: #01B171!important;
    border-radius: 4px;
    padding: 0 5px!important;
}
/*UA End*/
```

## 其它开源方案

>欢迎大家积极反馈，提出自己的想法^_^

Make DUOSHUO Show UA - http://git.oschina.net/huhuhuhu/Make-DUOSHUO-Show-UA/tree/master

ua-parser-js - https://github.com/faisalman/ua-parser-js

duoshuo-mod - https://github.com/wsgzao/duoshuo-mod

### 前端识别

>大家可以猛击测试各种UA

Useragent.js - http://zsxsoft.github.io/useragent.js/withimage.html

UAParser.js - http://faisalman.github.io/ua-parser-js/