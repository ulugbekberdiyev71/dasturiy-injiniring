# 2-laboratoriya ishi. Muammo va loyiha tahlili

**Fan:** Dasturiy injiniringga kirish **Variant:** 03 — Onlayn kurslar platformasi **Mashg'ulot:** 3–4 **Topshiriladigan materiallar:** AS-IS/TO-BE diagramma, muammo reyestri, KPI jadvali

## 1. Manfaatdor tomonlar (5 ta)

| № | Manfaatdor tomon | Roli | Asosiy ehtiyoji | Hozirgi og'riq nuqtasi |
| --- | --- | --- | --- | --- |
| 1 | O'quvchi (talaba, mutaxassis) | Kursda o'qiydi | Qulay to'lov, bir joyda o'qish, sertifikat | Kurslar tarqoq, to'lovdan keyin kursga kirish kechikadi |
| 2 | O'qituvchi-muallif | Kurs yaratadi va sotadi | Kursni tez joylash, daromad, o'quvchilarni kuzatish | To'lov va topshiriqlar qo'lda boshqariladi |
| 3 | Platforma administratori | Kontent va foydalanuvchilarni nazorat qiladi | Sifat nazorati, shikoyatlarni hal qilish | Yagona nazorat vositasi va sifat mezoni yo'q |
| 4 | To'lov tizimi (Uzcard, Humo, Payme, Click) | Tranzaksiyalarni amalga oshiradi | Xavfsiz va avtomatik to'lov | Kurslar uchun platforma bilan integratsiya yo'q |
| 5 | Universitet / o'quv markaz (hamkor) | Talabalarga kurslarni tavsiya qiladi | Talabalar progressini ko'rish, sifatli kontent | Natijalarni kuzatish imkoniyati yo'q |

## 2. AS-IS jarayon (joriy holat)

Hozirgi holatda o'quvchi kursni Telegram, Google va tanishlar orqali topadi, to'lovni kartaga o'tkazma bilan qiladi, o'qituvchi esa har bir chekni qo'lda tekshiradi.

&#91;embedded content: AS-IS jarayon · 6 qadam, 1 asosiy to'siq\]

Jarayon ketma-ket qo'lda bajariladi; 4-qadam (chekni qo'lda tasdiqlash) kursga kirishni kechiktiradi va boshqa qadamlarni to'xtatib turadi.

## 3. Muammolar reyestri va ustuvorlash

Ball = Ta'sir (1–5) × Chastota (1–5). Simptom — ko'rinadigan oqibat, sabab — uni keltirib chiqargan holat; ular alohida ustunlarda ko'rsatildi.

| № | Muammo (simptom) | Sabab | Ta'sir | Chastota | Ball | Ustuvorlik |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | To'lovdan keyin kursga kirish kechikadi | To'lov platformaga ulanmagan, chek qo'lda tekshiriladi | 5 | 5 | 25 | Yuqori |
| 2 | O'quvchi qayerda to'xtaganini ko'rmaydi | Darslar Telegram/Drive'da, progress yozilmaydi | 4 | 5 | 20 | Yuqori |
| 3 | Yaxshi kursni tanlash qiyin | Yagona katalog, reyting va sharhlar tizimi yo'q | 4 | 4 | 16 | O'rta |
| 4 | O'qituvchi vaqti tekshirishga ketadi | Test va topshiriqlar avtomatlashtirilmagan | 3 | 5 | 15 | O'rta |
| 5 | Sertifikat kech beriladi, haqiqiyligini tekshirib bo'lmaydi | Sertifikat raqami va tekshiruv tizimi yo'q | 3 | 3 | 9 | Past |

## 4. Ildiz sabab: 5 Why (1-muammo bo'yicha)

**Simptom:** to'lovdan keyin o'quvchi kursga kirish uchun kutadi va shikoyat qiladi.

