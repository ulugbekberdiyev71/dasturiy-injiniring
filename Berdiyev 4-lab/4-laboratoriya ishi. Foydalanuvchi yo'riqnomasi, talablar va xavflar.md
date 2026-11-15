# 4-laboratoriya ishi. Foydalanuvchi yo'riqnomasi, talablar va xavflar

**Fan:** Dasturiy injiniringga kirish **Variant:** 03 — Onlayn kurslar platformasi **Mashg'ulot:** 7–8 **Topshiriladigan materiallar:** SRS v1, use case, risk register, user guide draft

## 1. SRS v1: dasturiy ta'minotga talablar spetsifikatsiyasi

### 1.1. Maqsad va qamrov

EduPlatform — o'zbek tilida ishlaydigan onlayn kurslar platformasi. Hujjat MVP uchun talablarni belgilaydi. Talablar 3-laboratoriyadagi user storylar (US) asosida yozilgan; har talab ID va qabul mezoniga ega.

### 1.2. Foydalanuvchi rollari (3 ta)

| Rol | Tavsif | Asosiy imkoniyatlari |
| --- | --- | --- |
| O'quvchi | Kurslarda o'qiydigan foydalanuvchi | Katalog, kursga yozilish, darslar, test, sertifikat |
| O'qituvchi | Kurs muallifi | Kurs, dars va test yaratish |
| Administrator | Platforma moderatori | Kurslarni tasdiqlash, foydalanuvchilarni nazorat qilish |

### 1.3. Funksional talablar

| ID | Talab | Qabul mezoni | Prioritet | Manba |
| --- | --- | --- | --- | --- |
| FR-01 | Tizim foydalanuvchini email va parol bilan ro'yxatdan o'tkazishi va tizimga kiritishi kerak | Email takrorlanmasa, hisob yaratiladi; noto'g'ri parolda xato xabari chiqadi; parol kamida 8 belgi | Yuqori | US-01 |
| FR-02 | Tizim kurslar katalogini ko'rsatishi va nom hamda toifa bo'yicha qidirishni ta'minlashi kerak | Qidiruv so'ziga mos kurslar chiqadi; hech narsa topilmasa «Kurs topilmadi» xabari ko'rinadi | Yuqori | US-02 |
| FR-03 | Tizim kurs sahifasida tavsif, darslar ro'yxati, muallif va narxni ko'rsatishi kerak | Sahifada to'rt maydon ham ko'rinadi | Yuqori | US-03 |
| FR-04 | Tizim o'quvchini to'lovdan keyin kursga yozishi kerak (MVPda to'lov imitatsiya qilinadi) | To'lov muvaffaqiyatli bo'lsa kurs «Mening kurslarim»da paydo bo'ladi; rad etilsa yozilish bo'lmaydi va xato ko'rsatiladi | Yuqori | US-04 |
| FR-05 | Tizim yozilgan kursning darslarini ketma-ket ko'rsatishi kerak | Yozilmagan o'quvchiga darslar yopiq; yozilganga ochiq | Yuqori | US-05 |
| FR-06 | Tizim dars tugatilganini belgilash va kurs progressini foizda ko'rsatishi kerak | 10 ta darsdan 4 tasi tugatilsa, progress 40% | Yuqori | US-06 |
| FR-07 | Tizim testni qabul qilib, natijani avtomatik hisoblashi kerak | To'g'ri javoblar foizi ko'rsatiladi; 60% va undan yuqori bo'lsa test «o'tdi» | Yuqori | US-07 |
| FR-08 | Tizim testdan o'tgan o'quvchiga noyob raqamli sertifikat berishi kerak | Sertifikatda ism, kurs nomi, sana va noyob raqam bor; o'tmagan o'quvchiga berilmaydi | O'rta | US-08 |
| FR-09 | O'qituvchi yangi kurs yaratib, tavsif va narx kirita olishi kerak | Majburiy maydonlar to'ldirilsa kurs saqlanadi; bo'sh qolsa xato ko'rsatiladi | Yuqori | US-09 |
| FR-10 | O'qituvchi kursga dars va test savollarini qo'sha olishi kerak | Qo'shilgan dars va savol kurs sahifasida ko'rinadi | Yuqori | US-10 |
| FR-11 | Administrator yangi kurslarni tasdiqlashi yoki rad etishi kerak | Tasdiqlangan kurs katalogda ko'rinadi, rad etilgani ko'rinmaydi | O'rta | US-11 |

### 1.4. Nofunksional talablar

| ID | Toifa | Talab | Qabul mezoni |
| --- | --- | --- | --- |
| NFR-01 | Ishlash | Sahifalar tez yuklanishi kerak | Asosiy sahifalar oddiy internetda 3 soniyadan kam vaqtda ochiladi |
| NFR-02 | Xavfsizlik | Foydalanuvchi ma'lumotlari himoyalangan bo'lishi kerak | Parol ochiq matnda saqlanmaydi; o'quvchi boshqa o'quvchining ma'lumotini ko'ra olmaydi |
| NFR-03 | Qulaylik | Interfeys o'zbek tilida va mobil qurilmalarda ishlashi kerak | 360 px va undan keng ekranlarda kontent gorizontal aylantirishsiz ko'rinadi; sinovda kamida 10 foydalanuvchining o'rtacha bahosi 4,0/5 dan past emas |
| NFR-04 | Moslik | Tizim zamonaviy brauzerlarda ishlashi kerak | Chrome, Edge va Firefox ning so'nggi versiyalarida asosiy stsenariy xatosiz bajariladi |
| NFR-05 | Ishonchlilik | Ma'lumotlar sahifa yangilanganda yo'qolmasligi kerak | Sahifa qayta yuklangandan keyin foydalanuvchi, kurslar va progress saqlanib qoladi |

## 2. Use case modellari

Asosiy ikkita stsenariy tanlandi: kursga yozilish va test topshirib sertifikat olish.

### UC-01. Kursga to'lov qilib yozilish

| Band | Mazmun |
| --- | --- |
| Aktor | O'quvchi (ikkinchi darajali: to'lov tizimi) |
| Bog'liq talablar | FR-01, FR-02, FR-03, FR-04 |
| Oldingi shart | O'quvchi tizimga kirgan |
| Asosiy oqim | 1. O'quvchi katalogdan kursni topadi. 2. Kurs sahifasini ochib, tavsif va narxni ko'radi. 3. «Kursga yozilish» tugmasini bosadi. 4. Tizim to'lov oynasini ko'rsatadi. 5. O'quvchi to'lovni tasdiqlaydi. 6. Tizim to'lov natijasini oladi. 7. Tizim o'quvchini kursga yozadi va darslarni ochadi |
| Muqobil oqim | A. 5-qadamda o'quvchi bekor qiladi: tizim kurs sahifasiga qaytaradi, yozilish bo'lmaydi. B. 6-qadamda to'lov rad etiladi: tizim xato xabarini ko'rsatadi va qayta urinish imkonini beradi. C. O'quvchi kursga allaqachon yozilgan: tizim «Siz bu kursga yozilgansiz» deb darslarga yo'naltiradi |
| Natija | O'quvchi kursga yozilgan, darslar ochiq |

