##### SQL enjeksiyonu barındıran öğretici CTF Simple dan devam ediyoruz :

![1](https://user-images.githubusercontent.com/97543719/226121075-c344d6d3-2181-4766-850d-9c39bfb70979.PNG)

##### Klasik port scan yaptıktan sonra tarayıcımızı açıyoruz, Bu arada ssh'da 2222 portunun kullanıldığını görmek önceki CTF lere göre orijinal olmuş :

![2](https://user-images.githubusercontent.com/97543719/226121281-c8a57bd0-f417-4765-bd06-fc73eab7cd1c.PNG)

##### Görmeye alışık olduğumuz ubuntu sayfası karşıladı bizleri. Kaynak kodunu hızlıca inceledim. Bize oradan ekmek çıkmayacağını görünce directory yapmaya başladım :

![3](https://user-images.githubusercontent.com/97543719/226121458-a830aa20-7da7-4e17-b25c-31932b2694b9.PNG)

##### /simple çok çekici durmuyor mu? Hemen tarayıcıda deneyelim :

![4](https://user-images.githubusercontent.com/97543719/226121500-9ebe7670-e62a-4d30-b307-47ee23617fed.PNG)

##### CMS karşılıyor bizi. Biraz gezindiğimde görüyorum ki altta bir sürüm bilgisi var. Emin olun bu kısmı kasıtlı olarak koyuyorlar :

![5](https://user-images.githubusercontent.com/97543719/226121563-8d2ec97b-4df7-4f23-a95a-dd2bd540881b.PNG)

##### Sürüm hakkında araştırma yapmamız gerekiyor. Zafiyet bulmamız an meselesi. Bunun için searchsploit kullanalım :

![6](https://user-images.githubusercontent.com/97543719/226121623-0324e609-a741-46ed-84de-0effeb13bd35.PNG)

##### Buram buram SQL enjeksiyonunun olduğunu söyleyen bir sonuç çıktı karşımıza. Aradığımız dosyayı bulmak için klasik locate komutunu kullanıyorum :

![7](https://user-images.githubusercontent.com/97543719/226121726-3c190d3b-2c89-4b48-be14-a410d2255948.PNG)

##### Vee aradığımızı bulduk. Dosyayı okumak için leafpad kullanabiliriz. Halihazırda yoksa apt install leafpad yapıp kaldığınız yerden devam ediniz :

![8](https://user-images.githubusercontent.com/97543719/226121818-a24f48b1-84d6-4374-868c-082ae215420d.PNG)

##### Bu komutu enterlayınca karşımıza bizden istenenlerden birisi çıktı bile. CVE-2019-9053. Bu açık Simple 2.2.8 SQL enjeksiyonunu ilgilendiren bir açıktır :

![9](https://user-images.githubusercontent.com/97543719/226122025-5059f700-21ec-4c76-aeee-ee4bdfb1969a.PNG)

##### Şu uzunca yazdığım komutu bulunduğunuz yere ismini değiştirerek kopyalayın uzun uzun uğraştırmasın :

![10](https://user-images.githubusercontent.com/97543719/226122139-8c80755c-f477-43ac-8276-304f1155dd75.PNG)

##### Artık .py mizi çalıştırabiliriz. Python ile bunu kolaylıkla gerçekleştirebiliriz :

![11](https://user-images.githubusercontent.com/97543719/226122195-91cc5a24-7399-4c14-8de0-b00df205b67d.PNG)

##### Derken bize sorun olduğunu raporladı. Kodun 25. satırında hata olduğunu söylüyor. Hatayı düzeltmezsek çalıştıramayacağız haliyle, E düzeltelim madem :

![12](https://user-images.githubusercontent.com/97543719/226122285-319bcd59-acde-47c2-afb7-dfeb9ecea8a7.PNG)

##### leafpad ile .py nizi açın ve 25. satıra doğru gelin. Düzeltilmiş halini koydum buraya, dikkatinizi çektiyse print kısımlarına parantez eklenmemiş. Hatayı düzeltip çıktıktan sonra :

![13](https://user-images.githubusercontent.com/97543719/226122359-0721b294-bd9a-49de-a22a-cfb720fd9f6a.PNG)

##### 63. satırda sıkıntı var dedi. İlkel bir yöntem olan tekk tekk düzeltme yöntemi utandırsa da devam ediyoruz :

![14](https://user-images.githubusercontent.com/97543719/226122539-40dcfbec-25c4-4bc2-9bd2-e0d6117736b9.PNG)

##### print yanına parantezleri ekliyoruz yine. Başka sorun yok sanırım, bu sefer olacak gibi :

![15](https://user-images.githubusercontent.com/97543719/226122595-e9f65a6d-b70b-4a35-9cac-2e329881a730.PNG)

##### En başından kontrolümüzü yapsak bunlara gerek olmayacaktı. Son satıra yaklaştığı için başka hata olmayacağını umuyorum en azından :

![16](https://user-images.githubusercontent.com/97543719/226122641-c778da48-740b-4fd0-9c43-864dde36093e.PNG)

##### Buraya da parantezleri koyduk. Dediğim gibi siz böyle uğraşmayın tek tek. Hem zaman kaybı hem de komik. Artık .py mizi işleme sokabiliriz :

![17](https://user-images.githubusercontent.com/97543719/226122716-e97eed85-641b-43f4-9a04-c6d6e47435f0.PNG)

##### Hangi talimatları uygulamam gerektiğini söyledi. Hemen uygulamaya geçiyorum :

![18](https://user-images.githubusercontent.com/97543719/226122757-a377f524-0d62-403e-98e7-dd688a61e292.PNG)











