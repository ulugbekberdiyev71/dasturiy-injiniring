# 1-laboratoriya ishi. Loyihaviy taklif va jamoa shakllantirish

**Fan:** Dasturiy injiniringga kirish **Variant:** 03 — Onlayn kurslar platformasi **Mashg'ulot:** 1–2 **Topshiriladigan materiallar:** Project Charter, 5 savolli anketa, manfaatdor tomonlar xaritasi

## 1. Muammo va foydalanuvchi segmentini tavsiflash

**Muammo.** O'zbekistonda o'qish va kasbiy ko'nikmalarni oshirishni istaganlar ko'pincha tarqoq manbalarga tayanadi: Telegram kanallari, YouTube videolari, xorijiy platformalar va oflayn o'quv markazlari. Natijada: (1) kurslar sifatini baholash qiyin; (2) o'quvchi o'z progressini yagona joyda ko'ra olmaydi; (3) mahalliy to'lov usullari (Uzcard, Humo, Payme, Click) va o'zbek tilidagi kontent xorijiy platformalarda yetarli emas; (4) o'qituvchilar kursini sotish, baholash va o'quvchilar bilan aloqa qilish uchun alohida vositalarga muhtoj.

**Asosiy foydalanuvchi segmentlari.**

| Segment | Tavsif | Asosiy ehtiyoj |
| --- | --- | --- |
| Talaba-o'quvchi | 17–25 yoshli universitet talabalari | Arzon, o'zbek/rus/ingliz tilidagi, sertifikatli kurslar |
| Ishlayotgan mutaxassis | 25–40 yosh, malaka oshirish istagida | Moslashuvchan jadval, mobil qulaylik |
| O'qituvchi-muallif | Kurs yaratuvchi ekspert yoki o'quv markaz | Kurs joylash, topshiriqlar tekshirish, daromad hisoboti |
| Administrator/moderator | Platforma xodimi | Kontent sifati nazorati, to'lov va shikoyatlar |

**Birlamchi maqsadli auditoriya:** talaba-o'quvchi va o'qituvchi-muallif.

## 2. Mavjud 3 ta yechimni solishtirish

| Mezon | Coursera | Udemy | Stepik |
| --- | --- | --- | --- |
| Kontent tili | Asosan ingliz | Ko'p tilli, ammo o'zbekcha kam | Rus va ingliz, o'zbekcha kam |
| Mahalliy to'lov (Uzcard/Humo) | Cheklangan | Cheklangan | Cheklangan |
| Sertifikat | Bor (universitetlar bilan) | Bor (kurs yakuni) | Bor |
| O'qituvchi uchun kurs yaratish | Cheklangan (hamkorlar) | Ochiq | Ochiq |
| Mahalliy kontekstga moslik | Past | Past | O'rta |
| Asosiy kamchilik | Narx va til to'sig'i | Sifat nazoratining notekisligi | O'zbek bozoriga yo'naltirilmagan |

*Eslatma: jadval umumiy kuzatuvga asoslangan; topshirishdan oldin platformalarning joriy shartlarini o'zingiz tekshirib chiqing.*

**Xulosa:** mavjud platformalar o'zbek tili, mahalliy to'lov va mahalliy o'qituvchilar uchun qulay muhitni to'liq ta'minlamaydi. Bu loyiha uchun bozor bo'shlig'idir.

## 3. Qiymat taklifi (Value Proposition)

> Biz o'zbek tilida va mahalliy to'lov usullari bilan ishlaydigan onlayn kurslar platformasini taklif qilamiz: o'quvchi bir joyda kurs tanlaydi, to'laydi, o'qiydi, topshiriq topshiradi va sertifikat oladi; o'qituvchi esa kursini tez joylab, o'quvchilar progressini kuzatadi va daromadini ko'radi.

**O'quvchi uchun:** qulay narx, mobil moslik, progress kuzatuvi, sertifikat. **O'qituvchi uchun:** oson kurs yaratish, avtomatik test tekshiruvi, to'lov va statistika hisoboti. **Platforma uchun:** kontent moderatsiyasi va komissiya modeli.

