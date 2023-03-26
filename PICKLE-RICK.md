##### Turşuya dönüşen Rick'in ibretlik hikayesine üzüldükten sonra nmap taramamıza başlıyoruz :

![1](https://user-images.githubusercontent.com/97543719/227777967-da77e0d5-067a-4b31-a99b-e909305630e3.PNG)

![2](https://user-images.githubusercontent.com/97543719/227777981-7e7f9efa-2f93-429f-8dd3-094209213204.PNG)


##### 80 portunun açık olduğunu görüp de siteye bakmamak olmaz :

![3](https://user-images.githubusercontent.com/97543719/227777997-5cb804f2-a723-43e5-8347-4bc718bac550.PNG)


##### Sayfanın kaynak kodunu inceleyelim, belki bir ipucu ya da açık buluruz :

![4](https://user-images.githubusercontent.com/97543719/227778021-792ec0fb-cde6-4787-b7e8-33adde8cc96f.PNG)


##### R1ckRul3s kullanıcı adını bir yere not edelim. Başka bir şey bulamadığımız için çıkalım buradan. GoBuster taramamızı yapalım, dileyenler dirsearch -u "ip" komutunu da kullanabilirler elbette :

![5](https://user-images.githubusercontent.com/97543719/227778088-f76c23dc-9ba6-4db5-8968-fbadd5da4770.PNG)


##### Dikkatimi çeken /assets/ 'i incelemek istiyorum :

![6](https://user-images.githubusercontent.com/97543719/227778105-8018ca40-5cfa-42cb-964d-be2995f9d369.PNG)


##### Beklentimi karşılamadı. Oradaki dosyalardan bize ekmek çıkmaz arkadaşlar lakin emin olmak isterseniz inceleyebilirsiniz ben daha çok ilgimi çeken /login.php/ ile uğraşmak istiyorum :

![Uploading 8..PNG…]()


##### Bir köşeye not aldığımız R1ckRul3s kullanıcı adını burada kullanacak gibiyiz sanki? Peki parolası ne ola ki :

![4](https://user-images.githubusercontent.com/97543719/225948106-a80331ca-d419-4e05-b52e-1ddee2c012cd.PNG)

##### Burada sessiz sakin duran bir o kadar da dikkatimi çeken /robots.txt/ 'yi de görüntülemek istiyorum vee :

![7](https://user-images.githubusercontent.com/97543719/227778234-4064a3f4-9d0f-4e82-b2ed-09b576bc28dd.PNG)


##### Bu bir parola olabilir mi diye kafada kurmalara başlıyoruz ve yanılmıyoruz :

![8](https://user-images.githubusercontent.com/97543719/225948540-26b0e9c8-06ff-4769-a521-8a20de97e2a8.PNG)

##### Gerçekten de parolası buymuş. Bizi yeni bir sayfa karşıladı. Burada belli komutları uygulayabilirim :

![9](https://user-images.githubusercontent.com/97543719/225948850-6b2deb32-ae67-4171-a9d8-215d99a3cd81.PNG)

##### Belli başlı komutları uygulamama izin verip daha ileriye gittiğim zaman bana kızıyor. ls -la 'dan sonra daha acımasız komutları uygulamak için kendisine söz veriyorum :

![10](https://user-images.githubusercontent.com/97543719/225949255-f33d8888-97ab-4082-a33c-677971f4cb23.PNG)

##### Bunun için kadim dostumuz pentestmonkey'den kopya çekiyoruz azıcık. Birkaçını denedim lakin tepki veren perl oldu :

![11](https://user-images.githubusercontent.com/97543719/225949442-047f9457-acc2-4602-9e51-5d67c2973fc8.PNG)

##### Terminalimizde nc -lvp 1234 portu üzerinden bir dinleme yaparak komutlarımıza cevap verecek mi diye test ediyoruz, port seçimi tercihe bağlıdır. Komut paneline seçtiğiniz portu ve kendi ip nizi yazmayı unutmayın :

![12](https://user-images.githubusercontent.com/97543719/225949960-c1af6e95-2af0-4533-92d8-b9683b73c38d.PNG)

##### Bakınız dinlemem olumlu oldu. Erişimi sağlar sağlamaz görselde de gördüğünüz gibi belli komutları çalıştırdım ve THM'nin benden istediklerine ulaştım :

![13](https://user-images.githubusercontent.com/97543719/225950238-50eb4923-eec7-4dea-a651-7d43de01ce87.PNG)

##### Belli bir alanda sıkıştığımı ve bilgi açısından yetersiz olduğumu gördüm. Daha ileri gitmek ve daha fazla bilgiye ulaşmak için cd /home yaptım, ardından ls -la dedim ve :

![14](https://user-images.githubusercontent.com/97543719/225950863-6242a81f-a7f5-44c4-ab5a-e6e379a9fde2.PNG)

##### cd komutumu görmezden gelin .d cat komutu ile devam edin. Son aşamaya geldiğimin farkındayım ama yine sınırlı hissediyorum kendimi. Ne lazım başka? root olmak lazım :

![15](https://user-images.githubusercontent.com/97543719/225951149-f7feff79-fe30-4ddc-a8f6-1f7e5be492a4.PNG)

##### sudo -l  dediğimde absürt bir manzara karşıma çıkıyor. Bize root olmamız için parolaya ihtiyacımızın olmadığını söylüyor. Bu nasıl iş böyle diyoruz ve sudo su yazıyoruz :

![16](https://user-images.githubusercontent.com/97543719/225951393-0cc5eaf9-ec50-49b0-a8df-5bf53f776bbd.PNG)

##### whoami dedik, root olmuşuz harbiden. cd  /root dedik,  ls -la yaptık ve aradığımız tam olarak karşımızda. cat 3rd.txt dedik ve Rick arkadaşımızın ibretlik hikayesine katkımız son bulmuş oldu. Umarım faydalı olmuştur!




















