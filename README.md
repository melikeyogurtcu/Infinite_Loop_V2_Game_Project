# Infinite_Loop_V2_Game_Project
2022-2023 Game Programming Final Project

# Oyun Bağlantısı
https://memirerdem.itch.io/infinite-loop-v2

# ÜST NOT

Vize için yapılan oyunun üzerine eklentiler yapılmıştır. Bir önceki oyunun devamı niteliğindedir.

# Oynanış
Düz bir hat üzerinde rastgele konumlarda engeller ve ödüller çıkan sonsuza kadar kadar giden bir platforming oyunu. Karakterin 3 canı var ve kırmızı engellere çarptıkça canı azalmakta. 1 canı kaldığında sahne değişmekte. Eğer aşağıya düşerse ana menüye geri dönmekte. Canları sıfırlandığında yine ana menüye geri dönmekte. User Interface'de can göstergesi kasıtlı olarak belirtilmemiştir. Oyuncunun, oyunun ne zaman biteceğini veya sahnenin değişeceğini bilememesi üzerine bir psikolojik baskı oluşturmak hedeflenmiştir.

# Main Menu
![0](https://user-images.githubusercontent.com/76780294/212667245-198d1eee-a68b-4848-9796-6f144aa682f1.JPG)

# First Scene
![1](https://user-images.githubusercontent.com/76780294/204632836-b74e214d-6068-4aa5-af75-18da5fe39d86.JPG)

# Second Scene
![2](https://user-images.githubusercontent.com/76780294/212667291-00100be0-a263-4a4d-b956-236f52cb8d8f.JPG)

# KAYIT KISMI
Oyuna ilk başlandığında Continue buttonu pasif bir şekildedir ve görünmez durumdadır. Sadece New Game buttonu aktif ve görünür durumdadır. Oyuncu eğer oyun içerisinde herhangi bir sahnede ana menüye dönmezse oyun kayıt edilmez ve canı 0 olduğunda direkt ana menüye dönüp sadece New Game buttonunu görür. Eğer oyun içerisinde (ana menü hariç) herhangi bir sahnede ana menüye dönülürse, en son bulunan sahneyi kayıt eder ve Continue buttonu aktif olur. En son hangi sahnede kayıt olduysa, Continue buttonuna basıldığında o sahnenin başından oynamaya başlar (1. sahne veya 2. sahne).

Animasyon kısmı yapılırken idle, sniper ve smg stateleri arasında karşılıklı transitionlar kuruldu. Sniper ve smg parametreleri ile birlikte script üzerinden kontrol edilen ve gerekli şartları sağladığı anda stateler arası geçiş gerçekleşti. Smg ve sniper stateleri arasında transition bulunmasının sebebi sniper animasyonu icra ederken, smg animasyonuna da geçiş yapılabilmesi istendiği içindir.

![statemachine](https://user-images.githubusercontent.com/76780294/212704855-76d4c0c5-dd16-4783-9eec-31c73217b395.JPG)

# Ses ve Müzik

Oyunun ilk açıldığı zamandan itibaren bir döngü şeklinde sonsuza kadar müzik çalmakta ve sahne geçişleri arasında müzik kesilmemekte. Ses olarak, karakterimiz zıpladığı an bir ses efekti çalmakta.

# Kontroller
W -> İleri
S -> Geri / Yavaşlama
A -> Sol
D -> Sağ
Space -> Zıplama

# ANA MENU Kontrolleri
D -> Dinazorun SMG ile olan animasyonu çalışır (biraz basılı tutmak gerekiyor, anında bas çek yapınca çalışmayabiliyor). Sürekli basılı tutunca hep SMG animasyonu çalışıyor.
Space -> Dinazorun SNIPER ile olan animasyonu çalışır (biraz basılı tutmak gerekiyor, anında bas çek yapınca çalışmayabiliyor). Sürekli basılı tutunca hep SNIPER animasyonu çalışıyor.
Space'e basılı tutarken D'ye de basılırsa sırayla animasyonlar çalışıyor.
Hiç bir şey yapmazken, Loop şeklinde yürüme animasyonu çalışmakta.

# Ekipte Görev Dağılımı

Mehmet Emir ERDEM
- Ana Menü
- Sahneler
- Kayıt Alma
- camera_sc, coin_sc, enemy_sc, Mainmenu_sc, moveobj_sc, player_sc, spawn_manager_sc

Melike YOĞURTCU
- Animasyon
- Ses ve Müzik
- animation_sc, music_sc

NOT: Bazı scriptlerin entegre bir şekilde çalışması sebebiyle genel olarak scriptlerde herkesin emeği geçmiştir fakat kişilerin ağırlıkları üzerine sınıflandırılmıştır.
