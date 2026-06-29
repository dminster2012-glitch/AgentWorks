# ערכת שיעורים בעברית

מאגר זה מכיל אתר לימודי קטן בעברית, בנוי כמאגר תוכן של Jekyll ומפורסם דרך GitHub Pages. העיצוב מגיע מה-theme המרוחק Just the Docs בגרסה נעולה:

```yaml
remote_theme: just-the-docs/just-the-docs@v0.12.0
```

המאגר מיועד לסדנת מורים קצרה: עורכים Markdown, דוחפים ל-GitHub, ו-GitHub Actions בונה ומפרסם את האתר. אין צורך להריץ Ruby, Bundler או Jekyll מקומית כחלק מהעבודה הרגילה.

## הוספת שיעור חדש

1. צרו קובץ חדש בתוך `lessons/`, למשל `lessons/new-lesson.md`.
2. הוסיפו front matter בראש הקובץ:

```yaml
---
layout: default
title: שיעור חדש
parent: שיעורים
nav_order: 3
permalink: /lessons/new-lesson/
---
```

3. כתבו את תוכן השיעור בעברית מתחת ל-front matter.
4. ודאו שאין בקובץ מידע פרטי של תלמידים, הורים, צוות או בית הספר.

## ניווט באתר

הניווט נשלט באמצעות שדות front matter:

- `nav_order` קובע את סדר העמוד בתפריט.
- `has_children: true` מסמן עמוד אב, כמו `lessons/index.md`.
- `parent: שיעורים` מחבר שיעור לעמוד האב.
- `permalink` קובע כתובת יציבה וברורה לעמוד.

קישורים פנימיים צריכים להשתמש ב-`relative_url`, למשל:

```markdown
[לעמוד השיעורים]({{ '/lessons/' | relative_url }})
```

כך הקישורים נשארים תקינים באתר פרויקט של GitHub Pages, שבו הכתובת כוללת את base path של המאגר.

## פרסום דרך GitHub Actions

ה-workflow נמצא ב-`.github/workflows/pages.yml`. בכל push לענף `main`, GitHub Actions:

1. בודק את הקוד מהמאגר.
2. מפעיל את `actions/configure-pages`.
3. בונה את האתר עם `actions/jekyll-build-pages`.
4. מעלה artifact.
5. מפרסם ל-GitHub Pages עם `actions/deploy-pages`.

אם פרסום נכשל, פותחים את לשונית **Actions** במאגר GitHub, נכנסים לריצה האחרונה של "Deploy Jekyll site to Pages", ובודקים באיזה שלב הופיעה השגיאה.

## שינוי גרסת ה-theme

ה-theme נעול ב-`_config.yml` כדי למנוע שינויי עיצוב לא צפויים. שינוי גרסה צריך להיות מכוון:

1. בדקו את release notes של Just the Docs.
2. עדכנו את הערך `remote_theme`.
3. דחפו לענף `main`.
4. ודאו שה-build ב-GitHub Actions עובר ושהאתר נראה תקין.

אין להעתיק את קוד המקור של ה-theme לתוך המאגר אלא אם יש סיבה נקודתית ומנומקת.

## רישוי ותוכן מקורי

המאגר ציבורי, אבל ציבוריות אינה מגדירה אוטומטית רישיון שימוש חוזר לתוכן המקורי של המורה. אם רוצים לאפשר שימוש חוזר, יש להוסיף קובץ רישיון מפורש שמתאים למדיניות המורה או בית הספר.

## תצוגה מקומית

תצוגה מקומית עם Ruby, Bundler או Jekyll היא אפשרות מתקדמת בלבד למי שכבר יש לו סביבה עובדת. היא אינה חלק מה-workflow הנדרש בסדנה, ואין צורך להשתמש ב-WSL או להריץ `bundle exec jekyll serve` כדי לעבוד עם המאגר הזה.
