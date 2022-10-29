hostname = api.weibo.cn, mapi.weibo.com, *.uve.weibo.com, mp.weixin.qq.com, api.bilibili.com, app.bilibili.com, www.zhihu.com, api.zhihu.com, link.zhihu.com, aweme*.snssdk.com, *.kuwo.cn, *.xiaoxiao*.com, *.amemv.com, p.du.163.com, getuserinfo.321mh.com, getuserinfo-globalapi.zymk.cn, ios.fuliapps.com, vsco.co, api.vnision.com, *.my10api.com, apple.fuliapps.com, newdrugs.dxy.cn, app101.avictown.cc, api.hlo.xyz, api.ijo.xyz, www.luqijianggushi.com, account.wps.cn, u.kanghuayun.com, api1.dobenge.cn, api.mvmtv.com, mitaoapp.yeduapp.com, origin-prod-phoenix.jibjab.com, www.3ivf.com, pay.guoing.com, api.bjxkhc.com, viva.v21xy.com, biz.caiyunapp.com, ap*.intsig.net, mp.bybutter.com, api.vuevideo.net, api.picsart.c*, api.meiease.c*, ios.xiangjiaoapps.com, apple.xiangjiaoapps.com, *.xiangxiangapps.com, trade-acs.m.taobao.com, api.m.jd.com, ios.prod.ftl.netflix.com


# 去微博应用内广告 (By yichahucha)
^https?://(sdk|wb)app.uve.weibo.com(/interface/sdk/sdkad.php|/wbapplua/wbpullad.lua) url script-response-body https://raw.githubusercontent.com/yichahucha/surge/master/wb_launch.js
^https?://m?api.weibo.c(n|om)/2/(statuses/(unread|extend|positives/get|(friends|video)(/|_)(mix)?timeline)|stories/(video_stream|home_list)|(groups|fangle)/timeline|profile/statuses|comments/build_comments|photo/recommend_list|service/picfeed|searchall|cardlist|page|!/photos/pic_recommend_status|video/tiny_stream_video_list) url script-response-body https://raw.githubusercontent.com/yichahucha/surge/master/wb_ad.js

# 去微信公众号广告 (By Choler)
^https?:\/\/mp\.weixin\.qq\.com\/mp\/getappmsgad url script-response-body https://raw.githubusercontent.com/NobyDa/Script/master/QuantumultX/File/Wechat.js

# 酷我音乐SVIP (By yxiaocai)
^https?:\/\/vip1\.kuwo\.cn\/(vip\/v2\/user\/vip|vip\/spi/mservice) url script-response-body https://raw.githubusercontent.com/NobyDa/Script/master/Surge/JS/Kuwo.js
^https?:\/\/musicpay\.kuwo\.cn\/music\.pay\?uid\=\d+ url 302 http://musicpay.kuwo.cn/music.pay?uid=1

# 爱美剧Vip (by huihui）(官网：app.meiju2018.com)
^https?:\/\/api.bjxkhc.com\/index\.php\/app\/ios\/(vod\/show|(user|vod|topic|type)\/index) url script-response-body https://raw.githubusercontent.com/NobyDa/Script/master/QuantumultX/File/aimeiju.js
# 广告
^https?://api.bjxkhc.com/index.php/app/ios/ads/index url reject-dict
^https?://api.bjxkhc.com/index.php/app/ios/ver/index_ios$ url reject
^https?://api.bjxkhc.com/index.php/app/ios/pay/ok$ url reject-dict

# 网易蜗牛读书VIP (By yxiaocai and JO2EY)
^https?://p\.du\.163\.com/readtime/info.json url reject
^https?:\/\/p\.du\.163\.com\/gain\/readtime\/info\.json url script-response-body https://raw.githubusercontent.com/NobyDa/Script/master/QuantumultX/File/wnyd.js
