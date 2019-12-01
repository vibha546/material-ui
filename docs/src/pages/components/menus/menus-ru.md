---
title: React-компонент Меню
components: Menu, MenuItem, MenuList, ClickAwayListener, Popover, Popper
---

# Меню

<p class="description">Меню временно отображают список вариантов.</p>

A [Menu](https://material.io/design/components/menus.html) displays a list of choices on a temporary surface. Оно появляется когда пользователь взаимодействует с кнопкой или другим элементом управления.

## Простое меню

Простые меню по умолчанию открываются над якорным элементом (это поведение можно изменить с помощью props). Находясь вблизи края экрана, простое меню располагается таким образом, чтобы все элементы меню были полностью видны.

Выбор варианта должен в идеале немедленно зафиксировать его и закрыть меню.

**Disambiguation**: In contrast to simple menus, simple dialogs can present additional detail related to the options available for a list item or provide navigational or orthogonal actions related to the primary task. Although they can display the same content, simple menus are preferred over simple dialogs because simple menus are less disruptive to the user’s current context.

{{"demo": "pages/components/menus/SimpleMenu.js"}}

## Выбранные меню

If used for item selection, when opened, simple menus attempt to vertically align the currently selected menu item with the anchor element, and the initial focus will be placed on the selected menu item. The currently selected menu item is set using the `selected` property (from [ListItem](/api/list-item/)). To use a selected menu item without impacting the initial focus or the vertical positioning of the menu, set the `variant` property to `menu`.

{{"demo": "pages/components/menus/SimpleListMenu.js"}}

## MenuList composition

The `Menu` component uses the `Popover` component internally. However, you might want to use a different positioning strategy, or not blocking the scroll. For answering those needs, we expose a `MenuList` component that you can compose, with `Popper` in this example.

The primary responsibility of the `MenuList` component is to handle the focus.

{{"demo": "pages/components/menus/MenuListComposition.js"}}

## Customized menus

Ниже находится пример кастомизации компонента. You can learn more about this in the [overrides documentation page](/customization/components/).

{{"demo": "pages/components/menus/CustomizedMenus.js"}}

The `MenuItem` is a wrapper around `ListItem` with some additional styles. You can use the same list composition features with the `MenuItem` component:

## Меню с максимальной высотой

Если высота меню препятствует отображению всех пунктов меню, меню можно прокручивать внутри.

{{"demo": "pages/components/menus/LongMenu.js"}}

## Ограничения

Существует [ошибка flexbox](https://bugs.chromium.org/p/chromium/issues/detail?id=327437), которая предотвращает работу свойства `text-overflow: ellipsis` внутри flexbox. Вы можете использовать компонент `Typography` с `noWrap`, чтобы обойти эту проблему:

{{"demo": "pages/components/menus/TypographyMenu.js"}}

## Change transition

Используйте другой transition.

{{"demo": "pages/components/menus/FadeMenu.js"}}

## Context menu

Here is an example of a context menu. (Right click to open.)

{{"demo": "pages/components/menus/ContextMenu.js"}}

## Дополнительные проекты

Для более сложных вариантов использования вы можете воспользоваться:

### PopupState helper

There is a 3rd party package [`material-ui-popup-state`](https://github.com/jcoreio/material-ui-popup-state) that takes care of menu state for you in most cases.

{{"demo": "pages/components/menus/MenuPopupState.js"}}