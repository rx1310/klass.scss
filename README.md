# klass.scss
Абсолютно бесполезная фигня, которая непонятна даже автору (ну мне).

![GitHub](https://img.shields.io/github/license/rx1310/klass.scss?style=flat-square)
![GitHub language count](https://img.shields.io/github/languages/count/rx1310/klass.scss?style=flat-square)
![GitHub top language](https://img.shields.io/github/languages/top/rx1310/klass.scss?style=flat-square)
![npm](https://img.shields.io/npm/v/@rx1310/klass.scss?label=npm%3A%20version&style=flat-square)
![npms.io (popularity)](https://img.shields.io/npms-io/popularity-score/@rx1310/klass.scss?label=npm%3A%20popularity&style=flat-square)
![npm bundle size (scoped)](https://img.shields.io/bundlephobia/minzip/@rx1310/klass.scss?label=npm%3A%20minified%20size&style=flat-square)
![npm](https://img.shields.io/npm/dm/@rx1310/klass.scss?label=npm%3A%20downloads&style=flat-square)
![npm (prod) dependency version](https://img.shields.io/npm/dependency-version/@rx1310/klass.scss/sass?style=flat-square)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/rx1310/klass.scss?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/rx1310/klass.scss?style=flat-square)
![GitHub contributors](https://img.shields.io/github/contributors/rx1310/klass.scss?style=flat-square)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/rx1310/klass.scss?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/rx1310/klass.scss?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/rx1310/klass.scss?style=flat-square)
![GitHub closed issues](https://img.shields.io/github/issues-closed/rx1310/klass.scss?style=flat-square)
![GitHub pull requests](https://img.shields.io/github/issues-pr/rx1310/klass.scss?style=flat-square)
![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/rx1310/klass.scss?style=flat-square)

Крч, прикол в том, что я вообще не выкупаю нахрен это написал, но оно, блин, работает. Причем я написал с первого раза и что-то с первого раза начало работать. А чё я? А я ниче. Прихерел от этого, но потом понял, что ничего такого прям крышесносного не написал и ошибку там просто нечему выкидывать. Такие дела.

Ах да, это миксин + функция на языке препроцессора [SASS](https://github.com/sass). Миксин `klass` позволяет написать CSS-стили для компонента в непонятной даже для меня структуре. А функция `kvar()` просто помогает не писать постоянно `var(--propName)`, а просто `kvar(propName)`. В принципе также бесполезная херь.

> Как всё это юзать показано в примере ниже в пятом пункте.

## Установка и использование
Для начала необходимо иметь установленный пакетный менеджер (напр.: [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) или любой другой совместимый). Я буду показывать на примере npm.

Порядок действий:

1. откройте терминал (командную строку) в папке проекта:

    ```bash
    cd my-project
    ```

2. введите команду для установки npm-пакета [`@rx1310/klass.scss`](https://npmjs.com/package/@rx1310/klass.scss) в проект:

    ```bash
    npm install @rx1310/klass.scss
    ```

3. дождитесь установки всех пакетов и зависимостей в проект
4. в основной SASS-файл стилей пропишите импорт модуля `klass.scss`:

    ```scss
    @use 'node_modules/@rx1310/klass.scss' as *;
    ```

    > `*` означает, что миксины и функции из пакета `@rx1310/klass.scss` доступны глобально. Вы можете использовать [пространство имён в SASS](https://sass-lang.com/documentation/at-rules/use#choosing-a-namespace), чтобы избежать возможных конфликтов с другими пакетами/библиотеками.

5. создаете новый "класс" в файле стилей, как на примере ниже:

    ```scss
    @use 'node_modules/@rx1310/klass.scss' as *;
    @use 'node_modules/@rx1310/klass.scss' as k19;

    @include klass(button, (
      colorFont: #000,
      colorBackground: #fcfc,
      borderRadius: 8px
    )) {
      color: kvar(colorFont);
      background-color: kvar(colorBackground);
      @include border-radius(kvar(borderRadius));
    }
    ```
    и в итоговом CSS-файле должно быть что-то похожее:

    ```css
    .button {
      --colorFont: #000;
      --colorBackground: rgba(255, 204, 255, 0.8);
      --borderRadius: 8px;
      color: var(--colorFont);
      background-color: var(--colorBackground);
      -webkit-border-radius: var(--borderRadius);
      -moz-border-radius: var(--borderRadius);
      border-radius: var(--borderRadius);
    }
    ```

6. готово!

## Лицензия
Проект [klass.scss](https://github.com/rx1310/klass.scss) распространяется совершенно бесплатно и находится под защитой лицензии [MIT](LICENSE).

Инструментарий, используемый в разработке, распространяется по указанной автором / компанией / разработчиком лицензии, не зависящей от этого проекта!

```
MIT License
Copyright (c) 2022, Haba Kudzaev (rx1310) <rx1310@inbox.ru>
```

> Если Вы нашли нарушение чьей-либо лицензии в моем проекте, то просьба написать мне → [Telegram](https://t.me/rx1310), [эл. почта](mailto:rx1310@inbox.ru) или [VK](https://vk.com).
