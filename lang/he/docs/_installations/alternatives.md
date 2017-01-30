### דרכים חלופיות

אם אתה משתמש במערכת הפעלה אחרת, או שאחת מהדרכים שסופקו למערכת ההפעלה הספציפית שלך לא עובדות, יש כמה חלופות לתהליך ההתקנה. תצטרך [להתקין Node.js](https://nodejs.org/) אם עדיין לא התקנת.

בהפצות לינוקס נפוצות כמו Debian, Ubuntu ו-CentOS, מומלץ להתקין את Yarn דרך החבילות שלנו במקום.

{% include_relative _installations/tarball.md %}

#### התקנה דרך npm

> **הערה:** התקנה דרך npm בדרך כלל לא מומלצת. npm הוא לא דטרמיניסטי, החבילות לא חתומות, ולכן npm לא מבצע אף בדיקות אמינות חוץ מ-SHA1 בסיסי, כך שהוא מהווה סיכון אבטחתי כשמתקינים תוכנות גלובאלית.
> 
> מפאת הסיבות שצוינו לעיל, מומלץ מאוד להתקין את Yarn דרך שיטות ההתקנה שמותאמות למערכת ההפעלה שלך.

בנוסף, תוכל להתקין את Yarn דרך [מנהל התלויות npm](http://npmjs.org/) אם יש לך אותו מותקן כבר. אם יש לך [Node.js](https://nodejs.org/) מותקן, אמור להיות לך גם npm.

ברגע שיש לך npm מותקן, תוכל להריץ:

```sh
npm install --global yarn
```

### התקנה לנתיב

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}