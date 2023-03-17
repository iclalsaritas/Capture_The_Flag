##### Ultra erkkeğimizin kalkıştığı ultra tehlikeli Bounty Hacker çözümüne klasik port scan ile başlayalım :

![1](https://user-images.githubusercontent.com/97543719/225923763-e6235243-525a-4e4e-be64-88d34c8630e3.PNG)

##### Detaylı bir tarama yaptı, devamı da şu şekilde :

![2](https://user-images.githubusercontent.com/97543719/225924129-beb6be27-53b6-4aab-a280-0ad7d1142f21.PNG)

##### Burada dikkatinizi çektiyse ssh açık ve ftp Anonymous ile giriş yapmama izin veriyor. Bu ikisi üzerinden ilerleyelim ve nmap -sS -sV -sC -Pn -O "ip" ile de detaylı bir tarama sonucuna ulaşabilirsiniz aklınızda bulunsun. ssh ve ftp bilgilerini bir köşeye not ettikten sonra, bir başka klasiğimiz olan siteyi gezinme olayını gerçekleştirelim :

![3](https://user-images.githubusercontent.com/97543719/225925415-a4b4ff18-d362-4f1f-94a3-5c89b8cb9cf1.PNG)

##### Burada tatmin edici bir şey bulamadık, sayfanın kaynak koduna da bir bakalım :

![4](https://user-images.githubusercontent.com/97543719/225925735-e8c3a59f-a691-4e3d-9575-3688782876ab.PNG)

##### Kaynak kodunda da işimize yarayacak bir koz göremedik. Görünmeyen kısımları görmek istiyoruz. Geleneksel GoBuster taramamızı gerçekleştirelim gobuster dir -u http://ip/ -w /usr/share/dirb/wordlists/common.txt -x php,html,txt :

![5](https://user-images.githubusercontent.com/97543719/225926433-67d04d61-fcfe-4ac7-a307-07369c99d019.PNG)

##### Taramamızı yaptık lakin buradan bize ekmek çıkacağını sanmıyorum. Muhtemelen /images/ sitede ilk çıkan resimle alakalı o yüzden zaman kaybetmeye gerek yok. Yine de emin olmak isterseniz ip adresinin yanına /images/ ekleyip siteyi tekrar görüntüleyebilirsiniz. Devam edelim :

![6](https://user-images.githubusercontent.com/97543719/225926990-28d29151-2d35-4c25-ba3d-e291dadb7400.PNG)

##### En başlarda bir yere not edelim dediğim ftp yi kullanalım. ftp "ip" komutunu uygulayalım, Anonymous ile girişe izin verdiğinden onu yazdığımız zaman ftp ile işlem yapar hale geleceğiz :

![7](https://user-images.githubusercontent.com/97543719/225927450-df0ef326-d973-4e94-b031-696dbd6973b5.PNG)

##### Arkadaşlar bir de burada bence ne olur ne olmaz ftp ye girince passive komutunu yazın ki passive mode kapansın yoksa işlemlerinizi gerçekleştiremezsiniz. Bu dediğim sıkıntı herkeste olmaz lakin geneli bu problemle karşılaşır ve ftp iznim yok galiba diye düşünüp işlemine son verir aklınızda bulunsun. 

##### ls dedikten sonra locks.txt ve task.txt leri gördüm. Bunları kendime alayım ki içinde neler varmış kurcalayabileyim. get locks.txt ve get task.txt işlemlerini uygulayıp ftp den çıkıyorum artık. 

##### Terminalimizde task.txt ve locks.txt yi kurcalayalım bakalım. cat task.txt , cat locks.txt :

![8](https://user-images.githubusercontent.com/97543719/225929360-d0fbbd12-d4f5-4d83-81ce-392cbb4822cb.PNG)

##### Lin tarafından yazılmış görevler ve muhtemelen parolaların yer aldığı bir liste görüyoruz. Bunlar bizim çoook işimize yarayacak. Acaba listedeki hangi parola Lin'e ait? Onu bulursak Lin kullanıcısıyla elimizi kolumuzu sallayarak gireriz. Hydra komutuna hazır olun :

![9](https://user-images.githubusercontent.com/97543719/225929993-cec30a22-8463-49b4-991c-c85928578703.PNG)

##### Komutumuz bize sonucu güzel bir şekilde sundu. Artık oturum açmak için daha fazla beklemeye gerek var mı :

![10](https://user-images.githubusercontent.com/97543719/225930449-d1233e19-550d-4ef1-a7e0-ee50f963feed.PNG)

##### Flag e adım adım yaklaşıyoruz. ls diyelim :

![11](https://user-images.githubusercontent.com/97543719/225930634-9bd378bf-54d3-4ffa-8d9a-b502db48ec66.PNG)

##### THM nin bizden istemiş olduğu user.txt yi okumayı başardık. root.txt yi de bulmamızı istiyordu son olarak. Bunun için root olmamız gerekiyor ve biz henüz Lin olarak varız :

![12](https://user-images.githubusercontent.com/97543719/225931037-59b99b54-900d-41f7-aba5-7d18f4b4d066.PNG)

##### sudo -l komutunu yazıp Lin'in parolasını doğru girdiğim halde bir engelle karşılaşıyorum. O da tar engeli. Bu engeli aşabilmek için tarayıcımda sudo tar privilege escalation araştırması yapıyorum ve tar engelinden beni atlatacak olan komutu buluyorum :

![13](https://user-images.githubusercontent.com/97543719/225931510-8a9bf9c0-9067-488b-bef9-b1d4e7baa6e1.PNG)

##### Komutu uyguluyorum ve parola dahi girmeden beni root olarak atadığına şahit oluyorum. whoami diye test ettiğimde de root olduğumu görüyorum :

![14](https://user-images.githubusercontent.com/97543719/225931853-a074f4ad-7917-4b62-bc83-e64b90b2d2c6.PNG)

##### cd /root kısmına gidip ls dediğimde root.txt ye ulaşmış oldum. Son olarak da cat root.txt diyoruz ve flag karşımızda. Dayak yemekten kurtardığımız erkkeğimize tebesüm ediyor ve bir sonraki CTF'e geçiş yapıyoruz. Umarım faydalı olmuştur!