### UC-02. Test topshirish va sertifikat olish

| Band | Mazmun |
| --- | --- |
| Aktor | O'quvchi |
| Bog'liq talablar | FR-05, FR-06, FR-07, FR-08 |
| Oldingi shart | O'quvchi kursga yozilgan va darslarni tugatgan |
| Asosiy oqim | 1. O'quvchi «Testni boshlash» tugmasini bosadi. 2. Tizim savollarni ko'rsatadi. 3. O'quvchi barcha savollarga javob beradi. 4. «Topshirish» tugmasini bosadi. 5. Tizim to'g'ri javoblar foizini hisoblaydi. 6. Foiz 60 va undan yuqori bo'lsa, tizim natijani saqlaydi va sertifikat yaratadi. 7. O'quvchi sertifikatni ko'radi |
| Muqobil oqim | A. 3-qadamda ba'zi savollar javobsiz: tizim ogohlantiradi, o'quvchi davom ettirishi yoki to'ldirishi mumkin. B. 6-qadamda foiz 60 dan past: tizim natijani ko'rsatadi, sertifikat bermaydi va testni qayta topshirishni taklif qiladi |
| Natija | Test natijasi saqlangan; o'tgan bo'lsa sertifikat berilgan |

## 3. Xavflar reyestri (5 ta xavf)

Ball = Ehtimol (1–5) × Ta'sir (1–5). Daraja: 15 va undan yuqori — yuqori, 8–14 — o'rta, 7 va undan past — past.

| ID | Xavf | Ehtimol | Ta'sir | Ball | Daraja | Oldini olish / javob choralari |
| --- | --- | --- | --- | --- | --- | --- |
| R1 | Vaqt yetishmasligi, ish muddatga ulgurmaydi | 4 | 4 | 16 | Yuqori | Iteratsiyalarga bo'lish; prioriteti past talablarni (FR-11) keyinga qoldirish; haftalik tekshiruv |
| R2 | Talablar o'zgaradi | 3 | 3 | 9 | O'rta | Talablarni ID bilan yuritish; o'zgarishlar tarixini Git'da saqlash |
| R3 | To'lov integratsiyasi murakkab bo'lib chiqadi | 3 | 4 | 12 | O'rta | MVPda to'lovni imitatsiya qilish; to'lov alohida modulda, keyin almashtirish oson |
| R4 | Ma'lumotlar yo'qoladi (brauzer xotirasi cheklovi) | 3 | 4 | 12 | O'rta | Ma'lumotlarni JSON ga eksport qilish; keyingi bosqichda server va ma'lumotlar bazasi |
| R5 | Foydalanuvchi shaxsiy ma'lumotlari va parollari oshkor bo'ladi | 2 | 5 | 10 | O'rta | Parolni xeshlash; kerak bo'lmagan shaxsiy ma'lumotni so'ramaslik |

