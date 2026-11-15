# 3-laboratoriya ishi. XP metodologiyasi

**Fan:** Dasturiy injiniringga kirish **Variant:** 03 — Onlayn kurslar platformasi **Mashg'ulot:** 5–6 **Topshiriladigan materiallar:** Product backlog, iteration plan, TDD protokoli

## 1. Product backlog: user storylar

Backlog «EduPlatform» MVP uchun tuzildi. Har bir hikoya «Rol sifatida men ... xohlayman, shunda ...» shaklida yozilgan. Ball — nisbiy murakkablik (1, 2, 3, 5, 8 shkalasi).

| ID | User story | Ball | Prioritet | Iteratsiya |
| --- | --- | --- | --- | --- |
| US-01 | O'quvchi sifatida men email va parol bilan ro'yxatdan o'tib, tizimga kirishni xohlayman, shunda progressim saqlanadi | 3 | Yuqori | 1 |
| US-02 | O'quvchi sifatida men kurslar katalogini ko'rib, nom va toifa bo'yicha qidirishni xohlayman, shunda kerakli kursni tez topaman | 5 | Yuqori | 1 |
| US-03 | O'quvchi sifatida men kurs sahifasida tavsif, darslar ro'yxati va narxni ko'rishni xohlayman, shunda yozilishdan oldin qaror qabul qilaman | 2 | Yuqori | 1 |
| US-04 | O'quvchi sifatida men kursga to'lov qilib yozilishni xohlayman, shunda darslarga darhol kira olaman | 5 | Yuqori | 1 |
| US-05 | O'quvchi sifatida men yozilgan kursimning darslarini ketma-ket ko'rishni xohlayman, shunda o'qishni boshlayman | 5 | Yuqori | 1 |
| US-06 | O'quvchi sifatida men darsni tugatilgan deb belgilab, kurs progressini ko'rishni xohlayman, shunda qayerda to'xtaganimni bilaman | 3 | Yuqori | 2 |
| US-07 | O'quvchi sifatida men kurs testini topshirib, natijani darhol olishni xohlayman, shunda bilimimni tekshiraman | 5 | Yuqori | 2 |
| US-08 | O'quvchi sifatida men testdan o'tgach sertifikat olishni xohlayman, shunda yutug'imni tasdiqlay olaman | 3 | O'rta | 2 |
| US-09 | O'qituvchi sifatida men yangi kurs yaratib, tavsif va narx kiritishni xohlayman, shunda uni sotuvga chiqaraman | 5 | Yuqori | 2 |
| US-10 | O'qituvchi sifatida men kursga dars va test savollarini qo'shishni xohlayman, shunda o'quvchilar o'qiy oladi | 5 | Yuqori | 2 |
| US-11 | Administrator sifatida men yangi kurslarni ko'rib chiqib tasdiqlashni xohlayman, shunda katalogda faqat sifatli kurslar bo'ladi | 3 | O'rta | Keyingi |
| US-12 | O'quvchi sifatida men tugatgan kursimga sharh va reyting qoldirishni xohlayman, shunda boshqalar tanlashda yordam oladi | 2 | Past | Keyingi |

**Jami:** 46 ball. 1-iteratsiya: 20 ball, 2-iteratsiya: 21 ball, qolgan 5 ball keyingi bosqichga qoldirildi.

### INVEST tekshiruvi

