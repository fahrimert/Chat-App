# Üniversite ve Bölüm Tabanlı Gerçek Zamanlı Mesajlaşma Uygulaması

Bu proje, kullanıcıların üniversite ve bölümlerine özel mesajlaşma grupları oluşturarak, gruplara katılmasını ve gerçek zamanlı sohbet rubu kurmasını sağlayan bir platformdur. Kullanıcılar, grup üyeleriyle mesajlaşabilir, oradan üyeleri ekleyebilir, özel mesajlaşma (DM) yoluyla birebir sohbet edebilir. 

## Özellikler

- **Üyelik Sistemi**: Kullanıcılar, üniversite emailleri ile kayıt olur ve üniversite ile bölüm bilgilerini seçerek giriş yapar.
- **Gerçek Zamanlı Mesajlaşma**: PubNub kullanılarak gruplar ve birebir sohbetlerde gerçek zamanlı mesajlaşma deneyimi sunar.
- **Grup Özellikleri**:
  - Üniversite ve bölümlere özel gruplar oluşturma.
  -Gruplardan Üyeleri Ekleme.
  - Gruplardan çıkma.
- **Birebir Sohbet (DM)**: Kullanıcılar, grup üyelerini ekleyerek birebir sohbet başlatabilir.
- **Şifre Sıfırlama**: Resend ile email doğrulama ve şifre sıfırlama özellikleri.
- **Veri Yönetimi**:
  - Redis ile gerçek zamanlı veri saklama.
  - PostgreSQL ile ilişkisel veri yönetimi.
- **Docker Desteği**: Redis ve PostgreSQL containerları ile proje kurulumu kolaylaştırılmıştır.

## Kullanılan Teknolojiler

### Frontend
- **Next.js**: React tabanlı framework.
- **TailwindCSS**: Hızlı ve modern UI tasarımı için.
- **shadcn/ui**: Kullanıcı arayüzü bileşenleri.

### Backend
- **Next.js API Routes**: Sunucu tarafı işlemler için.
- **Redis**: Gerçek zamanlı veri yönetimi.
- **PostgreSQL**: İlişkisel veri tabanı.
- **Prisma**: ORM olarak veri tabanı yönetimi.

### Gerçek Zamanlı Mesajlaşma
- **PubNub**: Mesajlaşmaların gerçek zamanlı olması için.

### Authentication
- **JWT**: Kullanıcı doğrulama ve oturum yönetimi.
- **Resend**: Şifre sıfırlama ve email doğrulama için.

### Medya Yönetimi
- **Cloudinary**: Grup profil fotoğrafı ekleme.

### Diğer
- **Docker**: Redis ve PostgreSQL için container yönetimi.

## Kurulum

Projeyi yerel ortamınızda çalıştırmak için aşağıdaki adımları izleyin:

1. **Proje Deposu**: Bu repoyu klonlayın.
   ```bash
   git clone https://github.com/kullanici/repo-adi.git
   ```

2. **Bağımlılıkları Yükleyin**:
   ```bash
   npm install
   ```

3. **.env Dosyasını Oluşturun**:
   Gerekli ortam değişkenlerini içeren bir `.env` dosyası oluşturun.
   
   ```env
   DATABASE_URL=postgresql://user:password@localhost:5432/dbname
   REDIS_URL=redis://localhost:6379
   CLOUDINARY_URL=cloudinary://api_key:api_secret@cloud_name
   JWT_SECRET=your_jwt_secret
   PUBNUB_PUBLISH_KEY=your_publish_key
   PUBNUB_SUBSCRIBE_KEY=your_subscribe_key
   PUBNUB_PUBLISH_KEY=your_publish_key2 #farklı bir app daha kurup pubnubda ona ait publish key de gerekiyor 
   PUBNUB_SUBSCRIBE_KEY2=your_subscribe_key2 #farklı bir app daha kurup pubnubda ona ait subscribe key de gerekiyor 
   RESEND_API_KEY=your_resend_api_key
   ```

4. **Docker Containerlarını Çalıştırın**:
   ```bash
   docker-compose up -d
   ```

5. **Prisma ile Veri Tabanını Migrasyon Yapın**:
   ```bash
   npx prisma generate
   npx prisma migrate dev
   npx prisma db push
   ```

6. **Uygulamayı Başlatın**:
   ```bash
   npm run dev
   ```

## Kullanım

1. **Kayıt Olun**: Üniversite email adresinizle kayıt olun ve üniversitenizi ve bölümünüzü seçin.
2. **Gruplara Katılın**: Üniversitenize veya bölümünüze özel mesajlaşma gruplarına katılın.
3. **Mesajlaşın**: Grup içinde diğer kullanıcılarla gerçek zamanlı sohbet edin veya birebir DM başlatın.
4. **Grup Fotoğrafı Ekleyin**: Grup oluştururken fotoğraf yükleyin ve gruplardan çıkma işlemini gerçekleştirin.

## Katkıda Bulunma

Bu projeye katkıda bulunmak için aşağıdaki adımları takip edebilirsiniz:

1. Fork yapın.
2. Kendi branch'inizi oluşturun: `git checkout -b yeni-ozellik`.
3. Değişikliklerinizi commit edin: `git commit -m 'Yeni özellik eklendi'`.
4. Branch'inizi push edin: `git push origin yeni-ozellik`.
5. Pull request gönderin.

## Lisans

Bu proje [MIT Lisansı](LICENSE) ile lisanslanmıştır.
