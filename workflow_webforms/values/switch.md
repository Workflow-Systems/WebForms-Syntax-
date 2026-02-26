---
description: Выбор.
---

# Switch

## Шаблон Switch <a href="#template_switch" id="template_switch"></a>

```markup
<Switch>
  <Case>
    <When></When>
    <Then></Then>
  </Case>
  <Case>
    <When></When>
    <Then></Then>
  </Case>
  <Case></Case>
</Switch>
```

Проверка внутри каждого тэга `<Case>` происходит сверху вниз до первого тэга `<Case>`, выражение тэга `<When>` которого будет имеет значение True.

Если тэг `<When>` отсутствует, то используется значение True.
