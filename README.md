# 關於中文輸入法
這篇文就是來分享我實際安裝中文輸入法的過程中遇到的問題，以及推薦好用的中文輸入法（小麥mcbopomofo），希望有幫到大家。

關鍵字：小麥, rime, fcitx5, linux, 中文輸入法

## 簡單的架構介紹和差異
  我剛開始用linux遇到的第一個問題（想必也是多數人會遇到的問題）就是中文輸入法，因為網路上關於linux的教學多半是英文（尤其是新的技術或distribution), 教學影片上的按鈕都是英文的，要是英文不好的人還真的不容易照著影片操作學習（汗顏）， 也因此許多人會先載英文版的linux來一步一步學著架設， 而但當真的要開始用的時候卻發現沒有中文輸入法！！！ 安裝中文輸入法對於新手linux使用者算的上是小魔王一般的存在（困難重重），導致學習linux的那份上進心馬上被狠狠的打擊， 從此又回歸windows或MacOS的懷抱， 嗚呼哀哉QQ。
  好不容易終於下載好小麥輸入法了，趁著記憶猶新，趕快寫下來讓大家（以及以後的我）可以參考。

  首先要介紹fcitx5，他是一種輸入法框架，其底下可以有多個輸入法引擎，每種引擎又有各自對應的輸入法模組。
```
使用者層
  ↓
輸入法框架（IMF, Input Method Framework）e.g. fcitx5 fcitx
  ↓
輸入法引擎（IME, Input Method Engine）   e.g. rime Gramambular2 libchewing
  ↓
輸入方案 / 字詞庫（Schema, Dictionary）   e.g. 台灣注音 小麥Mcbopomofo 新酷音
```
我使用fcitx5框架（對中文友善），要注意不要搞錯成fcitx，兩個是新舊版的差別。
.
"小麥輸入法"、"rime", "新酷音"是三個比較常聽說的中文輸入法，在下載之前可能要先聊解三個的差異，以避免混淆。  
  小麥輸入法Mcbopomofo, 是基於Gramambular2"引擎"下的"輸入法程式"。  
  rime, 是一種"輸入法引擎", 其底下可以透過新增yaml 設定檔去作客自化的編排，如auto選字的詞庫等等。  
  新酷音, 由台灣中研院開發的注音輸入法，使用libchewing作為核心"引擎"。  
  
  我三種都用過，如果想要高客製化且熟悉yaml格式可以選rime，支持中研院可以玩玩看新注音，從windows轉來linux要馬上使用的話我建議用小麥Mcbopomofo。  

  為什麼我推薦用小麥呢？假如我要打『的』這個字，如果用windows的話需要按（ㄉㄜ˙）三個符號，windows的習慣是先打注音，然後打聲調時便會選字，小麥會自動判斷ㄉㄜ的位置然後接收˙便可以打出『的』；rime，則是在打完所有的注音和聲調後，要再按enter才會選字，如果打字很快的話會導致像是『ㄜㄉ˙enter』然後輸出『餓得』這樣的情況發生。很蠢。而且要選字的時候，小麥會用1234來選字，rime的話要用ABCD，很蠢。啊新注音呢？ 他是另外一種蠢法，這邊就不提了。  
  
  簡單來說，從windows來linux的使用者，我推薦先使用小麥Mcbopomofu。  
  btw，如果你問chatGPT什麼是小麥輸入法，他會跟你說小麥輸入法是rime底下的一個yaml設定檔。很蠢。可能真的有人也寫過叫做小麥（xiaomai ）的yaml檔吧，記得不要被搞混了。  

接下來，來跟大家介紹下載小麥Mcbopomofo的指令。  

## 小麥Mcbopomofo輸入法安裝

[小麥linux](https://mcbopomofo.openvanilla.org/)

1.安裝 fcitx5, CMake, 以及以下開發用模組
　```sudo apt install \
    pkg-config fcitx5 libfcitx5core-dev libfcitx5config-dev libfcitx5utils-dev fcitx5-modules-dev \
    cmake extra-cmake-modules gettext libfmt-dev libicu-dev libjson-c-dev```














