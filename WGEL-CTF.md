##### Kolay makineyi çözüp eğlenmemiz istenmiş, eğlenelim bakalım :

![1](https://user-images.githubusercontent.com/97543719/227779557-d7b97963-6600-4f0b-9a7b-b7164672ac20.PNG)

![2](https://user-images.githubusercontent.com/97543719/227779576-d2aa68a4-b562-4a19-8ab9-019936fe71bd.PNG)

##### 80 portunun açık olduğunu görürsek dayanamıyorduk :

![3](https://user-images.githubusercontent.com/97543719/227779590-849a953e-d007-4f59-b049-06a763f2e2c7.PNG)

##### Easy makinelerde görmeye alışık olduğumuz bir ubuntu sayfası karşıladı bizi. Kaynak kodunu inceleyelim :

![4](https://user-images.githubusercontent.com/97543719/227779640-d6e82dc4-87b3-4039-b8d8-65bf64bbd7a6.PNG)

##### Buradaki Jessie kişisini kesinlikle not alıyoruz. Başka bir ipucu görmediğimizden çıkıyoruz kaynaktan. GoBuster sevsek de biraz farklılık olsun, dirsearch kullanalım :

![5](https://user-images.githubusercontent.com/97543719/227779849-5c89aea1-a40c-4e7f-81f8-a047cc6d2c3b.PNG)

##### /sitemap/ çok çekici durmuyor mu? Hemen tarayıcımıza koşuyoruz :

![6](https://user-images.githubusercontent.com/97543719/227779939-af94180c-c213-4365-84e0-ee7014229d24.PNG)

##### Gayet güzel özennmişler siteye. Tebrik ediyoruz ve sitede biraz geziniyoruz. Kaynak kodda da bir şeyler bulamadık. Görünmeyen tarafları görebilme umuduyla bir search daha yapalım mı :

![7](https://user-images.githubusercontent.com/97543719/227780206-eb0d893f-759a-419e-9ad9-f875c619333e.PNG)

##### Gayet güzel bir sonuç döndürdü açıkçası. Burada en dikkat çekici ve kritik olan konusunda hemfikiriz bence. /.ssh/ :

![8](https://user-images.githubusercontent.com/97543719/227780258-c08d355e-afb5-4aa6-b371-e66f90483045.PNG)

##### Değerli bir bilgi bulduk arkadaşlar. Burada belki de Jessie kullanıcısının şifresi var ve bu sayede oturum açabileceğiz :

![8](https://user-images.githubusercontent.com/97543719/226098717-924f7297-0b7f-45bc-af5f-4d288b3f4df9.PNG)

##### Bu anahtarı txt olarak kaydedin. ben root içinde rsa.txt diye kaydettim. Bunu kullanarak çılgın şeyler yapabiliriz, bunun öncesinde hevesimizi kursağımızda bırakmasın diye chmod 600 rsa.txt ayarını da yapalım ki anahtarı kullanmamızı engelleyemesin :

![9](https://user-images.githubusercontent.com/97543719/226098792-2b5137cd-360b-4807-a7d9-46cc86d6af9a.PNG)

##### Artık hazırız sanki ve başlayalım :

![10](https://user-images.githubusercontent.com/97543719/226098808-f94dfd11-f1f4-4841-ad29-7b3f63ff7a50.PNG)

##### Başarılı şekilde oturum açmış bulunuyoruz. Biraz gezinme zamanı :

![11](https://user-images.githubusercontent.com/97543719/226098844-6aa19aeb-8402-4324-b918-7c0c80c9a757.PNG)

##### Burada aradığımızı göremiyoruz sanki. Daha diplerde saklamış olabilir. Documents e bir bakalım mesela :

![12](https://user-images.githubusercontent.com/97543719/226098883-ee6a9e6f-5bd3-45cc-b817-f6b00e1b88b5.PNG)

##### user_flag.txt mizi bulmayı başardık. Az çok tahmin edebiliyoruz. root olmadan root_flag.txt ye ulaşamayacağımızı. Bu arada root bayrağı root_flag.txt olmayabilir kanıtımız yok sonuçta ama user_flag.txt formatında yazılmış, root bayrağı da bu formatta saklanmıştır diye tahmin yürüttüm. Senaryo tutmazsa başka bir çözüm yaparız :

![13](https://user-images.githubusercontent.com/97543719/226098997-ac44c851-e904-4728-bdb6-087179b1617d.PNG)

##### sudo -l yapıp root yükselmesini denediğimde wget ile alakalı bir engel çıkarttı karşıma. Bu engeli aşmamı sağlayacak bir arama yapıyorum tarayıcımda :

![14](https://user-images.githubusercontent.com/97543719/226099028-4e576169-b271-4897-8c51-4efa19bf9099.PNG)

##### Birkaç tanesini denedim lakin işimi gören file upload oldu arkadaşlar. Bu yüzden bundan ilerleyeceğim :

![16](https://user-images.githubusercontent.com/97543719/226099070-62fd186f-01f0-4305-ba6a-95a3a5957e02.PNG)

##### Dinlememi başlattım 4545 portundan. Diğer taraftan komutlarımı da hazırladım :

![15](https://user-images.githubusercontent.com/97543719/226099128-824aad90-a105-4621-99e1-5b9cae284379.PNG)

##### Gördüğünüz gibi yanıt verdi ve aradığımızı bulduk :

![16](https://user-images.githubusercontent.com/97543719/226099395-9744c0cc-7fbd-420b-b008-244076305ed1.jpg)

##### Kolay makineyi çözdük, eğlendik sanırım. Umarım faydalı olmuştur!




