### Windows

יש שתי דרכים להתקין את Yarn על מערכת ההפעלה חלונות.

#### להוריד את אשף ההתקנה

תוכל להשתמש בקובץ ה`.msi` כדי לעבור תהליך התקנה סדור על Windows.

אם תשתמש באשף ההתקנה, תצטרך קודם כל להתקין את [Node.js](https://nodejs.org/).<a class="btn btn-primary" href="/latest.msi">הורדת אשף ההתקנה</a>#### התקנה דרך Chocolatey

[Chocolatey](https://chocolatey.org/) הוא מנהל חבילות ל-Windows, ותוכל להתקין את Chocolatey בעזרת [הוראות ההתקנה האלה](https://chocolatey.org/install).

ברגע שיש לך Chocolatey מותקן, תוכל להתקין את Yarn על ידי הרצה של הפקודות הבאות ב-console:

```sh
choco install yarn
```

זה גם יוודקא שיש לך [Node.js](https://nodejs.org/) מותקן.

#### הערה

אנא תוסיף ל-whitelist את ספריית הפרויקט שלך ואת ספריית המטמון של Yarn (שנמצאת ב-%LocalAppData%\Yarn) בתוכנת האנטי-וירוס שלך, אחרת כל התקנה של חבילות תהיה משמעותית איטית יותר משום שכל חבילה נסרקת לפני שהיא נכתבת לדיסק.