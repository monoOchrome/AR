# AR
- Kamera açmak için bağlantının güvenli  olması gerekiyor, bu yüzden **https** kullanılmalı.
- Ar kullanımı için browserın **WEBGL ve WEBRTC** desteği olmak zorunda, bundan dolayı IOS safari ve chrome minimum versiyon 11  olmak zorunda. Tüm destekleyen versiyonları bu linkten görebiliriz https://caniuse.com/#search=webrtc  
**Android Chrome 36** - Kamera isteği göndermiyor, siyah ekran veriyor, çalışmıyor  
**Android Chrome 76** - Çalışıyor  
**Android firefox 68** - Çalışıyor  
**IOS Safari 12.4** - Çalışıyor  
**IOS Safari 10 XCODE/Simulator** - Kamera isteği göndermiyor, siyah ekran veriyor, çalışmıyor
- Bu Ar.js plugini production için şu an uygun değil. Repoyu asıl hazırlayan kişi ortada yok ve güncellemeler bu yüzden minimuma inmiş. Stabil çalışmıyor, basic geometrik şekillerde performans alınabiliyor bu da kimin işine yarar bilemiyorum. Kullanan çoğu developer da sadece demo için kullandıklarını, birçok özelliğin eksik olduğunu belirtmişler. Sonuç olarak bu plugin hala development aşamasında.

## Marker
- Marker siyah beyaz olmak zorunda
- Marker şekli komplex olmamalı
- Marker tanımlaması kodsal olarak 0 ve 255 değerleri üzerinden yapılıyor. Parlaklık değişimi bu değerleri değiştirdiği için marker tanımlanamaz ve 3d obje gözükmez. Örneğin önceden tanımlanmış 255 beyaz değeri parlaklık ile 230 a inerse markerı tanımıyor.
##### Link (Desktop linki)
https://monoochrome.github.io/AR/ghpages/marker.pdf

## Tests
- Testler için kullandığım frameworkler: AR.js - A-Frame.js - Three.js
- Testlerde kullanılan modeller **gltf** formatında. Hem performans hem de animasyon olabilmesi için tercih edilen format bu. 
- Her modelin geometri değerleri verildi. Bu değerler ne kadar artarsa performans o kadar düşüyor, telefonda ısınma ve kamerada yavaşlama oluyor. (Test edildi) Burada tercih edilmesi gereken low poly modeller. 

### Hareketli 3D Model
##### Model Geometrisi
|Triangles|Quads|Polygons|Total Triangles|Vertices|
|---|---|---|---|---|
|44|471||986|495|

##### Link (Telefon test linki)
https://monoochrome.github.io/AR/ghpages/index-animated.html

### Hareketli 3D Model - Dinamik Değiştirme
Her refreshde önceden tanımlanmış 2 modelden biri gelecek. Kullanıcıya özel model gösterebiliyoruz.

##### Model Geometrisi 1
|Triangles|Quads|Polygons|Total Triangles|Vertices|
|---|---|---|---|---|
|44|471||986|495|
##### Model Geometrisi 2
|Triangles|Quads|Polygons|Total Triangles|Vertices|
|---|---|---|---|---|
|60|424|8|932|468|

##### Link (Telefon test linki)
https://monoochrome.github.io/AR/ghpages/index-random.html

### Hareketli 3D Model - Click/Touch Event
Marker üzerinde çıkan modele click/touch yaparak modelin içinde tanımlı olan animasyonları değiştiriyoruz. 

##### Model Geometrisi
|Triangles|Quads|Polygons|Total Triangles|Vertices|
|---|---|---|---|---|
|60|424|8|932|468|

##### Link (Telefon test linki)
https://monoochrome.github.io/AR/ghpages/index-click.html