| Mezon | Ma'nosi | Loyihada qanday ta'minlangan |
| --- | --- | --- |
| **I**ndependent (mustaqil) | Hikoyalar bir-biriga kam bog'liq | Har hikoya alohida tayyor bo'ladi; US-04 uchun kurslar vaqtincha JSON fayldan olinadi, shuning uchun US-09 ni kutish shart emas |
| **N**egotiable (muzokara qilinadigan) | Tafsilotlar kelishiladi | Hikoyada «nima» yozilgan, «qanday» emas (masalan, to'lov usuli keyinroq aniqlanadi) |
| **V**aluable (qimmatli) | Foydalanuvchiga foyda beradi | Har hikoyada «soddaki» qismi foydani ko'rsatadi |
| **E**stimable (baholanadigan) | Hajmini baholash mumkin | Barcha hikoyalar planning poker bilan baholangan |
| **S**mall (kichik) | Bir iteratsiyaga sig'adi | Eng katta hikoya 5 ball; kattalari bo'lingan (masalan, kurs yaratish va dars qo'shish ajratilgan) |
| **T**estable (tekshiriladigan) | Qabul mezoni bor | Quyida Given-When-Then shaklida yozilgan |

### Qabul mezonlari (asosiy hikoyalar)

**US-04. Kursga to'lov qilib yozilish**

- *Given:* o'quvchi tizimga kirgan va kurs narxi 0 dan katta.
- *When:* u «To'lov qilish» tugmasini bosib, to'lovni tasdiqlaydi.
- *Then:* kurs uning «Mening kurslarim» ro'yxatida paydo bo'ladi va darslar ochiladi.
- *Given:* to'lov rad etilgan.
- *When:* tizim xato qaytaradi.
- *Then:* o'quvchi kursga yozilmaydi va xato xabarini ko'radi.

**US-07. Testni topshirish va avtomatik baho**

- *Given:* o'quvchi kursning barcha savollariga javob bergan.
- *When:* u «Topshirish» tugmasini bosadi.
- *Then:* tizim to'g'ri javoblar foizini hisoblaydi va natijani ko'rsatadi.
- *Given:* foiz 60 va undan yuqori.
- *When:* natija saqlanadi.
- *Then:* test «o'tdi» deb belgilanadi va sertifikat (US-08) ochiladi.

**US-06. Progress**

- *Given:* kursda 10 ta dars bor va o'quvchi 4 tasini tugatgan.
- *When:* u kurs sahifasini ochadi.
- *Then:* progress 40% ko'rsatiladi.

## 2. Planning Game

Planning Game XP da mijoz va dasturchilar o'rtasida ikki bosqichda o'tadi. Individual loyihada mijoz roli (nima muhim ekanini hal qiladi) va dasturchi roli (baholaydi va bajaradi) bir talabada birlashadi, shuning uchun qarorlar yozib qo'yiladi.

| Qadam | Kim qiladi | Natija |
| --- | --- | --- |
| 1. Hikoyalarni yig'ish | Mijoz roli | 12 ta user story kartochkasi |
| 2. Baholash (planning poker, 1–2–3–5–8) | Dasturchi roli | Har hikoyaga ball; 8 dan katta hikoya bo'linadi |
| 3. Prioritetlash | Mijoz roli | Yuqori, o'rta, past tartib (biznes qiymati bo'yicha) |
| 4. Iteratsiya sig'imini aniqlash | Dasturchi roli | Taxminiy tezlik (velocity): iteratsiyada 20–22 ball |
| 5. Iteratsiya tanlash | Ikkalasi | Tezlikka sig'adigan hikoyalar tanlanadi |
| 6. Iteratsiya oxirida tahlil | Ikkalasi | Haqiqiy tezlik yozib qo'yiladi, keyingi reja tuzatiladi |

*Tezlik taxminiy; 1-iteratsiya tugagach haqiqiy qiymat bilan almashtiring.*

## 3. Iteratsiya rejasi (2 ta iteratsiya)

Iteratsiya davomiyligi: 2 hafta. Har iteratsiya ishlaydigan demo bilan tugaydi.

| Band | 1-iteratsiya | 2-iteratsiya |
| --- | --- | --- |
| Maqsad | O'quvchi kursni topib, yozilib, dars ko'ra oladi | O'quvchi o'qib, test topshirib, sertifikat oladi; o'qituvchi kurs qo'sha oladi |
| Hikoyalar | US-01, US-02, US-03, US-04, US-05 | US-06, US-07, US-08, US-09, US-10 |
| Ball | 20 | 21 |
| Asosiy vazifalar | Ro'yxatdan o'tish formasi; kurslar JSON ma'lumoti; katalog va qidiruv; kurs sahifasi; to'lov imitatsiyasi; darslar sahifasi | Progress hisobi; test mantig'i va avtomatik baho; sertifikat sahifasi; kurs yaratish formasi; dars va savol qo'shish |
| Demo natijasi | Foydalanuvchi to'liq yo'lni bosib o'tadi: kirish → qidirish → yozilish → dars ko'rish | To'liq stsenariy: yozilish → o'qish → test → sertifikat, o'qituvchi tomoni bilan |
| Tugallanish mezoni | Barcha qabul mezonlari bajarilgan, testlar o'tgan, kod GitHub'ga commit qilingan | Xuddi shunday + 1-iteratsiya regressiya testlari o'tgan |
| Asosiy xavf | To'lov imitatsiyasi haqiqiy to'lovdan farq qiladi | Vaqt yetishmasligi (ball ko'p) |
| Xavfni kamaytirish | To'lov alohida modulga ajratiladi, keyin almashtirish oson | US-12 va US-11 allaqachon keyingi bosqichga olingan; zarur bo'lsa US-08 ning dizayni soddalashtiriladi |

**Iteratsiya oxiridagi retrospektiva savollari:** nima yaxshi ketdi, nima to'sqinlik qildi, keyingi iteratsiyada nimani o'zgartiramiz.

## 4. TDD protokoli

TDD tsikli: **Red** (muvaffaqiyatsiz test yoziladi) → **Green** (testni o'tkazadigan eng sodda kod) → **Refactor** (tozalash, testlar o'tishda qoladi).

Namuna sifatida **US-07** ning asosiy funksiyasi tanlandi: `gradeTest(questions, answers)` testni baholaydi. Texnologiya: JavaScript va Jest.

### 1-tsikl: hamma javob to'g'ri

**Red.** Test yoziladi, funksiya hali yo'q:

```js
test("barcha javoblar to'g'ri bo'lsa 100% qaytaradi", () => {
  const questions = [{ id: 1, correct: 'b' }, { id: 2, correct: 'a' }];
  const answers = { 1: 'b', 2: 'a' };
  expect(gradeTest(questions, answers).percent).toBe(100);
});
```

Kutilgan natija: **FAIL** (`gradeTest is not defined`).

**Green.** Testni o'tkazadigan eng sodda kod:

```js
function gradeTest(questions, answers) {
  return { percent: 100 };
}
```

Kutilgan natija: **PASS**.

### 2-tsikl: qisman to'g'ri javob

**Red.**

```js
test("ikki savoldan biri to'g'ri bo'lsa 50% qaytaradi", () => {
  const questions = [{ id: 1, correct: 'b' }, { id: 2, correct: 'a' }];
  const answers = { 1: 'b', 2: 'c' };
  expect(gradeTest(questions, answers).percent).toBe(50);
});
```

Kutilgan natija: **FAIL** (100 qaytdi, 50 kutilgan edi).

**Green.** Haqiqiy hisob:

```js
function gradeTest(questions, answers) {
  const correct = questions.filter(q => answers[q.id] === q.correct).length;
  return { percent: (correct / questions.length) * 100 };
}
```

Kutilgan natija: ikkala test **PASS**.

### 3-tsikl: o'tish chegarasi

**Red.**

```js
test("60% va undan yuqori bo'lsa test o'tgan hisoblanadi", () => {
  const questions = [
    { id: 1, correct: 'a' }, { id: 2, correct: 'a' }, { id: 3, correct: 'a' },
    { id: 4, correct: 'a' }, { id: 5, correct: 'a' }
  ];
  const answers = { 1: 'a', 2: 'a', 3: 'a', 4: 'b', 5: 'b' };
  expect(gradeTest(questions, answers).passed).toBe(true);
});
```

Kutilgan natija: **FAIL** (`passed` hali yo'q).

**Green va Refactor.** `passed` qo'shiladi, chegara o'zgarmas qiymatga chiqariladi:

```js
const PASS_PERCENT = 60;

function gradeTest(questions, answers) {
  const correct = questions.filter(q => answers[q.id] === q.correct).length;
  const percent = (correct / questions.length) * 100;
  return { percent, passed: percent >= PASS_PERCENT };
}
```

Kutilgan natija: uchala test **PASS**.

### TDD dalillari jadvali

Har tsikldan keyin natijani Jest chiqishi bilan to'ldiring va commit qiling.

| Tsikl | Red (commit xabari) | Green (commit xabari) | Refactor | Skrinshot / log |
| --- | --- | --- | --- | --- |
| 1 | `test: gradeTest 100%` | `feat: gradeTest minimal` | — | *qo'shing* |
| 2 | `test: gradeTest 50%` | `feat: gradeTest hisoblash` | — | *qo'shing* |
| 3 | `test: o'tish chegarasi` | `feat: passed maydoni` | `refactor: PASS_PERCENT` | *qo'shing* |

Boshqa hikoyalar uchun ham shu tartibda TDD qo'llanadi: US-06 (progress foizi) va US-04 (to'lov muvaffaqiyatsiz bo'lganda yozilmaslik).

## 5. Pair programming dalillari

**Qoidalar:** bir kompyuterda ikki rol: **Driver** (kod yozadi) va **Navigator** (kodni kuzatadi, xato va keyingi qadamni aytadi). Rollar har 25 daqiqada almashadi. Juftlikda bajariladigan hikoyalar: **US-04** (to'lov) va **US-07** (test baholash), chunki ular xatoga eng moyil.

Individual ishda juftlik sifatida guruhdoshingiz yoki o'qituvchi/ustoz bilan ishlang.

| Sana | Juftlik (Driver / Navigator) | Hikoya va vazifa | Rol almashinuvi | Commit havolasi |
| --- | --- | --- | --- | --- |
| *sana* | *ism / ism* | US-04, to'lov funksiyasi | har 25 daqiqada | *GitHub commit* |
| *sana* | *ism / ism* | US-07, `gradeTest` | har 25 daqiqada | *GitHub commit* |

*Jadvalni haqiqiy sessiyalardan keyin to'ldiring: dalil bo'lishi uchun commit xabarida `Pair:` va ikkala ism yozilsin.*

## 6. XP amaliyotlari: loyihadagi izlar

| XP amaliyoti | Loyihada qanday qo'llanadi | Dalil (GitHub) |
| --- | --- | --- |
| Planning Game | Backlog va iteratsiya rejasi | `lab-03/` papkasidagi shu hujjat |
| Small releases | 2 haftalik iteratsiyalar, har biri demo bilan | Iteratsiya oxiridagi `tag` (masalan, `v0.1`, `v0.2`) |
| Test-first (TDD) | Avval test, keyin kod | Red/Green commitlar tartibi |
| Pair programming | Murakkab hikoyalar juftlikda | `Pair:` belgili commitlar |
| Simple design | Faqat joriy hikoyaga kerak kod yoziladi | Kichik, tushunarli funksiyalar |
| Refactoring | Testlar yashil bo'lganda tozalash | `refactor:` commitlar |
| Continuous integration | Kichik o'zgarishlar tez-tez commit qilinadi | Commit tarixi |
| Collective ownership | Kod hamma uchun ochiq, README da qoidalar | Repozitoriy va README |

## 7. Sifat nazorati

- [x] User storylar INVEST bo'yicha yozilgan va qabul mezonlari bor
- [x] Planning Game qadamlari tavsiflangan
- [x] 2 ta iteratsiya rejalashtirilgan
- [x] TDD protokoli (Red, Green, Refactor) kod bilan berilgan
- [x] Pair programming qoidalari va dalil jadvali tayyor
- [ ] Testlar Jest bilan ishga tushirilib, natijalar va commitlar GitHub'ga qo'shilgan (XP amaliyoti iz qoldirishi kerak)

## 8. Xulosa

Bu ishda EduPlatform loyihasi uchun 12 ta user story INVEST bo'yicha yozildi, Planning Game orqali baholanib, ikki iteratsiyaga taqsimlandi. TDD protokoli bilan `gradeTest` funksiyasi misolida Red-Green-Refactor tsikli ko'rsatildi, pair programming uchun qoidalar va dalil jadvali tayyorlandi. Keyingi laboratoriyada bu backlog talablar va foydalanuvchi yo'riqnomasi uchun asos bo'ladi.
