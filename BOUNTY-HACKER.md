###### Easy makinelerden olan Bounty Hacker çözümüne klasik port scan ile başlayalım :

![1](https://user-images.githubusercontent.com/97543719/225923763-e6235243-525a-4e4e-be64-88d34c8630e3.PNG)

###### Detaylı bir tarama yaptı, devamı da şu şekilde :

![2](https://user-images.githubusercontent.com/97543719/225924129-beb6be27-53b6-4aab-a280-0ad7d1142f21.PNG)

###### Burada dikkatinizi çektiyse ssh açık ve ftp Anonymous ile giriş yapmama izin veriyor. Bu ikisi üzerinden ilerleyelim ve nmap -sS -sV -sC -Pn -O "ip" ile de detaylı bir tarama sonucuna ulaşabilirsiniz aklınızda bulunsun. ssh ve ftp bilgilerini bir köşeye not ettikten sonra, bir başka klasiğimiz olan siteyi gezinme olayını gerçekleştirelim :

![3](https://user-images.githubusercontent.com/97543719/225925415-a4b4ff18-d362-4f1f-94a3-5c89b8cb9cf1.PNG)

###### Burada tatmin edici bir şey bulamadık, sayfanın kaynak koduna da bir bakalım :

![4](https://user-images.githubusercontent.com/97543719/225925735-e8c3a59f-a691-4e3d-9575-3688782876ab.PNG)

###### Kaynak kodunda da işimize yarayacak bir koz göremedik. Görünmeyen kısımları görmek istiyoruz. Geleneksel GoBuster taramamızı gerçekleştirelim gobuster dir -u http://ip/ -w /usr/share/dirb/wordlists/common.txt -x php,html,txt :

![5](https://user-images.githubusercontent.com/97543719/225926433-67d04d61-fcfe-4ac7-a307-07369c99d019.PNG)

###### Taramamızı yaptık lakin buradan bize ekmek çıkacağını sanmıyorum. Muhtemelen /images/ sitede ilk çıkan resimle alakalı o yüzden zaman kaybetmeye gerek yok. Yine de emin olmak isterseniz ip adresinin yanına /images/ ekleyip siteyi tekrar görüntüleyebilirsiniz. Devam edelim :

![6](https://user-images.githubusercontent.com/97543719/225926990-28d29151-2d35-4c25-ba3d-e291dadb7400.PNG)

###### En başlarda bir yere not edelim dediğim ftp yi kullanalım. ftp "ip" komutunu uygulayalım, Anonymous ile girişe izin verdiğinden onu yazdığımız zaman ftp ile işlem yapar hale geleceğiz :

![7](https://user-images.githubusercontent.com/97543719/225927450-df0ef326-d973-4e94-b031-696dbd6973b5.PNG)

###### Arkadaşlar bir de burada bence ne olur ne olmaz ftp ye girince passive komutunu yazın ki passive mode kapansın yoksa işlemlerinizi gerçekleştiremezsiniz. Bu dediğim sıkıntı herkeste olmaz lakin geneli bu problemle karşılaşır ve ftp iznim yok galiba diye düşünüp işlemine son verir aklınızda bulunsun. 

###### ls dedikten sonra locks.txt ve task.txt leri gördüm. Bunları kendime alayım ki içinde neler varmış kurcalayabileyim. get locks.txt ve get task.txt işlemlerini uygulayıp ftp den çıkıyorum artık. 



