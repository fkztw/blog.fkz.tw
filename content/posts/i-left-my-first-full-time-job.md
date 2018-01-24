Title: 我的新鮮人離職紀錄  
Slug: i-left-my-first-full-time-job  
Date: 2017-12-26 21:54:30  
Authors: m157q  
Category: Life  
Tags: Job, 2018 iT 邦幫忙鐵人賽  
Summary: 離開了人生第 1 份全職工作，2016/01/21 ~ 2017/11/30 將近兩年的時間，想藉這篇文章紀錄一下，一方面也是給自己日後檢視用。  
Modified: 2018-01-23 13:48:30  
  
  
## 前言  
  
這個標題是為了與另一篇將近兩年前寫的文章：[我的新鮮人面試紀錄](/posts/2016/02/12/first-job-interviews/) 相互呼應，  
這篇文章因為把面試過程紀錄的很詳細，  
導致被 Google 搜尋到的機率很高，  
意外成了我部落格上瀏覽量最高的文章，  
是當初始料未及的，  
原本只是想紀錄給自己看。  
  
至於為什麼這篇文章要與其相呼應的原因也很明顯了，  
嗯，因為我離職了。  
算是這輩子第一份離開的全職工作，  
想說既然當初找工作的時候紀錄得這麼詳細，  
那就不要虎頭蛇尾。  
所以這篇文章會紀錄我在 2016/01/21~2017/11/30 這段時間，  
於塔圖科技擔任 Web back-end engineer 發生的事情。  
  
其實 2017/09/30 就辦離職了，  
但 2017/10/01~2017/11/30 轉為約聘，  
把停了一年多的架構搬遷的專案收個尾，  
也算是為自己負責吧。  
而頭銜雖然是掛 Web Back-end Engineer，  
實際上算是 DevOps + Architect + 半個 Support engineer。  
  
主要當然還是紀錄下來給我自己以後有空的時候回頭檢視用的，  
但如果有幫助到閱讀這篇文章的你的話，  
我也會感到滿開心的就是，  
如果真的有幫助的話也請你不吝留言讓我知道。  
  
---  
  
## 紀錄  
  
就先從我做了哪些事開始回想好了，一方面也是為了最近要開始改履歷用。  
這裡當然會比較流水帳一點，會再從這找比較重點的事蹟更新到履歷上。  
以下依照到職時間以每 6 個月來切分：  
  
---  
  
###  剛到職到六個月  
  
因為剛到職的狀況比較多變，所以這裡我再區分成每個月來紀錄：  
  
+ 剛到職  
    + 只有我一個 Web Back-end Engineer，另外是寫 JavaScript 的 Support Engineer，也剛進公司沒多久，之前的開發團隊都到另外一間公司去了。  
    + 雖然在 Slack 上有位前員工可以問，但也只有一開始一兩個月有問而已，其他都靠自己摸索。  
+ 到職一個月  
    + 把所有前人留下來的文件讀完並進到還有在用的伺服器自行尋找相關設定。  
    + 因為前人留下來的文件不夠完整，這部份真的很像在打站，拿到一個可以登入的 shell 以後就什麼都要自己找...  
+ 到職兩個月  
    + 把伺服器搞炸。  
    + 不小心把 Google Cloud Platform 上的 Compute Engine Service Account 給砍了，到處求助但都無法解決，最後只好開一個新的 GCP Project。  
    + 因為之前的人把服務都跑在同一台 Google Cloud Compute Engine 上，所以一堆服務都掛掉，為此加班熬夜幾天搞定自己捅出來的簍子。  
    + 第一次參加 GCPUG.tw 就非常狼狽得來問這個問題，這裡有尋求協助的紀錄：<https://www.facebook.com/groups/GCPUG.TW/permalink/1695449067380624/>  
    + 剛好公司方向有改變，很多之前的服務用不到，適合開個新的 GCP project 把還有要用的東西移過去。  
+ 到職三個月  
    + 把雲端平台的使用費省下 70% 左右。  
    + 大概是從每個月 2x 萬新台幣降到 6 萬左右，大概是降了 20  
