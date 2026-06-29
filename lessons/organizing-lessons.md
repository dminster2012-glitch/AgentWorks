---
layout: default
title: ארגון שיעורים
parent: שיעורים
nav_order: 2
permalink: /lessons/organizing-lessons/
---

# ארגון שיעורים

ככל שהאתר גדל, חשוב לשמור על שמות קבצים ברורים ועל ניווט צפוי. תיקיית `lessons/` מיועדת לכל דפי השיעור.

## כללי עבודה מומלצים

| כלל | דוגמה טובה | למה זה עוזר |
| --- | --- | --- |
| שמות באנגלית קטנה | `reading-map.md` | כתובות URL יציבות ופשוטות |
| כותרת בעברית | `title: מפת קריאה` | ניווט ברור לקוראים |
| סדר ניווט מפורש | `nav_order: 3` | שליטה במיקום בתפריט |

## Front matter לדוגמה

```yaml
---
layout: default
title: שיעור חדש
parent: שיעורים
nav_order: 3
permalink: /lessons/new-lesson/
---
```

{: .task }
כשמוסיפים שיעור חדש, ודאו שהשדה `parent` תואם בדיוק לכותרת עמוד האב: `שיעורים`.