1. **Nega kursga kirish kechikadi?** Chunki o'qituvchi to'lov chekini qo'lda tekshiradi.
2. **Nega qo'lda tekshiradi?** Chunki to'lov tizimi kursga kirish bilan bog'lanmagan, o'quvchi kartaga o'tkazma qiladi.
3. **Nega bog'lanmagan?** Chunki kurslar yagona platformada emas, Telegram va Drive'da tarqoq tarqatiladi.
4. **Nega tarqoq?** Chunki o'qituvchida kurs joylash, sotish va kirishni boshqarish uchun qulay vosita yo'q.
5. **Nega vosita yo'q?** Chunki mahalliy to'lov usullari bilan ishlaydigan, o'zbek tilidagi yagona kurslar platformasi mavjud emas.

**Ildiz sabab:** kurs, to'lov, kirish va progress ma'lumotlari bitta tizimda birlashtirilmagan.

## 5. TO-BE jarayon (kelajakdagi holat)

Taklif etilayotgan platformada barcha bosqichlar bitta tizimda bajariladi. MVP bosqichida to'lov imitatsiya qilinadi, haqiqiy to'lov shlyuzi keyingi bosqichga qoldiriladi.

&#91;embedded content: TO-BE jarayon · 6 qadam, avtomatik yozilish\]

To'lov tasdig'i kelishi bilan o'quvchi kursga avtomatik yoziladi, qo'lda tekshirish qadami olib tashlanadi.

**TO-BE qaysi muammoni hal qiladi:**

- **1-muammo (kechikish):** to'lov tasdig'i kelgach, kursga yozilish avtomatik bajariladi.
- **2-muammo (progress):** har bir dars va test natijasi platformada yoziladi, o'quvchi progressni ko'radi.
- **3-muammo (tanlash):** yagona katalog, qidiruv, reyting va sharhlar.
- **4-muammo (tekshirish):** testlar avtomatik tekshiriladi, o'qituvchi faqat murakkab topshiriqlarni ko'radi.
- **5-muammo (sertifikat):** test natijasiga ko'ra avtomatik va noyob raqam bilan beriladi.

## 6. Muvaffaqiyat KPI jadvali

| № | KPI | Formula / ta'rif | Hozirgi (AS-IS) | Maqsad (TO-BE) | O'lchash usuli |
| --- | --- | --- | --- | --- | --- |
| 1 | Kursga yozilish vaqti | To'lov boshlanishidan kursga kirishgacha o'tgan vaqt | 1-laboratoriya anketasi bilan aniqlanadi | ≤ 5 daqiqa | Tizim jurnali (vaqt belgisi) |
| 2 | Kursni tugatish ulushi | Tugatganlar / yozilganlar × 100% | Hisob yuritilmaydi, anketa bilan baholanadi | ≥ 60% | Progress ma'lumotlari |
| 3 | Foydalanuvchi qoniqishi | O'rtacha baho (1–5) | Anketa bilan aniqlanadi | ≥ 4,0 | Sinov so'rovnomasi (kamida 10 foydalanuvchi) |

*Maqsad qiymatlari taklifiy; AS-IS qiymatlarni o'zingiz o'tkazgan anketa natijalari bilan to'ldiring.*

## 7. Sifat nazorati

- [x] Sabab va simptom alohida ko'rsatilgan
- [x] 5 ta manfaatdor tomon belgilangan
- [x] AS-IS va TO-BE jarayonlar diagramma bilan berilgan
- [x] 5 ta muammo ustuvorlangan (Ta'sir × Chastota)
- [x] Ildiz sabab 5 Why usuli bilan aniqlangan
- [x] 3 ta KPI belgilangan

## 8. Xulosa

Bu ishda onlayn kurslar platformasining joriy jarayoni (AS-IS) tahlil qilindi, asosiy muammo to'lovni qo'lda tasdiqlash va ma'lumotlarning tarqoqligi ekani aniqlandi. Ildiz sabab sifatida yagona integratsiyalangan platforma yo'qligi topildi. TO-BE jarayon va KPI lar keyingi laboratoriyalarda talablar va prototiplar uchun asos bo'ladi.