萬新台幣左右，雖然嚴格說起來真的沒有很多就是。  
    + 原因是因為之前團隊的人走了之後，沒把 GCP Cloud Bigtable（可以想成是跑在 GCP 上的 Spark）關掉，也沒在跑啥運算，就這樣每個月白白燒掉 20 萬新台幣。  
    + 當然也還把一些確定沒用到的服務都一併暫停了。  
+ 到職四個月  
    + 已經把有在跑的服務大致上都搞懂了，可以修改並加上新功能，只剩下一些非常久遠的 legacy package 沒有去動它。  
    + 開始撰寫新文件，因為對服務都大致瞭解了，所以也從舊的文件中篩選出還有用的部份，將其獨立出來，並儘量完整補充。  
    + 因為之前的團隊把服務都集中在某台 Google Compute Engine 上，所以開始跟約聘的 Web Back-end Engineer 同事討論計劃把服務拆分出來，以避免之後「一個掛、全部掛」的狀況。  
    + 剛好同事有用過 Docker 跟 Kubernetes，也是我當時想學的新技術之一，於是就開始計劃把現有的服務都拆分成 microservices。  
+ 到職五個月  
    + 年資最久的工程師離職了（其實也只比我早進公司 3 個月），所以要花比較多時間帶兩位跟我同期進來，但比較沒經驗的同事。（其實在這之前多少就有花時間帶了，因為座位在旁邊，年紀也相仿，所以比較好溝通。）  
    + 有新的全職 Web Back-end Engineer 加入，雖然是有經驗的，但也得額外花點時間帶他熟悉。  
    + 開始針對現有服務的效能做改善。  
  
---  
  
### 到職六個月到一年  
  
+ 和後來加入的 Web Back-end Engineer 磨合，年紀差了一輪以上，溝通上面有很嚴重的問題，許多觀念差太多，這是第一個腦海浮現讓我想離職的時候。  
    + 另外一位年紀與我相仿的約聘同事也在和他的合作上遇到滿大的問題，剛好當時他們有個案子要合作，常常溝通到後來都要請我居中協調。  
    + 常常在溝通的時候不發表意見，都說「好」「沒問題」，但之後實作出來的程式碼卻不是照討論的結果，而是他原本想做的事，浪費的討論的時間。  
    + 程式碼會動就好，常常直接 copy-paste 程式碼，因為很快就能交差了事，老闆都會覺得他的進度很快很棒，甚至我包好的 function 也被直接複製出去修改，然後原本的就被棄置。  
    + 每天都要跑來問我們昨天的進度，但明明大家都會寫在 Trello 上，其實每個人就只是把 Trello 打開，講昨天紀錄的東西，所以是浪費時間，溝通很多次了也沒用，後來就不了了之。  
    + 所以後來在分配專案的時候，我都會儘量與其避開，因為實在是太累，是心理上的那種累。  
