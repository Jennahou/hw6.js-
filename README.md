# hw6.js-
-非同步：
同時可以做很多件事情，不需要等到前一件事情做完才做下一件事情。

-同步：
一次只能做一件事情，如果安排了很多事情要給他做，他就會讓這些事情去排隊，再一件一件做，逐行執行。這就是所謂的同步，一次只做一件事情。
當跑一段程式碼，瀏覽器會將執行結果盡快的回傳。
因為 Javascript 是跑在一條單執行緒。主執行緒在同一時間只能做一件事情，直到目前操作完成為止其他的操作都會暫停。

Promise then
能有效解決callback hell
提供resolve(),reject()函數告知超長任務的進度

then(稱回調函數)
then會在超長與四執行完後被執行，裡面會寫處理超長任務返回數據的代碼
假如被reject程序就需要被catch捕捉這些錯誤，避免程序崩潰。

範例：
```css
let sentToAirport = false;

let p = new Promise(function(resolve,reject){
    if(sentToAirport){
resolve("from resolve():send to airport");
    }
    else{
        reject("from reject():order cancelled");
    }
}


);

p.then(function(message){console.log(`${message}-promise resolved`)})
.catch(function(message){console.log(`${message}-promise rejected`)});
```

