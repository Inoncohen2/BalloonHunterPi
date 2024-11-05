# BalloonHunterPi

🚀 **אחרי חודשים של למידה אינטנסיבית, פיתוח ובדיקות, אני גאה לשתף אתכם במערכת BalloonHunterPi – מערכת אוטונומית לזיהוי, מעקב ויירוט בלונים בזמן אמת** 🎈. הפרויקט הזה הוא חלק מפרויקט הגמר שלי בהנדסת חשמל ואלקטרוניקה, שבו שילבתי עיבוד תמונה, בינה מלאכותית ובקרת תנועה – תחומים שלמדתי להכיר לעומק.

## תוכן עניינים
- [אודות](#אודות)
- [תכונות](#תכונות)
- [מטרות הפרויקט](#מטרות-הפרויקט)
- [דרישות חומרה ותוכנה](#דרישות-חומרה-ותוכנה)
- [איך זה עובד?](#איך-זה-עובד)
- [תהליך הפיתוח](#תהליך-הפיתוח)
- [אתגרים עיקריים](#אתגרים-עיקריים)
- [תוצאות עיקריות](#תוצאות-עיקריות)
- [הערך של הפרויקט](#הערך-של-הפרויקט)
- [התקנה והפעלה](#התקנה-והפעלה)
- [ארכיטקטורת המערכת](#ארכיטקטורת-המערכת)
- [שיפורים עתידיים](#שיפורים-עתידיים)
- [הדגמה ויזואלית](#הדגמה-ויזואלית)
- [סרטון הדגמה](#סרטון-הדגמה)
- [תודות](#תודות)

---

## אודות
**BalloonHunterPi** היא מערכת חכמה, ניידת ואוטונומית, המיועדת לזיהוי, מעקב ויירוט של בלונים בזמן אמת. המערכת פותחה כדי להוות מודל ללמידה ולהדגמה של יכולות זיהוי ועקיבה אחר אובייקטים נעים. היא מבוססת על פלטפורמת Raspberry Pi ומשלבת טכנולוגיות מתקדמות בעיבוד תמונה ובינה מלאכותית. 

## תכונות
- **זיהוי בזמן אמת** - המערכת משתמשת במודל TensorFlow Lite מותאם לזיהוי בלונים במרחב.
- **מעקב אוטומטי** - כיוון סמן הלייזר למיקום הבלון והתאמתו בהתאם לתנועת הבלון.
- **מנגנון בטיחות** - סמן הלייזר כבה אוטומטית כאשר הבלון יוצא מטווח הזיהוי, מה שמשפר את בטיחות המערכת.
- **תמיכה ב-Raspberry Pi** - מאפשר למערכת לפעול באופן עצמאי ובעלות נמוכה.

## מטרות הפרויקט
המשימה הייתה לפתח מערכת אוטונומית שמסוגלת:
1. **לזהות בלונים בתנועה** ולהעריך את מיקומם.
2. **לעקוב אחרי בלונים** ולכוון לייזר אליהם בצורה מדויקת.
3. **לעבוד בזמן אמת** על גבי פלטפורמת Raspberry Pi תוך שימוש בטכנולוגיות עיבוד תמונה מתקדמות.

---

## דרישות חומרה ותוכנה
### חומרה
- **Raspberry Pi 4 Model B**
- **מצלמת USB (2K)**
- **מנועי סרוו (MG995)** לטווח תנועה של 180 מעלות
- **סמן לייזר**
- **ספק כוח חיצוני (5V, 3A)** 
- **גימבל** לייצוב המצלמה וסמן הלייזר
- **כבלים**

### תוכנה
- **מערכת הפעלה**: Raspbian
- **שפת תכנות**: Python 3.7
- **ספריות Python**:
  - TensorFlow Lite
  - OpenCV
  - RPi.GPIO
  - Numpy
  - time

---

## איך זה עובד?
1. **מודול קליטת וידאו**: מצלמת USB ברזולוציה גבוהה מחוברת ל-Raspberry Pi, ומזרימה וידאו בזמן אמת כדי לספק נתונים על מיקום הבלון במרחב.
2. **זיהוי ועיבוד תמונה**: באמצעות TensorFlow Lite ו-OpenCV, המערכת מזהה את הבלון בפריים, מחשבת את מיקומו ומעריכה את המרחק.
3. **בקרת תנועה מדויקת**: מנועי סרוו מכוונים את סמן הלייזר בהתאם לתנועת הבלון, מה שמאפשר שמירה על מיקוד מדויק. מנגנון בטיחות מובנה מכבה את הלייזר כאשר הבלון יוצא מטווח המעקב.

---

## תהליך הפיתוח
- **איסוף ותיוג תמונות**: אספתי תמונות רבות של בלונים ותיוגתי אותן ידנית כדי ליצור מאגר נתונים איכותי לאימון המודל.
- **אימון המודל**: אימנתי את המודל על GPU תוך ביצוע אופטימיזציות לשיפור דיוק ומהירות.
- **הטמעת המודל ב-Raspberry Pi**: המודל הומר לפורמט TensorFlow Lite, כך שהמערכת מסוגלת לזהות ולעקוב אחרי בלונים בזמן אמת.

---

## אתגרים עיקריים
- **מגבלות כוח עיבוד**: היכולת להריץ זיהוי ועיבוד תמונה בזמן אמת על גבי Raspberry Pi דרשה מודל יעיל וקל משקל.
- **שמירה על מיקוד בתנועה מהירה**: התאמת מנועי הסרוו לשמירה על מיקוד הבלון גם בתנועה היוותה אתגר משמעותי.
- **ביצועים וזמן תגובה**: פתרתי את האתגר של תגובות איטיות על ידי אופטימיזציות מיוחדות לשיפור ביצועי המערכת.

---

## תוצאות עיקריות
- **זיהוי מדויק ומהיר**: המערכת הצליחה לזהות בלונים במצבי תאורה ומרחקים שונים.
- **בקרת מנועי סרוו חלקה**: המנועים כיוונו את הלייזר במהירות ובדיוק גבוה לעבר הבלון.
- **מנגנון בטיחות מובנה**: הלייזר כבה אוטומטית כשהבלון יוצא מהטווח, מה שתורם לבטיחות המערכת ולחיסכון באנרגיה.

---

## הערך של הפרויקט
הפרויקט הזה מדגים את היכולת לשלב בין עיבוד תמונה, בינה מלאכותית ובקרת תנועה לכדי מערכת חכמה וגמישה, עם פוטנציאל יישומי בתחומים כמו:
- **אבטחה וניטור**: מעקב אוטומטי אחר אובייקטים.
- **הדרכה ברובוטיקה**: הדגמות מעשיות ואינטראקטיביות.
- **תעשיות ביטחוניות**: מערכות מתקדמות למעקב, הגנה ואבטחה.

---

## התקנה והפעלה
### התקנה
1. **הורדת מערכת ההפעלה** Raspbian והתקנתה על ה-Raspberry Pi.
2. **הורדת הקוד** מה-GitHub:
   ```bash
   git clone https://github.com/Inoncohen2/TensorFlow-Lite-Balloon-Detection-on-Raspberry-Pi.git
   mv TensorFlow-Lite-Balloon-Detection-on-Raspberry-Pi Balloon_Detection
   cd Balloon_Detection

3. **התקנת סביבה וירטואלית**:
   ```bash
   sudo pip3 install virtualenv
   python3 -m venv balloon_env
   source balloon_env/bin/activate
   ```
4. **התקנת התלויות**:
   ```bash
   bash get_pi_requirements.sh
   ```

### הפעלה
1. הפעל את הסביבה הווירטואלית:
   ```bash
   source balloon_env/bin/activate
   ```
2. הרץ את הקוד:
   ```bash
   python3 BallonHunterPi.py
   ```

---

## ארכיטקטורת המערכת
המערכת מחולקת לשלושה מודולים עיקריים:
1. **מודול קליטת וידאו** - מקבל את קלט הווידאו ומכין אותו לעיבוד.
2. **מודול עיבוד וזיהוי בלונים** - מזהה את הבלונים ומחשב את מיקומם.
3. **מודול שליטה במנועי הסרוו** - מכוון את סמן הלייזר לפי מיקום הבלון.

---

## שיפורים עתידיים
- **שימוש במאיץ חומרה (Google Coral)**: עשוי לשפר ביצועים.
- **שדרוג למודל YOLO**: עשוי לספק זיהוי מהיר יותר.
- **שיפור במנועי סרוו**: למעקב מדויק יותר בתנועות מהירות.

---

## הדגמה ויזואלית

להלן מספר תמונות של מערכת BalloonHunterPi בפעולה:

![תמונה 1 - תצוגה כללית של המערכת](images/IMG_4549.png)
![תמונה 2 - זיהוי בלונים](images/IMG_4554.png)
![תמונה 3 - מעקב באמצעות לייזר](images/IMG_4564.png)

---

## סרטון הדגמה

לצפייה במערכת בפעולה, מזהה ומיירטת בלונים, צפו בסרטון הבא:
[צפה בסרטון הדגמה ב-YouTube](https://youtube.com/shorts/DD6aBiDKsEU?si=VOegjBFnZ_yktvcv)

או לחצו על התמונה למעבר לסרטון:

[![סרטון הדגמה](images/IMG_4549.png)](https://youtube.com/shorts/DD6aBiDKsEU?si=VOegjBFnZ_yktvcv)

---

## תודות
תודה למנחה שלי ולכל מי שתמך במהלך הדרך, נתן עצות והכוונה, ותרם להצלחת הפרויקט.
