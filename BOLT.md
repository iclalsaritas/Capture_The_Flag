##### Sevimli Bolt ve şaşkın Admin kombinasyonlu makinemize başlıyoruz :

![1](https://user-images.githubusercontent.com/97543719/229149233-3015c076-b998-4000-b5f3-dda72e48b17b.PNG)
![2](https://user-images.githubusercontent.com/97543719/229149362-bd50fd89-932f-49af-bc41-e4e1ff46b993.PNG)

##### 8000 portunun açık olduğu notunu aldıktan sonra tarayıcıma gidiyorum :

![3](https://user-images.githubusercontent.com/97543719/229149809-3ed9208b-2528-434f-a8b3-9c59bc65444f.PNG)

##### Görmeye alışık olduğumuz ubuntu sayfası çıktı karşımıza. Not aldığım 8000 portu ile tekrar bir çalışayım :

![4](https://user-images.githubusercontent.com/97543719/229150216-4e418d0a-9b84-472a-9a16-cf65d00a998e.PNG)

##### Karşımda beliren sitede gezindim biraz ve gezinme sonucu bir şey buldum :

![6](https://user-images.githubusercontent.com/97543719/229150723-5b944ec0-c856-4b78-b020-2c231e5208d9.PNG)

![5](https://user-images.githubusercontent.com/97543719/229150504-41028e9d-0e09-44f6-bfd0-47669fe11482.PNG)

##### Kullanıcı adı Bolt şifre ise boltadmin123, bunları değerlendirebilmek için login sayfasına ihtiyacımız var. Ufak bir bolt cms login araştırması yaptım ve /bolt yazdığımda login sayfasına erişebileceğim sonucuna vardım :

![7](https://user-images.githubusercontent.com/97543719/229152039-cc0f157d-b5b3-4ca4-9954-0f912080d706.PNG)

##### Sayfaya kullanıcı bilgilerini girdim :

![8](https://user-images.githubusercontent.com/97543719/229152759-6ead0e58-a2ac-4c88-b9a4-dc2f2ca84e14.PNG)

![9](https://user-images.githubusercontent.com/97543719/229153452-30989674-ee18-4192-8eaf-d50f608cae67.PNG)

##### Dashboard çevresinde ufak bir gezinme sonucu versiyon bilgisine ulaştım. Bolt CMS 3.7.1'in exploitini aramaya başladım :

![10](https://user-images.githubusercontent.com/97543719/229154561-eed9f286-0200-456d-863c-f6fe38103156.PNG)

##### 3.7.1 için hazırlanmış bir repoya ulaştım. Internette 3.7.0 için kaynaklar vardı daha çok bu yüzden bu repo oldukça işime yaradı. Leafpad'e bolt.py olarak kaydettim. Kodu biraz incelemiştim. Kodda bahsettiği talimatları uyguladım. Python ile çalıştırmamı, py dosyası belirtmemi ve adresi yazıp kullanıcı adı - parola yazmamı istiyordu :

![11](https://user-images.githubusercontent.com/97543719/229155256-20de7034-f103-426d-a688-53e70b7017d6.PNG)

##### whoami yazdığımda yetki yükseltmeye gerek kalmadan root olduğumu söyledi. Bu arada Dashboardda gezindiğinizde dosya yükleme kısmını görmüşsünüzdür. jpg gibi formatlarda yükleme yapabileceğimizi söylüyordu. O taraftan da bir şeyler deneyebilirdik ama daha kolayını aramak istedim çünkü yükleme izinleri sınırlıydı. Neyse, shell almak için 1 yaz dedi. 1 yazıp ip adresimi ve portu girdim :

![12](https://user-images.githubusercontent.com/97543719/229158312-50e9bb6a-9dff-4ee8-aeb2-2771965a6077.PNG)

##### Bunu ilk başta yapmak faydalıdır. Çünkü uygulama kendi içinde dinleme yapıp benim dinleme yapmama engel olabilir. O yüzden ilk başta bunu bir çalıştırmak faydalıdır. Şimdi 3311'den dinlememi başlatmak istiyorum :

![13](https://user-images.githubusercontent.com/97543719/229158750-082243d4-c1a2-463f-b05a-953935866202.PNG)











