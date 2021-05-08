Daha fazla bilgi için --> [Proje Raporu](https://github.com/mustafayigit34/flutter-mobilSorgular-YazLab/files/6412286/Rapor.pdf)

# Mobil Sorgular
## Kurulum
Öncelikle ```pubspec.yaml``` dosyasında ```flutter pub get``` komutunu çalıştırmanız gerekmektedir. Aksi taktirde çalışmayacaktır.
Daha sonra ```"lib\main.dart"``` yolunu izleyerek ```flutter emulators --launch "Your Emulator Name"``` ile sanal cihazını çalıştırıp ardından ```flutter run``` komutuyla uygulamayı çalıştırabilirsiniz.
## Giriş
Bu projede Firebase Firestore üzerinden 
çeşitli sorgular yapılarak filtrelenmiş veriler alınmış, ardından bu veriler ile proje isterleri üç aşama halinde gerçeklenmiştir.
İlk aşamada veritabanı üzerinde bulunan 
verilerden istere uygun olan veriler getirilmiştir. İkinci aşamada ise kullanıcı uygulamaya daha çok dahil edilmiş ve kullanıcı 
tarafından seçilen başlangıç-bitiş tarihine, 
bölge adına göre istere cevap niteliğinde 
olan veriler ekranda saydırılarak sıralanmıştır. Üçüncü ve son aşamada ise projeye 
Google Maps ürünleri dahil olmuş ve kullanıcıdan alınan sınırlamalara göre üretilen 
sonuç harita üzerinde çizdirilerek kullanıcıya görsel bir sonuç sunulmuştur. Kullanıcıların tüm bu işlemleri yapabilmesi için 
bir mobil uygulama tasarlanmıştır.

## Yöntem
Bu projede izlenilen yol aşağıda anlatılmıştır: <br>
Proje isterlerine geçmeden önce projede 
kullanılacak verilerin sayısının azaltılması 
ve bulut ortamına yüklenmesi işlemleri 
Python dili kullanılarak yapılmıştır. Daha 
sonra ise proje isterlerine geçilmiştir. Proje 
üç tip sorgu için üç aşama şeklinde 
tasarlanmıştır. <br>
Veriler https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page sitesinden alınıp birkaç düzenleme ile Firebase Firestore'a aktarılmıştır.
Dosya isimleri: <br><br>
```yellow tripdata 2020-12.csv``` <br>
``` taxi+ zone lookup.csv``` <br><br>
olup indirildikten sonraki düzenlemeler ile Firestore'da şu şekilde görülmektedir: <br><br>
![trips](https://user-images.githubusercontent.com/65903573/117537692-57da8680-b00b-11eb-9005-bd2d86916325.png)
![zones](https://user-images.githubusercontent.com/65903573/117537654-1944cc00-b00b-11eb-8704-9213d2e70b1c.png) <br>
Belge (collection9 isimleri sırasıyla "trips" ve "zones" olmalıdır. <br>
Belgede değişiklik yapılmasının sebebi, Google Maps'te yol çizdirme işleminin yapılabilmesi için enlem (latitude) ve boylam (longitude) bilgilerine ihtiyaç duyulmasıdır. <br><br>
Uygulama çalıştırıldığında şu şekilde görülecektir: <br><br>
![anasayfa](https://user-images.githubusercontent.com/65903573/117537902-6d03e500-b00c-11eb-91f0-80252be08b8c.png) <br><br>
### Aşama 1 (Tip 1 Sorgu):
Kullanıcı ana menü ekranında “TİP 1 SORGU” butonuna tıkladığında Firebase Firestore üzerinden “en uzun mesafeli beş yolculuktaki gün ve mesafeler” isterini sağlayacak veriler çekilmektedir. Verilerin çekilmesini sağlayan sorgu, uygulamanın içerisinden Firebase’e gönderilmektedir. Sorgu ile elde edilen veriler cihaz ekranında art arda sıralanarak gösterilmektedir. <br><br> 
![sorgu1](https://user-images.githubusercontent.com/65903573/117537968-ba805200-b00c-11eb-9f69-9a6bd31fb923.png) <br><br>
![sorgu1_sayfa](https://user-images.githubusercontent.com/65903573/117538004-d5eb5d00-b00c-11eb-98d8-898f9c2ffc4d.png) <br><br>