+ 開始把服務拆分並轉移到新的 GCP Project，這中間比較有挑戰性的事情是和另外兩位同事們討論如何做到 zero downtime 的 Database migration，透過架構與程式碼的修改以及撰寫 script 進行資料搬移，大家各負責不同的部份，後來也成功做到了。  
+ 解決現有服務要提供給中國客戶使用的問題  
    + 其實這原本不是我主要負責的事，老闆是先指派給年紀比我大一輪的那位同事做，因為他剛好做完了上一件老闆交代的事。我一開始有給些方向與想法，但該同事就沒再來找我討論，結果一個禮拜過去了，上線前測試，根本不會動。跟客戶講說下禮拜就可以好的東西，老闆只好去請客戶寬限一週，然後就落到了我頭上，開啟了一個禮拜的爆炸加班之旅。  
    + 中國網路環境特殊，要使用 GCP 的服務直接提供根本不可能，因為會被擋光光，但老闆談這筆生意的時候又很急著上線，所以根本來不及把所有的服務都複製到中國的雲端平台上使用，更別說可能還有域名得立案的問題。  
    + 後來當然是沒有遇域名立案，因為根本沒時間，而是老闆先跟同行借了中國的伺服器，但要佈署服務很麻煩，畢竟不是自己的伺服器，再加上狀況其實不太好，所以最後還是用了中國的雲端服務。  
    + 加了三天晚上的班，吃老闆請的披薩等等速食晚餐，總算是弄出了個能用的東西。但效果不太好，即便是在中國牆內的網路，還是被擋的很慘，不然就是 latency 太高，而且還被同行合作的程式碼雷到。XD  
    + 之後大概又來來回回折騰了一個多月，仍舊無法完全克服 Google Tag Manager 部份被擋的狀況。折衷弄了一個全由自己獨立開發的 Django server，撰寫爬蟲定時去抓取資訊，並提供 API，做到確保能載入 `gtm.js` 的時候才載入，不能載入的時候就不載入。當然也有把 request 資訊紀錄到資料庫裏面，方便之後拉資料出來觀察狀況。詳細紀錄在這篇文章：[中國網路相關筆記 | Just for noting](https://blog.m157q.tw/posts/2018/01/11/dealing-with-china-network/)  
+ 2016 梅竹黑客松  
    + 回交大當評審，其他評審看起來都至少大我 5~10 歲以上，第一次當程式相關的評審，其實有點抖。  
    + 為此弄了一個 Django server，搭配 Django REST framework 和 Django REST framework Docs 提供 API 給參加者撈出 BigQuery 裡頭的資料。詳細紀錄在這篇文章：[關於 Django REST framework 的一些筆記 | Just for noting](https://blog.m157q.tw/posts/2018/01/07/django-rest-framework-note/)  
+ 開始開發 Facebook Messenger Bot  
    + 用 Google App Engine 搭配 `webapp2` 開發，因為 Facebook 官方沒有 SDK，所以啥都得自己接。  
    + 也踩到了不少雷，例如：  
        + Facebook 的開發文件很雷這應該就不用說了，有程式碼的話直接去看程式碼比較快，程式碼寫的比文件好。  
        + Generic Template 10 個 element 都放圖片的話，即便已經用了 cache 快速回應給 Facebook 的伺服器，訊息仍舊非常慢才在 client 端被 render 出來，主要都是卡在圖片。  
        + 沒有完善的測試環境，基本上大家都是開一個 production bot、一個 testing bot 分開維護。  
        + API 常常沒在管 backward compability，major version 都還在 1 的時候常常 API 行為突然就改了。  
  
---  
  
### 到職一年到一年半  
  
+ 繼續開發 Facebook Messenger Bot  
    + 2017 上半年時間幾乎都在弄 Facebook Messenger Bot，主要是功能需求其實有點違反 Facebook 的 policy，所以在實作上為了不要觸犯 policy，一直在花時間想要怎麼繞路。  
    + 主要是需求沒有確定下來，PM 是個初心者，所以浪費了不少時間在做重複的事，導致之後要儲存使用者行為及分析的流程延宕了很久。  
    + 為了更加瞭解 Facbeook Messenger Bot，2017 年 6 月參加了 [Facebook Developer Circle: Taipei - Meetup #2](https://fdctaipei.kktix.cc/events/fdc201706)，有篇筆記文：[Facebook Developer Circle: Taipei - Meetup #2 | Just for noting](https://blog.m157q.tw/posts/2017/06/22/facebook-developer-circle-taipei-meetup-2/)  
+ 支援同事  
    + 這反而是我這段時間做得比較有成就感的，實在是因為 Messenger Bot 的開發沒規劃好，讓我覺得有點厭煩了。  
    + 幫忙解決了一些數字落差的問題，有點像是網站方面的 debug，除了更加熟悉架構與細節以外，有時候也挺享受確定問題的發生的原因跟自己思考出來的結果是相同的那種成就感。  
    + 幫忙把原本在 Travis CI 上要跑一個半小時的測試（沒錯，一個半小時。），加上 multiprocessing，縮短到只要花 15 分鐘就跑完。  
    + 加上廣告商品自動下架機制，因為原本的下架機制很陽春，常常被客戶抱怨。  
  
---  
  
### 到職一年半到離職前  
  
+ 因為覺得公司走向改變，工作內容已經變成我不太喜歡的部份，經過多次思考後，在 2017 的 7 月底提離職。  
    + 談完之後調整了工作內容，回歸到架構和資料分析的部份。  
    + 並設定兩個月的觀察期，期間順便把工作相關的部份逐步交接給同事，如果不行的話就 2017 的 9 月底離職。  
+ 開始做 data cleaning 和接觸 Machine Learning  
    + 參加了幾場資料科學年會辦的活動，學到了不少東西：  
        + [台灣資料科學年會之系列活動：深入淺出深度學習 (Dive into Deep Learning) | Just for noting](https://blog.m157q.tw/posts/2017/08/12/dive-into-deep-learning-datasci-tw/)  
        + [台灣資料科學年會之系列活動：手把手的深度學習實務 | Just for noting](https://blog.m157q.tw/posts/2017/08/13/deep-learning-hands-on-step-by-step-datasci-tw/)  
    + 這期間真的是比較多時間在碰 Machine Learing 和 Deep Learning，但花在上面的時間沒有很多，因為還有其他事情得做，而且主要負責機器學習相關專案的開發者不是我，所以自己覺得只學了點皮毛。  
+ 儘量把文件補齊全  
    + 花最多時間的應該是用 draw.io 畫出了整個公司的伺服器架構圖。  
    + 其次則是撰寫新的員工訓練與入門文件。  
+ 最後還是在 2017 的 9 月底離職了，但後續以約聘的方式完成了一件案子，直到 2017 年 11 月底。  
    + 主要內容是 API 搬遷以及整理資料流。  
    + API 搬遷算是 2016 年中做到一半的東西，因為相關人員都已經離職，只剩我比較瞭解，自己也想做個了斷，所以就接了。  
        + 主要是去除舊的 API 以及增添新的資料庫欄位因應新的需求。  
    + 整理資料流則是儘量讓不同服務之間傳遞資料的方式有個統一的規則，在此之前是有點雜亂無章的，常常會搞混。  
  
---  
  
## 反省  
  
「人非聖賢，孰能無過？」其實在這段時間內自己覺得也犯了不少錯，在這邊紀錄下來，用來提醒以後的自己。  
  
+ 絕對要克制自己看到 legacy code 就想改的強迫症。  
    + 基本上沒有錯誤或者嚴重效能瓶頸的 legacy code 就別動它了。  
    + 剛進公司的時候逞一時之勇，改了一些 legacy code 導致行為改變，都是後來有人回報或是察看資料才發現。  
    + 如果真的要改的話，先確定自己瞭解整個服務在幹嘛，最好還要確定有夠完整的測試，避免修改後出錯卻不知道。  
+ 在面對年紀比自己大的同事時的溝通能力還不夠好  
    + 無法像和年紀相仿的同事那樣直接溝通  
    + 這部份目前真的沒啥其他想法，之後可能要多注意一下。  
+ 對於技術瞭解得不夠深入  
    + 很多時候都是網路上查到覺得不錯就用某個工具或方法，但用了以後發現有不少的問題或者中途才發現有更好的處理方法，但要改的話進度又會落後。  
    + 對於該如何用什麼樣的技術、什麼樣的架構、什麼樣的演算法、什麼樣的資料結構還是不夠確定，資工的基礎部份還是不夠熟，得多花時間加強。  
+ 對於專案進度的安排不夠準確  
    + 常常有進度落後的狀況出現，對於專案的估期還是不夠準確，其實某方面應該也代表自己的技術能力不夠純熟。  
    + 當然也會遇到需求變動而導致專案進度落後的部份，這部份可能之後要多熟悉 Agile 的流程，畢竟在這份工作並沒有使用到 Agile。  
+ 解釋東西的時候常常會太過發散  
    + 有時候為了要讓人比較好懂反而會講得太過詳細或太過多餘，甚至不自覺得離了題，這點是自己之後要注意的部份，講話要多講些重點。  
    + 還有一點要注意的是講解技術相關的東西時，必需要再多加確定聽的人的程度，這樣才能更有效且更精準的討論或解答，不會太過或不及。  
+ 仍舊沒養成寫測試的習慣  
    + 雖然知道寫測試很重要，但常常因為開發進度的關係來不及寫測試。  
    + 知道 TDD，但還是不太習慣，總覺得有機會應該找一個 side project，強迫自己試試 TDD，去體會其中明顯的差別。  
+ 英文口說沒太大進步  
    + 畢竟在台灣能用到的場合相對來說真的比較少，這部份還要自己再找時間精進。  
    + 基本上現在已經不太怕口說了，但重點是用字會趨於過度單調，常常重複使用同樣的字。  
+ 和人交談技巧還是不夠  
    + 算是我自己長久以來的問題吧，常常都是事後才想到當時其實應該還有很多東西可以聊，有助於建立人際網路。  
    + 出社會以後算是真的體驗到人際網路比我以前想像中的重要些。  
+ 聽完演講歸納問題並勇於發問的能力仍舊不足  
    + 之後應該要多訓練自己聽講時的歸納與分析能力，並和自己的一些想法結合，提出一些精闢的問題。  
    + 這個算是 2016 年底去 33C3 的時候有非常深刻的體會，會場不僅提問踴躍，每個人問的問題也都很棒，我覺得這是從小到大習慣了填鴨式教育最大的問題。  
+ 時間管理不夠好、自信不足、應該多嘗試面試邀約  
    + 在這將近兩年的時間內，從 LinkedIn 或 Email 至少收到 7 位獵頭詢問、與一間東南亞頗大間公司的 HR 當面吃飯聊天、和想在加拿大創業的高中同班同學聊過，不過都因為覺得自己還在工作中加上個性的關係沒有進一步去面試，現在覺得導致自己少了滿多學習的機會的。  
    + 之後在工作中如果有不錯的面試邀約應該就會去嘗試看看，不然老實說將近兩年的時間沒有面試，對於面試的東西實在有點生疏，現在要額外準備的心力讓我的拖延症更嚴重了。以後不如就把面試當健身，讓自己保持在習慣面試的狀態，也許這樣會比較好。  
    + 期間還有一件事是，2015 年底找工作的時候在 Livecoding.tv 這個平台（現在改名為 LiveEdu）上開了寫程式的實況，後來找到工作後因為租屋觸網路問題所以就沒繼續開了，結果後來發生了幾件事：  
    + 收到不少次該平台的工作人員寄訊息來說覺得我的實況不錯，不知道為什麼我沒繼續開了，想邀請我參加他們的 Premium member，可能每週固定時間開實況這樣。  
    + 也在該平台的私訊收到一些人表示剛學 Python，說看我之前的實況 VOD 學到不少，算是在這平台上還不錯的影片，問我什麼時候能繼續開。  
        + 當時我因為 2016 年下半年比較忙，再加上租屋處網路問題短時間內也無法解決，所以只回說目前因為網路問題無法解決所以不會開，之後有可能會再開，但不一定。  
    + 收到該平台中國區工作人員邀請我進行一段訪問，我也因為工作因素加上自信不足沒有回應，就這樣算是錯失了一個可以小小建立一點自己的能見度的機會。  
  
---  
  
## 心得  
  
在這將近兩年的工作時間，收穫其實也不少，就在這邊把一些心得感想寫下來。  
  
+ 最大的收穫應該是認識了一群感情很好的同事吧  
    + 週末晚上會約去唱歌、吃飯、喝酒，還有自己揪團的小旅行。  
+ 用中文和技術職或非技術職的同事溝通的能力算是有長進吧  
    + 獲得了「會講人話的工程師」的稱號  
    + 關於回答問題的部份，最近翻譯的這篇文章算是把我想講的話都講出來了：[《回答的智慧》 | Just for noting](https://blog.m157q.tw/posts/2017/12/21/how-to-answer-questions-in-a-helpful-way-zh-tw/)  
+ Docker 和 Kubernetes 算是這份工作學到比較多的吧  
    + 雖然自己覺得對於 Docker 和 Kubernetes 的實作還是不夠瞭解，如果要進行效能方面的改善的話應該還是會有問題就是。  
+ 獨立完成的兩個使用 Django 的專案  
    + 無論是程式碼、註解、說明文件，我自己都覺得還算滿意。  
    + 最不滿意的都是效能的部份，之後從事 Python 相關開發的話得提醒自己多注重要怎麼讓效能更好這一部份。  
+ 算是有點確定自己有興趣的方向了  
   + 對於網站後端架構以及自動化測試與佈署的部份，覺得能幫助同事和自己節省更多時間或看到因為架構改善讓開發變得比較容易，會滿有成就感的。  
  
---  
  
## 原因  
  
紀錄一下這次離職的一些原因，想說在之後有新工作的時後可以拿來檢視。  
  
+ 公司著重方向改變，和我想做的事情以及當初面試進來的工作內容不符合。  
    + 主要是我對於新的方向沒有很強烈的興趣。  
    + 雖然工作內容有調整，但剛進來的新人也無法成為即戰力，等於是我要做更多的事。  
+ 覺得自己的技術能力沒有什麼顯著的長進  
    + 自己覺得剛畢業後的工作應該要能夠讓自己的技術能力有顯著的成長，不然會嚴重影響之後的職涯發展  
    + 因為同事大部份都算是初學者，所以花比較多時間在帶人，基本上同事有問問題的話我都是儘量回答到好，畢竟從別人的問題也常常可以學到新東西或發現自己的盲點。  
    + 甚至連非工程師的同事提出的問題我也儘量回答，而且是儘我最大的能力用比喻的方式讓不懂技術名詞的同事也能理解其中的概念。  
    + 其實我還滿享受這種幫助同事的成就感，但肯定是會擠壓到我精進技術能力的時間。  
+ 薪資成長不如預期  
    + 覺得調薪幅度跟我做的事情不太成比例。  
    + 當然也可能跟我自己沒有積極爭取加薪有關，算是下一份工作會想要有所突破的部份吧。  
  
---  
  
## 結論  
  
其實在這將近兩年的工作時間內，我也有好幾次不斷問自己，「到底下一份工作要不要找個大公司試試？」每次問完自己以後，都還是偏向找比較小型的公司。  
  
最近再次問了自己這個問題，還是想要找小型的新創公司來待，可能跟我自己的個性有關吧，不是很在意 brand name。  
  
但我想之後還是會每隔一段時間問自己這個問題就是，我自己也知道大公司與小公司各有優缺點，唯一一個讓我覺得最有感的是，大公司比較有可能遇到好的 mentor 授予你一些經驗，不是說小公司遇不到，主要是小公司每個人得各司其職，工作範圍可能都不太重疊，所以比較沒有人有時間可以帶你。大公司則制度比較完善，人力資源也比較多，也大多會分配 mentor，當然能不能遇到好 mentor 也是要看運氣就是。  
  
這份工作會想離職有滿大一部份原因是「沒有人可以帶我」，所以都得靠自己摸索，也不是說自己就無法自學，只是就進步得比較緩慢，然後就覺得自己將近兩年來在能力上沒啥成長。也許跟之前的工作都有比我有經驗的人在帶有關，被有經驗的人指點或者被有經驗的人電，會讓我學得非常快，我想這是我自己的盲點，需要多花點時間去思考。  
  
下一份工作應該會先從國外的小型新創公司開始找吧，如果能夠 relocate 的話最好，但目前並沒有鎖定美國，畢竟美國現在因為 Trump 當總統，所以對技術移民不是那麼友善。  
  
但也有在考慮大公司就是，主要是可以面對規模比較大的服務以及可以接觸到比較深的技術，這是主要考量的點，很多問題在規模夠大的服務才會浮現，而且通常滿有挑戰性的。畢竟小公司大多數狀況會因為人少而且要急著有個賺錢的產品，所以會比較偏快速弄出個應用，且剛上線的服務使用人數不會太多。總之最近跟朋友聊完以後，對大公司可能有這樣的工作環境有點興趣，但就是要多花更多心力去準備大公司繁瑣的面試流程就是。  
  
我反而比較想去比較少人去的歐洲或是紐澳，總之可能就是邊緣人個性作祟吧，想去試一些比較少人試過的事。也因為這樣，其實雖然知道 referral 是比較容易找到工作的，但我其實沒有很喜歡從朋友變成同事，不知道為什麼下意識就會覺得多了一份利害關係而感到尷尬，還是覺得朋友之間可以分享彼此都不知道的事情比較有趣些。  
  
但我可以接受從同事變成朋友，我也不太確定為啥我會有這種想法，可能是因為我對朋友的要求並沒有很嚴格，就算我不太喜歡某位朋友的作風，我還是可以接受他比較 OK 的地方，但如果要成為同事的話，可能就會超越這條線讓我無法接受吧。再加上我的個性很難與人深交，所以寧願多認識一些不同的人之類的。  
  
總之，目前應該還是會傾向 Web Back-end 和 DevOps 的部份吧，我自己是覺得算有興趣，至於 Data Analysis 和 Machine Learning 的部份也要找時間好好碰一下，算是有興趣，但在這份工作比較沒有機會接觸到。  