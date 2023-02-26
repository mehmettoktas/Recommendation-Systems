# Recommendation-Systems
I did project about Recommendation Systems &amp; User Based Recommendation project.
Adımlar¶
1- Veri Hazırlama

2- Öneri Yapılacak Kullanıcının İzlediği Filmlerin Belirlenmesi

3- Aynı Filmleri Kullanıcıların Verisine, ID'lerine Erişilmesi

4- Öneri Yapılacak Kullanıcı ile En Benzer Kullanıcıların Belirlenmesi

5- Weighted Average Recommendation Score'un Hesaplanması, İlk 5 Filmin Tutulması

Yapılan İşlemlerin Açıklanması
1- Veri Hazırlama
Tavsiye sistemlerinde ilk önce veriyi çalışmaya uygun formata getirmemiz gerekiyor. Bu yüzden veri hazırlama adımı ile projeye başlıyoruz Bu adımda sırasıyla yapılanlar;

1- Gerekli kütüphanelerin import edilmesi

2- Dataframe görüntülemek için yapılan görüntü ayarları

3- Veri setlerini ortak sütun üzerinden birleştirmek. Örneğin movie ve rating veri setlerinin ortak sütunu "movieId" sütunudur.

4- Hangi filme kaç yorum yapıldığını öğrenmek

5- Belirli sayının (1000) altında yorum alan filmleri veri setinden çıkartmak, üzerinde ne kadar bilgi varsa o kadar sağlıklı öneri yapılacağı için.

6- Her bir kullanıcının yorum yaptığı filmleri pivot tablo haline getirmek

2- Öneri Yapılacak Kullanıcının İzlediği Filmlerin Belirlenmesi
1- Rastgele kullanıcı seçmek, o kullanıcının izlediği filmleri belirlemek.

2- Kullanıcının sadece oy kullandığı, attığı filmleri belirlemek. NaN olarak gözüken, izlemediği filmleri liste dışı bırakmak.

3- Aynı Filmleri İzleyen Kullanıcıların Verisine, ID'lerine Erişmek
1- Seçilen kullanıcının izlediği filmlere ait sütunları, yani film adlarını, izlenen filmler olarak kaydediyoruz.

2- İzlenen filmlerin kaçına oy verildiğine bakıyoruz.

4- Öneri Yapılacak Kullanıcıyla En Benzer Kullanıcıları Belirliyoruz
1- Seçilen kullanıcının izlediği filmlerle, diğer kullanıcıların izlediği filmler arasında %60 ve daha fazla benzerlik olanları benzer olarak kaydediyoruz. Öneri yapılacak kullanıcı ile benzer kullanıcıları belirlemiş oluyoruz.

2- Kullanıcıların birbiriyle olan korelasyonlarını buluyoruz. %65’ten yüksek olanları seçiyoruz.

5- Weighted Average Recommendation Score Hesaplanması, 5 Öneri Yapılması
1- Korelasyon ve rating değerlerinin çarpımından oluşan weighted_rating oluşturmak.

2- Filmlerin ID’sine göre weighted rating değerlerinin ortalama değeri bulunması.

3- 3.5’ten büyük olanları seçip sıralıyoruz.

4- İlk 5 gözlemi önerilecek olarak kaydediyoruz.

Değişkenlerin İsimlerinin Anlamı
comment_counts → Filmlere gelen yorumların sayısı

rare_movies → 1.000’den az yorum gelen filmler

common_movies → 1.000 ve daha fazla yorum gelen filmler

user_movie_df → herhangi bir kullanıcının filmlere oy verip vermediğini gösteren pivot tablo

random_user → rastgele bir kullanıcı

random_user_df → seçilen kullanıcının filmlere oy verip vermediğini gösteren pivot tablo

movies_watched → seçilen kullanıcının oy verdiği tüm filmler

movies_watched_df → tüm kullanıcıların, seçilen kullanıcının izlediği filmlere oy verip vermediğini gösteren pivot tablo

user_movie_count → kullanıcıların, seçtiğimiz kullanıcının izlediği filmlerden kaçına oy verdiğini gösteren tablo

users_same_movies → setçiğimiz kullanıcının izlediği filmlerin %60’ından fazlasını izleyen, oy verenlerin sayısı

final_df → tüm kullanıcıların %60’tan fazla oy verenlerden oluşan, hangi filmleri izleyip izlemediğini gösteren tablo

corr_df → final_df’teki kullanıcıların birbiriyle korelasyonu

top_users → seçtiğimiz kullanıcının diğer kullanıcılarla %65 ve daha fazla korelasyon sağlayanların yer aldığı tablo

top_users_ratings → seçili kullanıcıların korelasyon ve rating değerlerinin çarpılması

recommendation_df → bu skorların film Id’sine göre sıralanıp, ilk 5’in önerildiği son veriseti
