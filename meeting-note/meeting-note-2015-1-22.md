**Plan**
=====================================================================================================

PoHao

(舊版投影片對照：https://drive.google.com/file/d/0BzEUu9bj9sLcZVdrSTZFM1FzaU0/view?usp=sharing)

+ p.2 - p.3
 - conceptNet的圖改成用中文且有sentiment concept的例子，最好選個例子是能貫穿整個投影片的，
 
+ p.4 
 - 右下的圖的assertion不用把encode那些format也都show出來

p.5 
 - 把它整個json直接貼出來不太好，應該把要強調的部分用high level的方式寫出來就好，而且選的例子有sentiment會比較好(就可以用這例子一直解說下去)
 - weight的值域要查一下，它的大小代表多強
 
p.6
 - 為什麼用surface text而不是relation的理由要解釋，在這裡是因為不同的surface text雖然是同一個relation但也有不同程度的propagate方式
 - 下去觀察這些relation和它們的surface text，自己先試著定一下我會用哪些surface text和surface text的pattern可能有哪些，如果要用surface text的話，這裡的表格可以它們列出來
 - 其實像厭惡這個surface text，它的sentiment是定義在relation上的，直接propagate到後面的concept是否恰當，例如女生喜歡吃蛋糕或是大象厭惡老鼠
 - 所以surface text在這裡能看出其實有兩種，一種是會傳送sentiment的，一種是它本身有sentiment的
 
p.7
 - 因為季恩的版本和我不一樣，要附的話自己要去統計一下
 
p.8
 - reference的format要統一，像是作者的姓名和publish的訊息，只有第二個是完整的，第三個居然還有To Appear in Knowledge-Based Systems, 2014. 

p.9 - p.10
 - "英文with value" 和 "中文with polarity"要列清楚
 - 要套蕙欣學姊前面的結果，也可直接寫seeds就是她的dictionary
 - weight of assertion不用一定要和propage出去的值綁在一起，例如他影響的是discount factor(削減得比較快，傳得比較短)，這裡直接乘在一起的理由是甚麼
 - （前面列了） 要真的下去看surface text和想出找法，讓人同意真的有能抓出的規律
 - 為什麼大家不用outlink: 表示越多relation的concept，反而影響力越小

p.11 - p.14
 - 如何用小雞來問問題多取得seed要再survey，或是自己設計平台，但是小雞的受眾較廣，所以比較prefer
 

Schedule
 - 1/24-1/26: Collect sentiment seeds（可先看或聯絡蕙欣學姊看是否有結果來當seeds）
 - 1/27-1/28: 基本的propagate結果和觀察（In-link和Out-link）
 - 1/29-2/02: Surface text和relation type對propagate的處理
 - 2/03-2/06: 處理In-link normalization的兩個問題：
  1. Number of seeds (透過小雞label或是設計human label的平台)
  2. Many Objective words weaken the result of propagation

 
1/23 with Janet:
 - 整理Evaluation的幾種方法的來源(來自哪個work)和用的時候的設計，目前已知幾個：
  1. （SentiWordNet和長蓉）: 由人去排序來和自己用polarity排序去比較（要想一下那我這邊是要如何讓人排，是兩個兩個排還是一起排，優缺點是？）
  2. （蕙欣）：看coverage還有把seed用5-fold來看準確率
  3. 用電影字幕sentence來evaluate的話如何設計（例如做個簡單的matching和negation，來真的去查查看），能真的看看真實語句能否分析得更好
