---
title: Способи управління
subtitle: АВТОРСЬКИМИ ПРАВАМИ
author:
  - Ілля Брашкін
---

## Проблема класичного копірайту

TODO

## Публічні оферти

---

### Дозвільні

(MIT, Apache 2.0)

Максимальна свобода.

> «Роби з кодом що хочеш, використовуй у комерції, тільки збережи копірайт та
> текст ліцензії».

---

### Copyleft

(GPL, AGPL)

«Вірусне» ліцензування.

> Використовуєш цей код? Усі похідні продукти також мають бути відкритими під
> цією ж ліцензією.

---

### Creative Commons

(CC BY, CC0)

Управління правами для не-коду:

- документація;
- датасети для ШІ;
- графіка;
- навчальні матеріали.

## Стандарт [REUSE][link-reuse]

---

### Проблема: Хаос у репозиторіях

Ліцензія лежить у файлі `LICENSE` у корені проєкту, але незрозуміло, під чим
ліцензовані окремі скрипти, конфіги чи запозичені файли. Це створює **юридичні
ризики** для бізнесу.

---

### Розв'язання проблеми: REUSE

Free Software Foundation Europe запровадила стандарт REUSE, згідно з яким
кожен файл має містити **машинозчитувані метадані** за допомогою `SPDX`
заголовків.

---

```ts
// SPDX-FileCopyrightText: Copyright (c) 2026 Jane Doe
// SPDX-License-Identifier: MIT

export function doSomething(): void {
  // …
}
```

---

### Інтеграція в CI/CD

`.github/workflows/reuse.yml`

```yaml
name: reuse
'on':
  push:
  pull_request:
jobs:
  reuse:
    timeout-minutes: 15
    runs-on: ubuntu-24.04
    steps:
      - uses: actions/checkout@v7
      - uses: fsfe/reuse-action@v6
```

## Виклики сьогодення

TODO

[link-reuse]: https://reuse-standard.org/
