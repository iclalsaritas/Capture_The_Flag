##### Ultra erkkeğimizin kalkıştığı ultra tehlikeli Bounty Hacker çözümüne klasik port scan ile başlayalım :

![1](https://user-images.githubusercontent.com/97543719/227783705-cc889df3-0520-47a9-b5bf-b41936ab6c69.PNG)

##### Detaylı bir tarama yaptı, devamı da şu şekilde :

![2](https://user-images.githubusercontent.com/97543719/227783723-3ec0f212-4f24-4428-a07a-58fdd99fa616.PNG)

##### Burada dikkatinizi çektiyse ssh açık ve ftp Anonymous ile giriş yapmama izin veriyor. Bu ikisi üzerinden ilerleyelim ve nmap -sS -sV -sC -Pn -O "ip" ile de detaylı bir tarama sonucuna ulaşabilirsiniz aklınızda bulunsun. ssh ve ftp bilgilerini bir köşeye not ettikten sonra, bir başka klasiğimiz olan siteyi gezinme olayını gerçekleştirelim :

![3](https://user-images.githubusercontent.com/97543719/227783741-109bebc2-8237-4119-bba6-74f37ab1551a.PNG)

##### Burada tatmin edici bir şey bulamadık, sayfanın kaynak koduna da bir bakalım :

![4](https://user-images.githubusercontent.com/97543719/227783757-217e7b9c-6bb6-456e-a018-0dc2181c5fc1.PNG)

##### Kaynak kodunda da işimize yarayacak bir koz göremedik. Görünmeyen kısımları görmek istiyoruz. Geleneksel GoBuster taramamızı gerçekleştirelim gobuster dir -u http://ip/ -w /usr/share/dirb/wordlists/common.txt -x php,html,txt :

![2](https://user-images.githubusercontent.com/97543719/227784215-28dde651-3e33-4d44-aa8a-69ebee0ff2be.PNG)

##### Taramamızı yaptık lakin buradan bize ekmek çıkacağını sanmıyorum. Muhtemelen /images/ sitede ilk çıkan resimle alakalı o yüzden zaman kaybetmeye gerek yok. Yine de emin olmak isterseniz ip adresinin yanına /images/ ekleyip siteyi tekrar görüntüleyebilirsiniz. Devam edelim :

![6](https://user-images.githubusercontent.com/97543719/225926990-28d29151-2d35-4c25-ba3d-e291dadb7400.PNG)

##### En başlarda bir yere not edelim dediğim ftp yi kullanalım. ftp "ip" komutunu uygulayalım, Anonymous ile girişe izin verdiğinden onu yazdığımız zaman ftp ile işlem yapar hale geleceğiz :

![5](https://user-images.githubusercontent.com/97543719/227784107-2b6d1d9b-3025-47f4-98b7-ac2c6cbee951.PNG)

##### Arkadaşlar bir de burada bence ne olur ne olmaz ftp ye girince passive komutunu yazın ki passive mode kapansın yoksa işlemlerinizi gerçekleştiremezsiniz. Bu dediğim sıkıntı herkeste olmaz lakin geneli bu problemle karşılaşır ve ftp iznim yok galiba diye düşünüp işlemine son verir aklınızda bulunsun. 

##### ls dedikten sonra locks.txt ve task.txt leri gördüm. Bunları kendime alayım ki içinde neler varmış kurcalayabileyim. get locks.txt ve get task.txt işlemlerini uygulayıp ftp den çıkıyorum artık. 

##### Terminalimizde task.txt ve locks.txt yi kurcalayalım bakalım. cat task.txt , cat locks.txt :

![1](https://user-images.githubusercontent.com/97543719/227784288-e6ae2d40-9ea5-4dd5-a656-ca194738cff7.PNG)

##### Lin tarafından yazılmış görevler ve muhtemelen parolaların yer aldığı bir liste görüyoruz. Bunlar bizim çoook işimize yarayacak. Acaba listedeki hangi parola Lin'e ait? Onu bulursak Lin kullanıcısıyla elimizi kolumuzu sallayarak gireriz. Hydra komutuna hazır olun :

![1](https://user-images.githubusercontent.com/97543719/227784476-1f2804b9-3c71-451d-b60c-318888117ff7.PNG)

##### Komutumuz bize sonucu güzel bir şekilde sundu. Artık oturum açmak için daha fazla beklemeye gerek var mı :

![2](https://user-images.githubusercontent.com/97543719/227784515-987af5ad-3b92-4e1c-9e88-b17fc369bc6f.PNG)

##### Flag e adım adım yaklaşıyoruz. ls diyelim :

![11](https://user-images.githubusercontent.com/97543719/225930634-9bd378bf-54d3-4ffa-8d9a-b502db48ec66.PNG)

##### THM nin bizden istemiş olduğu user.txt yi okumayı başardık. root.txt yi de bulmamızı istiyordu son olarak. Bunun için root olmamız gerekiyor ve biz henüz Lin olarak varız :

![12](https://user-images.githubusercontent.com/97543719/225931037-59b99b54-900d-41f7-aba5-7d18f4b4d066.PNG)

##### sudo -l komutunu yazıp Lin'in parolasını doğru girdiğim halde bir engelle karşılaşıyorum. O da tar engeli. Bu engeli aşabilmek için tarayıcımda sudo tar privilege escalation araştırması yapıyorum ve tar engelinden beni atlatacak olan komutu buluyorum :

![13](https://user-images.githubusercontent.com/97543719/225931510-8a9bf9c0-9067-488b-bef9-b1d4e7baa6e1.PNG)

##### Komutu uyguluyorum ve parola dahi girmeden beni root olarak atadığına şahit oluyorum. whoami diye test ettiğimde de root olduğumu görüyorum :

![14](https://user-images.githubusercontent.com/97543719/225931853-a074f4ad-7917-4b62-bc83-e64b90b2d2c6.PNG)

##### cd /root kısmına gidip ls dediğimde root.txt ye ulaşmış oldum. Son olarak da cat root.txt diyoruz ve flag karşımızda. Dayak yemekten kurtardığımız erkkeğimize tebesüm ediyor ve bir sonraki CTF'e geçiş yapıyoruz. Umarım faydalı olmuştur!







