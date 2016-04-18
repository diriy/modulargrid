# Основные настройки #
Все настройки изображения-макета задаются как свойства объекта `image` в объекте настройки:
```
ModularGrid.init(
   {
      image: {...}
   }
);
```

Адрес изображения задаётся строкой `image.src`, ширина в пикселах - числом `image.width`, высота в пикселах - числом `image.height`.

Чтобы центрировать изображение, установите свойства `image.centered` в `true`.

## Пример ##
```
ModularGrid.init(
   {
      image: {
         src: 'http://example.com/design.png',
         width: 960,
         height: 1200
      }
   }
);
```
Создаст изображение-макет (размером 960 на 1200 пикселей) в левом верхнем углу рабочей области браузера.

# Дополнительные настройки #
```
/**
 * Функция вызывается каждый раз при нажатии клавиш в браузере.
 * @param {Object} params информация о нажатой комбинации клавиш (params.ctrlKey, params.altKey, params.keyCode)
 * @return {Boolean} true, если нужно показать/скрыть изображение
 */
shouldToggleVisibility:
   function (params) {
      // Ctrl + \
      var result = (params.ctrlKey && params.keyCode == 220);
      return result;
   },

/**
 * Значения CSS-свойства z-index HTML-контейнера изображения
 * @type Number
 */
'z-index': 255,

/**
 * Отступ от верхнего края рабочей области браузера до изображения в пикселах
 * @type Number
 */
marginTop: 0,

/**
 * Отступ от левого края рабочей области браузера до изображения.
 * Возможные значения аналогичны значениям CSS-свойства margin-left
 * @type Number
 */
marginLeft: '0px',

/**
 * Отступ от правого края рабочей области браузера до изображения.
 * Возможные значения аналогичны значениям CSS-свойства margin-left
 * @type Number
 */
marginRight: '0px'
```