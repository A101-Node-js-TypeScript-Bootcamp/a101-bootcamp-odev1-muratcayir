<div align="center">

##  <code >Node.JS Server Oluşturma İşlemi </code>

</div>

<p>
 Server kurma işlemine gerekli nodejs paketlerinin kurulumunun  yapıldığını varsayarak başlıyorum. İlk olarak projemize ait bir klasör oluşturalım.Ben nodejsServer  adında bir klasör oluşturuyorum. Daha sonra klasörün içerisinde javascript dosyası oluşturuyoruz. Örneğin ben index.js adında bir dosya oluşturdum.Kodlarımızı oluşturduğumuz bu dosya içerisine yazacağız.Daha sonra projemizi nodejs projesine çevirebilmek adına terminalden 

 ```
 npm init
 ```

komutunu çalıştırarak yolumuza devam ediyoruz ve bizden istenilen bilgileri dolduruyoruz.Bu işlemler yapılırken oluşturduğumuz klasörün içerisinde olduğunuzdan emin olunuz.Şimdi ise server oluşturmak için gerekli olan paketi indirelim. Ben ExpressJS’i kullanacağım. ExpressJS’e alternatif olarak http modülü de kullanılabilir. ExpressJS’i  indirmek için terminalden 

  ```
 npm install express
 ```
yazıp indirelim.NodeJS’de projeye modül dahil etmek için require fonksiyonunu kullanılıyor. Bu yüzden ExpressJS modülünü dahil etmek için de

 ```
const express = require('express');
 ```
kod satırını yazalım.ExpressJS modülünü kullanabilmek için ise class yapısından kurtarmamız gerek.Bunun için tek gereken ise modül içerisinde bulunan class’tan yeni bir nesne türetmek.Aşağıda ki kod satırı işimizi görecektir.
  ```
const app = express()
 
 ```
 kod satırını yazalım.Şimdi ise gelen istekleri karşılayabilmek adına router (yönlendirici) oluşturmak gerek.Bunun için de

```
app.get('/', (req, res) => {
    res.send('Hello World !');
    res.end();
});
 ```
yazıyoruz. Burda "/" işareti sunucumuzun ana sayfasını temsil ederken bu da localhost:3000 adresine karşılık gelir.req() değişkeni sunucuya gelen istekleri ve res() değişkeni ise sunucudan geri dönen cevaplara karşılık geliyor. res.send() ifadesi sunucudan gelen cevabı derlememizi sağlar.Şimdi de sıra geldi sunucumuzu aktifleştirmeye.Sunucumuzu dinlemek yani aktifleştirmek için  aşağıda ki kod satırlarını yazalım.

```
app.listen(3000, () => {
    console.log('Sunucu 3000 portunda çalışıyor');
});
});
 ```
listen() fonksiyonu yardımı ile portu (3000) dinlemeye başladık.console.log() yazmak tamamen opsiyonel burda ki amaç sunucunun çalışma durumunu kontrol etmek. Her şey hazır olduğuna göre terminalden aşağıda ki kod satırını girerek sunucuyu ayağa kaldırabiliriz.

  ```
node index.js
 ```
Bundan sonra localhost:3000  adresine giderek  Hello World ! yazısını görebilirsiniz. Tebrikler !!! İlk defa server ayağa kaldırma işlemini başarılı bir şekilde tamamladınız. Aşağıya tüm kodları bırakıyorum

  ```
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    res.send('Hello World !');
    res.end();
});

app.listen(3000, () => {
console.log('ISunucu 3000 portunda çalışıyor');
});
 ```