## 4. Project Charter (Loyiha pasporti)

| Band | Mazmun |
| --- | --- |
| Loyiha nomi | EduPlatform — onlayn kurslar platformasi |
| Loyiha raqami | 03 |
| Loyiha rahbari | \[Ism-familiya\] |
| Boshlanish/tugash | Semestr boshi — yakuniy himoya |
| Biznes muammo | Sifatli, o'zbek tilidagi, mahalliy to'lov bilan ishlaydigan kurslar platformasi yo'qligi |
| Loyiha maqsadi | Semestr oxirigacha ishlaydigan MVP yaratish: kurslar katalogi, ro'yxatdan o'tish, kursga yozilish, video/matn darslar, test, progress, sertifikat |
| Muvaffaqiyat mezonlari | 1) MVP to'liq asosiy stsenariyni (ro'yxatdan o'tish → kursga yozilish → dars → test → sertifikat) bajaradi; 2) kamida 5 ta test kursi kiritiladi; 3) kamida 10 foydalanuvchi sinovdan o'tadi; 4) barcha test holatlarining 90% i muvaffaqiyatli |
| Qamrov (scope) ichida | Autentifikatsiya, kurslar katalogi va qidiruv, kursga yozilish, darslarni ko'rish, testlar, progress, sertifikat, o'qituvchi paneli, admin paneli (asosiy) |
| Qamrov tashqarisida | Haqiqiy to'lov shlyuzi integratsiyasi (MVPda imitatsiya), jonli video efir, mobil ilova, AI tavsiyalar |
| Texnologiyalar | HTML, CSS, JavaScript; boshlang'ich bosqichda localStorage/JSON; Git/GitHub; draw.io; Figma |
| Asosiy xavflar | Vaqt yetishmasligi; kontent tayyorlash qiyinligi; talablar o'zgarishi; jamoa a'zolari faolligi |
| Xavflarni kamaytirish | XP iteratsiyalari, haftalik ko'rik, kontentni namunaviy qisqa kurslar bilan cheklash |
| Taxminiy vaqt rejasi | 15 ta mavzu bo'yicha izchil: talablar → prototip V1–V3 → arxitektura → test → refaktoring → himoya |

### Jamoa rollari

| Rol | Mas'uliyat |
| --- | --- |
| Loyiha rahbari (Project Manager) | Reja, muddatlar, jamoa muvofiqlashtirish |
| Biznes tahlilchi | Talablar, foydalanuvchi tadqiqoti, anketa |
| UI/UX dizayner | Qog'oz va raqamli prototip |
| Dasturchi (Frontend/Logic) | MVP kodi, localStorage/JSON bilan ishlash |
| Test muhandisi (QA) | Test rejasi, test bayonnomasi |
| Hujjatlashtiruvchi / Git mas'uli | Hujjatlar, GitHub, commitlar |

*Individual ishda barcha rollar bir talaba tomonidan bajariladi; jamoa ishida ular taqsimlanadi.*

## 5. Foydalanuvchi tadqiqoti: 5 savolli anketa (intervyu)

**Maqsad:** onlayn kurslardan foydalanish odatlari va muammolarini aniqlash. **Respondentlar:** talabalar va kurs o'qituvchilari.

