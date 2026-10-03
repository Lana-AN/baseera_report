# طريقة العمل على الريبو

## القواعد

1. **كل واحد يشتغل على فصل/ملف خاص فيه** (انظر جدول التوزيع تحت) عشان ما يصير تعارض (conflict).
2. لا أحد يعدّل في `00-main.tex` إلا للضرورة (إضافة حزمة أو اختصار)، وينبّه الباقين.
3. لا نرفع ملفات الناتج (`build/`, `*.pdf`, `*.aux`...)، الـ `.gitignore` يتكفل فيها.
4. المراجع تنضاف في `ref.bib` فقط، كل مرجع في آخر الملف.
5. الصور في مجلد `figures/`.

## توزيع الفصول (عدّلوه)

| الفصل | المسؤول |
|---|---|
| Ch1 Introduction | |
| Ch2 Literature Review | |
| Ch3 Problem Analysis | |
| Ch4 System Design | |

## خطوات العمل اليومية

```bash
git pull                              # قبل ما تبدأ
git checkout -b ch2-literature        # فرع باسم الفصل (مرة وحدة)
# ... تعدّل ملفك ...
git add 02-literature.tex ref.bib
git commit -m "Add background section"
git push -u origin ch2-literature
```

بعدها تفتح Pull Request على `main` في GitHub، ويراجعه واحد من الفريق قبل الدمج.

إذا حصل تعارض في `ref.bib` (لأن الكل يضيف فيه) احتفظوا بالنسختين الاثنتين وشيلوا علامات `<<<<<<<`.
