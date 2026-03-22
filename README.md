# Custom Slider Component

A lightweight, customizable slider component for web projects. Features include:
- **Touch support** – swipe gestures for mobile devices
- **Keyboard navigation** – arrow keys support for accessibility
- **Configurable** – control how many slides to scroll at once
- **Easy customization** – customize sizes, colors, and spacing via CSS

Переиспользуемый компонент слайдера для веб-проектов.

## Подключение

### 1. Скопируйте файлы компонента в ваш проект:
```
your-project/
├── slider-component/
│   ├── slider-component.css
│   └── slider-component.js
```

### 2. В HTML файле подключите CSS в `<head>`:
```html
<link rel="stylesheet" href="slider-component/slider-component.css">
```

### 3. Добавьте HTML разметку слайдера:
```html
<div class="slider" data-slides-to-scroll="3" tabindex="0">
  <button class="slider-btn-prev" aria-label="Предыдущий"><span>&#8249;</span></button>
  <button class="slider-btn-next" aria-label="Следующий"><span>&#8250;</span></button>
  
  <div class="slider-viewport">
    <div class="slider-track">
      <div class="slider-slide">
        <div class="slide-image"><img src="image1.jpg" alt="..."></div>
        <div class="slide-text"><h3>Заголовок</h3><p>Описание</p></div>
      </div>
      <!-- Повторите для каждого слайда -->
    </div>
  </div>
</div>
```

### 4. Подключите JS перед `</body>`:
```html
<script src="slider-component/slider-component.js"></script>
```

## Настройки

### data-slides-to-scroll
Количество слайдов для прокрутки за один раз:
```html
<div class="slider" data-slides-to-scroll="3">
```

## Кастомизация

### Изменение размера слайда:
```css
.slider-slide {
  width: 400px;  /* Ваша ширина */
  height: 400px; /* Ваша высота */
}
```

### Изменение цвета стрелок:
```css
.slider-btn-prev,
.slider-btn-next {
  background: rgba(0, 123, 255, 0.9); /* Ваш цвет */
}
```

### Изменение отступа между слайдами:
```css
.slider-track {
  gap: 20px; /* Ваш отступ */
}
```

## Структура слайда

```html
<div class="slider-slide">
  <div class="slide-image">
    <img src="..." alt="...">
  </div>
  <div class="slide-text">
    <h3>Заголовок</h3>
    <p>Описание (обрезается до 2 строк)</p>
  </div>
</div>
```

##  Доступность

- `tabindex="0"` — позволяет фокусироваться на слайдере
- Стрелки реагируют на клавиши ← →
- `aria-label` для кнопок

## Поддержка свайпов

Компонент поддерживает свайпы на тач-устройствах.

## Инициализация

Слайдер инициализируется автоматически после загрузки страницы.

Для ручной инициализации:
```javascript
// Инициализировать все слайдеры
SliderComponent.initAll();

// Инициализировать конкретный слайдер
const slider = document.querySelector('.slider');
SliderComponent.init(slider);
```