1. **Onlayn kurslarni qanchalik tez-tez ko'rasiz va qaysi platformalardan foydalanasiz?** (har hafta / oyiga bir necha marta / kamdan-kam / umuman ko'rmayman; platforma nomi)
2. **Onlayn kursni tanlashda siz uchun eng muhim omillar qaysilar?** (narx, til, o'qituvchi obro'si, sertifikat, davomiyligi, sharhlar — eng muhim 3 tasini belgilang)
3. **Onlayn kurslarda o'qiyotganda qanday qiyinchiliklarga duch kelgansiz?** (to'lov muammosi, til to'sig'i, motivatsiya yo'qligi, savollarga javob olmaslik, sifatsiz kontent va h.k.)
4. **Kurs to'lovini qaysi usulda qilishni qulay deb bilasiz?** (Uzcard/Humo, Payme/Click, bank o'tkazmasi, naqd/terminal) va kurs uchun o'rtacha qancha to'lashga tayyorsiz?
5. **Ideal onlayn kurslar platformasida qanday imkoniyat bo'lishini istardingiz?** (ochiq javob; masalan: mobil moslik, o'zbek tili, progress kuzatuvi, o'qituvchi bilan aloqa, sertifikat)

*O'qituvchilar uchun qo'shimcha savol:* kursingizni hozir qayerda va qanday sotasiz, qaysi jarayon eng ko'p vaqt oladi?

## 6. Manfaatdor tomonlar xaritasi (Stakeholder Map)

| Manfaatdor tomon | Rol | Manfaati | Ta'sir darajasi | Qiziqish darajasi | Strategiya |
| --- | --- | --- | --- | --- | --- |
| O'quvchilar (talabalar) | Asosiy foydalanuvchi | Qulay va arzon o'qish | O'rta | Yuqori | Doimiy fikr olish, sinov |
| O'qituvchilar/mualliflar | Kontent yaratuvchi | Daromad, auditoriya | Yuqori | Yuqori | Chuqur hamkorlik |
| Platforma administratori | Moderator | Sifat va xavfsizlik | Yuqori | Yuqori | Muntazam muvofiqlashtirish |
| Loyiha rahbari (fan o'qituvchisi) | Buyurtmachi/baholovchi | Talablarning bajarilishi | Yuqori | Yuqori | Muntazam hisobot |
| Ishlab chiqish jamoasi | Ijrochi | Sifatli MVP | Yuqori | Yuqori | Kundalik aloqa |
| To'lov tizimlari (Payme, Click, Uzcard/Humo) | Tashqi hamkor | Tranzaksiyalar | O'rta | Past | Xabardor qilib turish |
| Universitet/o'quv markazlar | Potensial hamkor | Talabalarni o'qitish | O'rta | O'rta | Ma'lumot berib turish |
| Davlat regulyatorlari | Tashqi nazorat | Ma'lumotlar himoyasi, qonuniylik | O'rta | Past | Talablarga rioya qilish |

**Ta'sir/qiziqish matritsasi (qisqacha):**

- **Yuqori ta'sir + yuqori qiziqish (chuqur hamkorlik):** o'qituvchilar, administrator, fan o'qituvchisi, jamoa.
- **Past ta'sir + yuqori qiziqish (xabardor qilib turish):** o'quvchilar.
- **Yuqori/o'rta ta'sir + past qiziqish (kuzatib borish):** to'lov tizimlari, regulyatorlar.
- **O'rta ta'sir + o'rta qiziqish:** universitet va o'quv markazlar.

## 7. Sifat nazorati (tekshiruv ro'yxati)

- [x] Muammo aniq va tekshiriladigan tarzda ifodalangan
- [x] Foydalanuvchi segmentlari aniqlangan
- [x] 3 ta mavjud yechim solishtirilgan
- [x] 5 savolli anketa tuzilgan
- [x] Qiymat taklifi asoslangan
- [x] Project Charter, jamoa rollari va manfaatdor tomonlar xaritasi tayyor

## 8. Xulosa

Bu laboratoriya ishida 3-variant — «Onlayn kurslar platformasi» bo'yicha muammo va foydalanuvchi segmenti aniqlandi, Coursera, Udemy va Stepik bilan solishtirish o'tkazildi, qiymat taklifi shakllantirildi, Project Charter va jamoa rollari belgilandi, 5 savolli anketa va manfaatdor tomonlar xaritasi tuzildi. Bu natijalar keyingi laboratoriyalarda (muammo tahlili, XP, talablar, prototiplar) asos bo'ladi.
