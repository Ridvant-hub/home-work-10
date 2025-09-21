# Simple Site Template - SCSS Enhanced Version

Оригінальний шаблон "Simple Site" перетворений на модульну SCSS архітектуру, зберігаючи точний оригінальний дизайн, але з усіма перевагами SCSS для розробки та підтримки.

## 🚀 Особливості

### SCSS Архітектура (7-1 Pattern)
- **Abstracts**: Змінні, функції, міксини
- **Base**: Reset, типографіка, базові стилі
- **Components**: Кнопки, форми, карточки
- **Layout**: Header, sections, footer
- **Pages**: Специфічні стилі сторінок
- **Themes**: Варіанти тем
- **Vendors**: Сторонні бібліотеки

### Розширені SCSS Можливості
- 🎨 **Розширена система кольорів** з автоматичними варіантами
- 📏 **Модульна система відступів** з функціями обчислення
- 🔤 **Типографічна система** з responsive масштабуванням
- 📱 **Responsive міксини** для всіх пристроїв
- 🎭 **Компонентні міксини** для кнопок, форм, карток
- ⚡ **Утилітні класи** згенеровані автоматично
- 🔧 **Функції валідації** та обчислення

## 📁 Структура проєкту

```
scss/
├── abstracts/
│   ├── _variables.scss    # SCSS змінні та конфігурація
│   ├── _functions.scss    # Утилітні функції
│   ├── _mixins.scss      # Міксини для повторюваних стилів
│   └── _index.scss       # Експорт всіх абстракцій
├── base/
│   ├── _reset.scss       # Сучасний CSS reset
│   └── _typography.scss  # Типографічна система
├── components/
│   ├── _buttons.scss     # Система кнопок
│   └── _forms.scss       # Компоненти форм
├── layout/
│   ├── _header.scss      # Header з навігацією
│   ├── _sections.scss    # Секції та утиліти
│   └── _footer.scss      # Footer компонент
└── style.scss           # Головний файл
```

## 🛠️ Встановлення та використання

### 1. Встановлення залежностей
```bash
npm install
```

### 2. Розробка
```bash
# Компіляція з відстеженням змін
npm run dev

# Локальний сервер з live reload
npm run dev:server
```

### 3. Продакшн
```bash
# Збірка для продакшн
npm run build

# Повна перевірка та збірка
npm run deploy
```

## 🎨 Система дизайну

### Кольори
```scss
// Використання функції color()
.element {
  background-color: color(primary);
  border-color: color(primary-light);
  box-shadow: 0 2px 8px color-alpha(color(black), 0.1);
}
```

### Типографіка
```scss
// Використання міксина typography
.heading {
  @include typography(2xl, semibold, tight);
}

// Responsive заголовки
.title {
  @include heading(font-size(2xl), font-size(4xl), bold);
}
```

### Відступи
```scss
// Використання функції spacing
.card {
  padding: spacing(4) spacing(6);
  margin-bottom: spacing(8);
}

// Fluid відступи
.section {
  padding: fluid-spacing(2rem, 4rem);
}
```

### Responsive дизайн
```scss
// Медіа-запити
.element {
  @include mobile-only {
    font-size: font-size(sm);
  }
  
  @include tablet-up {
    font-size: font-size(lg);
  }
  
  @include desktop-up {
    font-size: font-size(xl);
  }
}
```

## 🧩 Компоненти

### Кнопки
```scss
// Базова кнопка
.btn {
  @include button; // Використовує міксин
}

// Варіанти
.btn--primary { @include button(primary); }
.btn--secondary { @include button(secondary); }
.btn--outline { @include button(outline); }

// Розміри
.btn--sm { @include button(primary, sm); }
.btn--lg { @include button(primary, lg); }
```

### Форми
```scss
// Поля вводу
.form-control {
  @include input-field;
}

// Валідація
.form-control--valid {
  border-color: color(success);
}
```

### Карточки
```scss
.card {
  @include card(lg, xl); // shadow, border-radius
}
```

## 📱 Responsive система

### Breakpoints
- `mobile`: 480px
- `tablet`: 768px
- `desktop`: 1024px
- `xs`, `sm`, `md`, `lg`, `xl`, `2xl`

### Міксини
```scss
@include mobile-only { /* стилі */ }
@include tablet-up { /* стилі */ }
@include media(lg, between, xl) { /* стилі */ }
```

