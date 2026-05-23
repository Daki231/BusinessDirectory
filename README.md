# 📱 Business Directory — Android Application

## 📌 Опис
Business Directory е Android мобилна апликација која претставува 
бизнис директориум за приказ на различни бизниси поделени по категории. 
Апликацијата овозможува внес, чување и пребарување на компании 
преку едноставен и интуитивен кориснички интерфејс.


## 👤 Автор
- Давид Стојчевски 102723 — индивидуална проектна задача
- Предмет: Развој на мобилни апликации
- Универзитет: УГД — Факултет за информатика

---

## 🛠️ Технологии и алатки

| Технологија | Опис |
|-------------|------|
| Android Studio | Развојна околина (IDE) |
| Java | Програмски јазик |
| Room (SQLite) | Локална база на податоци |
| ViewPager2 | Навигација меѓу табови со swipe |
| TabLayout | Приказ на категории |
| ListView | Приказ на листа на компании |
| Material Design | UI компоненти и стилизација |

---

## 🏗️ Архитектура на проектот
app/
├── model/
│   └── Company.java          ← Entity класа за Room база
├── database/
│   ├── AppDatabase.java      ← Room Database инстанца
│   └── CompanyDao.java       ← SQL queries (insert, select, search)
├── adapter/
│   ├── CompanyAdapter.java   ← Custom BaseAdapter за ListView
│   └── ViewPagerAdapter.java ← Adapter за ViewPager2
├── fragments/
│   └── CategoryFragment.java ← Фрагмент за секоја категорија
├── MainActivity.java         ← Главен екран со TabLayout
└── AddCompanyActivity.java   ← Екран за внес на компанија
---

## 📂 Функционалности

### 🏠 Главен екран
- **TabLayout** со 4 категории: Services, Fun, Industry, Education
- **Swipe** навигација меѓу табовите (лево-десно)
- **ListView** со приказ на компании по категорија
- Секоја компанија прикажува:
  - Икона (различна по категорија)
  - Назив на компанијата
  - Адреса
  - Телефон
  - Веб страна
- **Search поле** на дното за пребарување по назив

### ➕ Додавање компанија
- Клик на иконата горе десно отвора форма за внес
- Полиња за внес:
  - Назив
  - Адреса
  - Географска ширина и должина (Latitude/Longitude)
  - Контакт е-маил адреса
  - Телефон
  - Веб страна
  - Категорија (checkbox — можност за избор на повеќе категории)
- **SAVE** копче за зачувување во локална база
- Валидација — задолжителни полиња (назив и категорија)
- Стрелка за враќање горе лево

---

## 🗄️ База на податоци — Room (SQLite)

Апликацијата користи **Room** — официјална Android библиотека за 
локално складирање на податоци базирана на SQLite.

### Company Entity
| Поле | Тип | Опис |
|------|-----|------|
| id | int | Примарен клуч (autoGenerate) |
| name | String | Назив на компанијата |
| address | String | Адреса |
| latitude | double | Географска ширина |
| longitude | double | Географска должина |
| email | String | Контакт е-маил |
| phone | String | Телефон |
| website | String | Веб страна |
| category | String | Категорија (Services, Fun, Industry, Education) |

### DAO Queries
- `insert(Company)` — внес на нова компанија
- `getByCategory(category)` — земи компании по категорија
- `searchByCategory(category, search)` — пребарување по назив во категорија

---

## 📦 Dependencies

```groovy
// Room Database
implementation 'androidx.room:room-runtime:2.6.1'
annotationProcessor 'androidx.room:room-compiler:2.6.1'

// ViewPager2
implementation 'androidx.viewpager2:viewpager2:1.1.0'

// Material Design
implementation 'com.google.android.material:material:1.12.0'

// AppCompat
implementation 'androidx.appcompat:appcompat:1.6.1'
```

---

## 🚀 Инсталација и стартување

1. Клонирај го репозиториумот:
```bash
git clone https://github.com/tvoeto-ime/BusinessDirectory.git
```
2. Отвори го проектот во **Android Studio**
3. Почекај да заврши Gradle Sync
4. Стартувај на емулатор или физички уред (**▶ Run**)

---

## 📚 Референци
- [Android Room Documentation](https://developer.android.com/training/data-storage/room)
- [ViewPager2 Guide](https://developer.android.com/guide/navigation/navigation-swipe-view-2)
- [Material Design Components](https://material.io/components)
- [Room Beginner Tutorial](https://medium.freecodecamp.org/room-sqlite-beginner-tutorial-2e725e47bfab)
- [ListView Custom Adapter](https://www.journaldev.com/10416/android-listview-with-custom-adapter-example-tutorial)
- [Android TabLayout + ListView](https://www.androidhive.info/2012/05/android-combining-tab-layout-and-list-view/)