### Xavf matritsasi

| Ehtimol \\ Ta'sir | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| **5** |  |  |  |  |  |
| **4** |  |  |  | R1 |  |
| **3** |  |  | R2 | R3, R4 |  |
| **2** |  |  |  |  | R5 |
| **1** |  |  |  |  |  |

## 4. Foydalanuvchi yo'riqnomasi (qoralama)

*Qoralama: tugmalar va sahifa nomlari prototip (5–7-laboratoriyalar) tayyor bo'lgach aniqlashtiriladi, skrinshotlar shunda qo'shiladi.*

### 4.1. O'quvchi uchun

**Ro'yxatdan o'tish va kirish**

1. Bosh sahifada «Ro'yxatdan o'tish» tugmasini bosing.
2. Email va kamida 8 belgili parolni kiriting.
3. «Yaratish» tugmasini bosing. Keyingi safar «Kirish» orqali email va parol bilan kirasiz.

**Kurs topish**

1. «Kurslar» sahifasini oching.
2. Qidiruv maydoniga kurs nomini yozing yoki toifani tanlang.
3. Kerakli kursni bosib, tavsif, darslar ro'yxati va narxni ko'ring.

**Kursga yozilish**

1. Kurs sahifasida «Kursga yozilish» tugmasini bosing.
2. To'lov oynasida ma'lumotlarni tasdiqlang.
3. To'lov muvaffaqiyatli bo'lsa, kurs «Mening kurslarim» bo'limida paydo bo'ladi.

**O'qish va progress**

1. «Mening kurslarim» dan kursni oching.
2. Darslarni ketma-ket ko'ring; har dars oxirida «Tugatildi» ni belgilang.
3. Kurs tepasida progress foizini kuzating.

**Test va sertifikat**

1. Barcha darslar tugagach, «Testni boshlash» tugmasini bosing.
2. Savollarga javob berib, «Topshirish» ni bosing.
3. Natija 60% va undan yuqori bo'lsa, sertifikat avtomatik beriladi. Past bo'lsa, testni qayta topshirishingiz mumkin.

### 4.2. O'qituvchi uchun

**Kurs yaratish**

1. O'qituvchi hisobi bilan kiring va «Yangi kurs» tugmasini bosing.
2. Nom, tavsif, toifa va narxni kiriting.
3. «Saqlash» ni bosing; kurs administrator tasdig'idan keyin katalogda ko'rinadi.

**Dars va test qo'shish**

1. Kurs sahifasida «Dars qo'shish» ni bosing, nom va kontent (matn yoki video havolasi) kiriting.
2. «Test qo'shish» orqali savol, javob variantlari va to'g'ri javobni belgilang.

### 4.3. Ko'p uchraydigan savollar

| Muammo | Yechim |
| --- | --- |
| Kirishda parol xato deb chiqmoqda | Parolni tekshiring; unutgan bo'lsangiz, ro'yxatdan qaytadan o'ting (MVPda parolni tiklash yo'q) |
| To'lov rad etildi | Ma'lumotlarni tekshirib, qayta urinib ko'ring; kurs faqat muvaffaqiyatli to'lovdan keyin ochiladi |
| Sertifikat berilmadi | Test natijasi 60% dan past bo'lgan; testni qayta topshiring |

## 5. Talablar izlanuvchanligi (traceability)

| User story | Talab | Use case |
| --- | --- | --- |
| US-01 | FR-01 | UC-01 (oldingi shart) |
| US-02, US-03 | FR-02, FR-03 | UC-01 |
| US-04 | FR-04 | UC-01 |
| US-05, US-06 | FR-05, FR-06 | UC-02 |
| US-07, US-08 | FR-07, FR-08 | UC-02 |
| US-09, US-10, US-11 | FR-09, FR-10, FR-11 | Keyingi use case lar |

## 6. Sifat nazorati

- [x] 11 ta funksional va 5 ta nofunksional talab yozilgan (minimum 8 va 4)
- [x] Har talab ID va qabul mezoniga ega
- [x] 3 ta rol va 2 ta asosiy use case ajratilgan
- [x] 5 ta xavf baholanib, matritsa tuzilgan
- [x] Foydalanuvchi yo'riqnomasi qoralamasi tayyor

## 7. Xulosa

Bu ishda EduPlatform uchun SRS v1 yozildi: 11 ta funksional va 5 ta nofunksional talab, 3 ta rol, 2 ta use case. 5 ta xavf baholanib, eng yuqori xavf sifatida vaqt yetishmasligi (R1) aniqlandi. Foydalanuvchi yo'riqnomasi qoralamasi keyingi laboratoriyalardagi prototiplar bilan to'ldiriladi.
