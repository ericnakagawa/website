* * *

id: docs_creating_a_project guide: docs_yarn_workflow layout: guide

* * *

זה לא משנה אם יש לך מאגר/ספריית קוד קיימת, או אם אתה מתחיל אחד חדש לגמרי, הוספת Yarn עובדת באותה הדרך כל פעם.

בטרמינל / קונסולה שלך, בתיקייה שבה תרצה להוסיף את Yarn (אשר כמעט תמיד צריך להיות הroot של הפרויקט שלך), הרץ את הפקודה הבאה:

```sh
yarn init
```

לאחר מכן, ייפתח טופס אינטראקטיבי ליצירת פרויקט yarn חדש עם השאלות הבאות:

    name (your-project):
    version (1.0.0):
    description:
    entry point (index.js):
    git repository:
    author:
    license (MIT):
    

באפשרותך לענות על כל אחת מהשאלות האלו או שתוכל פשוט ללחוץ על כפתור האנטר על מנת להשאיר את ברירת המחדל או להשאיר את השדה ריק.

### `package.json` [](#toc-package-json){#toc-package-json.toc}

עכשיו אמור להיות לך קובץ בשם `package.json` שנראה דומה לדוגמה מטה:

```json
{
  "name": "my-new-project",
  "version": "1.0.0",
  "description": "My New Project description.",
  "main": "index.js",
  "repository": {
    "url": "https://example.com/your-username/my-new-project",
    "type": "git"
  },
  "author": "Your Name <you@example.com>",
  "license": "MIT"
}
```

כאשר אתה מריץ את הפקודה `yarn init`, כל מה שהיא עושה זה ליצור את הקובץ הזה ושום דבר לא קורה ברקע. אתה מוזמן לערוך את הקובץ הזה ככל שתרצה.

הקובץ `package.json` שלך משתמש רק בשביל לשמור מידע על הפרויקט שלך. המידע כולל את השם של הפרויקט, המתחזקים שלו, ואיפה נמצא קוד המקור. אך הכי חשוב - הוא כולל את המידע על אילו חבילות דרושות להתקנה בשביל הפרויקט.