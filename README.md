# web

Одна страница: аватарка выпрыгивает из точки, рядом выезжает «Hello»,
потом оно сменяется на «This is a test». Только HTML и CSS (из SCSS), без JS.

## Что где лежит

```
index.html          разметка
scss/style.scss     стили — правки вносить сюда
css/style.css       скомпилированный CSS, его читает браузер (руками не править)
fonts/              Gravitas One и Abril Fatface (woff2) + их лицензии OFL
media/avatar.mp4    аватарка (видео без звука, 400×400)
```

## Как править

1. Открыть `scss/style.scss`. Цвета, размеры и тайминги анимации — в самом верху,
   в блоке «Настройки».
2. Пересобрать CSS:

   ```sh
   sassc --style expanded scss/style.scss css/style.css
   ```

   (или `sass scss/style.scss css/style.css`, если стоит Dart Sass)
3. Открыть `index.html` в браузере.

Текст фраз меняется прямо в `index.html`. Если меняешь текст, обнови
и `$hello-width` / `$test-width` в настройках scss: от них зависит, куда
съезжает группа. Ширину слова в em можно посмотреть в инспекторе браузера:
ширина элемента в px, делённая на размер шрифта в px.

Кривые скорости (`$ease-…`) удобно крутить на cubic-bezier.com.