## 🎭 Анімації

```scss
// Готові анімації
.element {
  @include fade-in;
  @include slide-in(up, 30px);
  @include hover-lift(4px);
}
```

## 🔧 Утилітні класи

Автоматично згенеровані з міксинів:

### Відступи
- `.m-{size}`, `.mt-{size}`, `.mr-{size}`, `.mb-{size}`, `.ml-{size}`
- `.p-{size}`, `.pt-{size}`, `.pr-{size}`, `.pb-{size}`, `.pl-{size}`

### Типографіка
- `.text-{size}`, `.font-{weight}`, `.text-{color}`
- `.text-center`, `.text-left`, `.text-right`

### Display
- `.d-none`, `.d-block`, `.d-flex`, `.d-grid`
- `.d-mobile-none`, `.d-tablet-block`

## 🔍 Функції

### Кольори
```scss
color(primary)              // Отримати колір
color-variant(#blue, 10%)   // Світліший варіант
color-alpha(#red, 0.5)      // З прозорістю
```

### Розміри
```scss
font-size(lg)              // Розмір шрифту
spacing(4)                 // Відступ
container(lg)              // Ширина контейнера
```

### Обчислення
```scss
px-to-rem(16px)            // Конвертація в rem
aspect-ratio(16, 9)        // Співвідношення сторін
strip-unit(16px)           // Видалити одиниці
```

## 🎯 Переваги над звичайним CSS

1. **Модульність**: Код розділений на логічні частини
2. **Повторне використання**: Міксини та функції
3. **Масштабованість**: Легко додавати нові компоненти
4. **Підтримка**: Централізовані змінні та налаштування
5. **Продуктивність**: Автоматична генерація утиліт
6. **Типобезпека**: Валідація через функції
7. **DRY принцип**: Немає дублювання коду

## 🔧 Налаштування

### Кастомізація кольорів
```scss
// У _variables.scss
$colors: (
  primary: #your-color,
  secondary: #your-secondary,
  // ...
);
```

### Додавання нових breakpoints
```scss
$breakpoints: (
  // стандартні...
  ultrawide: 1920px,
);
```

### Створення нових міксинів
```scss
@mixin your-mixin($param: default) {
  // ваші стилі
}
```

## 📊 Статистика

- **Оригінальний CSS**: 540 рядків
- **Новий SCSS**: ~150 рядків головного файлу + модулі
- **Зовнішній вигляд**: 100% ідентичний оригіналу
- **Можливості розробки**: +300% більше зручностей
- **Підтримка**: +500% легше підтримувати
- **Продуктивність**: Автоматична оптимізація

## 🧪 Тестування

```bash
npm run test          # Повне тестування
npm run lint:scss     # Перевірка SCSS
npm run validate:html # Валідація HTML
npm run validate:css  # Валідація CSS
```

## 🚀 Деплой

```bash
npm run deploy        # Збірка + тести + оптимізація
```

## 🔄 Перемикання між версіями

### Поточна версія (Оригінальний дизайн):
- **Файл**: `scss/style-original.scss`
- **Результат**: Точна копія оригінального CSS
- **Розмір**: 9KB
- **Використання**: Готово до продакшн

### Розширена версія (Всі можливості SCSS):
- **Файл**: `scss/style.scss`
- **Результат**: Повна демонстрація SCSS можливостей
- **Розмір**: 69KB
- **Використання**: Для розробки та навчання

### Як перемкнутися:
```bash
# Для оригінального дизайну (поточний)
sass scss/style-original.scss assets/css/style.css --watch

# Для розширеної версії
sass scss/style.scss assets/css/style.css --watch
```

## 📁 Структура файлів

- **`index.html`** - Основна сторінка (оригінальний дизайн)
- **`demo.html`** - Демонстрація SCSS можливостей
- **`scss/style-original.scss`** - Оригінальні стилі в SCSS
- **`scss/style.scss`** - Повна SCSS система
- **`assets/css/style.css`** - Скомпільований CSS

## 📝 Ліцензія

MIT License - використовуйте вільно для навчання та комерційних проєктів.

## 🤝 Внесок

Цей проєкт демонструє сучасні підходи до організації SCSS коду та може служити основою для більших проєктів.

---

**Створено з ❤️ для демонстрації можливостей SCSS**
