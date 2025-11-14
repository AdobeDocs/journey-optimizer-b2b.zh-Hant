---
title: 協助程式功能
description: Journey Optimizer B2B edition中個人化協助程式功能的參考指南。 其中包含字串、日期、數學等的語法和範例。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 運算式，編輯器，語法，個人化
source-git-commit: fee5bddcce11b3035da6ab93b18bcc7006b4b554
workflow-type: tm+mt
source-wordcount: '4857'
ht-degree: 6%

---

# 協助程式功能

使用個人化編輯器中的協助程式功能，透過操控資料、執行計算和格式化內容，以精確且有效率的方式定義個人化內容體驗。 探索並實驗這些功能、操作員和協助人員，瞭解他們如何合作，以幫助您製作量身打造的資料導向歷程。

>[!AVAILABILITY]
>
>協助程式功能適用於在[簡化架構](../simplified-architecture.md)上布建的Journey Optimizer B2B edition環境。

## 聚合函式

使用彙總函式將多個值分組，以形成單一摘要值。 您也可以使用陣列和清單函式，更輕鬆地定義與陣列、清單和字串的互動。

### 平均 {#average}

使用`average`函式傳回陣列中所有選取值的算術平均值。

+++語法

```sql
{%= average(array) %}
```

**範例**

下列作業會傳回所有訂單的平均價格。

```sql
{%=average(orders.order.price)%}
```

+++

### 計數 {#count}

使用`count`函式傳回指定陣列中的元素數目。

+++語法

```sql
{%= count(array) %}
```

**範例**

下列作業會傳回陣列中的訂單數。

```sql
{%= count(orders) %}
```

+++

### max {#max}

使用`max`函式傳回陣列中所有選取值的最大值。

+++語法

```sql
{%= max(array) %}
```

**範例**

下列作業會傳回所有訂單的最高價格。

```sql
{%=max(orders.order.price)%}
```

+++

### min {#min}

使用`min`函式傳回陣列中所有選取值的最小值。

+++語法

```sql
{%= min(array) %}
```

**範例**

下列作業會傳回所有訂單的最低價格。

```sql
{%=min(orders.order.price) %}
```

+++

### sum {#sum}

使用`sum`函式傳回陣列中所有選取值的總和。

+++語法

```sql
{%= sum(array) %}
```

**範例**

下列作業會傳回所有訂單價格的總和。

```sql
 {%=sum(orders.order.price)%}
```

+++

## 算術函式 {#maths}

使用算術函式對值執行基本計算。

### 新增 {#add}

使用`+` （相加）函式來尋找兩個引數運算式的總和。

+++語法

```sql
{%= double + double %}
```

**範例**

下列作業會加總兩個不同產品的價格。

```sql
{%= product1.price + product2.price %}
```

+++

### 乘 {#multiply}

使用`*` （乘法）函式尋找兩個引數運算式的乘積。

+++語法

```sql
{%= double * double %}
```

**範例**

下列作業會尋找存貨的產品與產品價格，以尋找產品的總值。

```sql
{%= product.inventory * product.price %}
```

+++

### 減 {#substract}

使用`-` （減法）函式找出兩個引數運算式的差異。

+++語法

```sql
{%= double - double %}
```

**範例**

下列作業會找出兩個不同產品之間的價格差異。

```sql
{%= product1.price - product2.price %}
```

+++

### 除 {#divide}

使用`/` （除法）函式尋找兩個引數運算式的商。

+++語法

```sql
{%= double / double %}
```

**範例**

下列作業會找出已售出產品總數與已賺取金額總數之間的商數，以檢視每個專案的平均成本。

```sql
{%= totalProduct.price / totalProduct.sold %}
```

+++

### 餘數 {#remainder}

使用`%` （餘數）函式找出兩個引數運算式相除後的餘數。

+++語法

```sql
{%= double % double %}
```

**範例**

下列作業會檢查個人的年齡是否可被5整除。

```sql
{%= person.age % 5 = 0 %}
```

+++

## 陣列和清單功能 {#arrays}

使用這些函式可讓與陣列、清單和字串的互動更容易。

### countOnlyNull {#count-only-null}

使用`countOnlyNull`函式計算清單中null值的數目。

+++語法

```sql
{%= countOnlyNull(array) %}
```

**範例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

傳回3。

+++

### countWithNull {#count-with-null}

使用`countWithNull`函式計算清單中包含null值的所有元素。

+++語法

```sql
{%= countWithNull(array) %}
```

**範例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

傳回6。

+++

### distinct {#distinct}

使用`distinct`函式從移除重複值的陣列或清單中取得值。

+++語法

```sql
{%= distinct(array) %}
```

**範例**

下列作業會指定在多個商店下訂單的人員。

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

+++

### distinctCountWithNull {#distinct-count-with-null}

使用`distinctCountWithNull`函式計算清單中包含null值的不同值數目。

+++語法

```sql
{%= distinctCountWithNull(array) %}
```

**範例**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

傳回3。

+++

### head {#head}

使用`head`函式傳回陣列或清單中的第一個專案。

+++語法

```sql
{%= head(array) %}
```

**範例**

下列作業會傳回價格最高的前五個訂單中的第一個。 有關`topN`函式的詳細資訊可在陣列[區段的`n`第一個](#first-n)中找到。

```sql
{%= head(topN(orders,price, 5)) %}
```

+++

### topN {#first-n}

`topN`函式根據給定的數值運算式以遞減順序排序陣列，並傳回前`N`個專案。 如果陣列大小小於`N`，則會傳回整個已排序陣列。

+++語法

```sql
{%= topN(array, value, amount) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{ARRAY}` | 要排序的陣列或清單。 |
| `{VALUE}` | 用來排序陣列或清單的屬性。 |
| `{AMOUNT}` | 要傳回的專案數。 |

**範例**

下列作業會傳回價格最低的前五個訂單。

```sql
{%= topN(orders,price, 5) %}
```

+++

### 在  {#in}

使用`in`函式來判斷專案是否為陣列或清單的成員。

+++語法

```sql
{%= in(value, array) %}
```

**範例**

下列作業會定義3月、6月或9月有生日的人員。

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

+++

### 包含 {#includes}

使用`includes`函式來判斷陣列或清單是否包含指定的專案。

+++語法

```sql
{%= includes(array,item) %}
```

**範例**

下列作業會定義哪些人最喜愛的顏色包括紅色。

```sql
{%= includes(person.favoriteColors,"red") %}
```

+++

### 相交 {#intersects}

`intersects`函式是用來判斷兩個陣列或清單是否至少有一個通用成員。

+++語法

```sql
{%= intersects(array1, array2) %}
```

**範例**

下列作業會定義哪些人最喜愛的顏色至少包括紅色、藍色或綠色之一。

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```

+++

<!-- ## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Syntax**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

### bottomN {#last-n}

`bottomN`函式根據給定的數值運算式以遞增順序排序陣列，並傳回前`N`個專案。 如果陣列大小小於`N`，則會傳回整個已排序陣列。

+++語法

```sql
{%= bottomN(array, value, amount) %}
```

| 引數 | 說明 |
| --------- | ----------- | 
| `{ARRAY}` | 要排序的陣列或清單。 |
| `{VALUE}` | 用來排序陣列或清單的屬性。 |
| `{AMOUNT}` | 要傳回的專案數。 |

**範例**

下列作業會傳回價格最高的前5個訂單。

```sql
{%= bottomN(orders,price, 5) %}
```

+++

### notIn {#notin}

使用`notIn`函式來判斷專案是否不是陣列或清單的成員。

>[!NOTE]
>
>`notIn`函式&#x200B;*也*&#x200B;可確保這兩個值都不等於null。 因此，結果不是`in`函式的完全否定。

+++語法

```sql
{%= notIn(value, array) %}
```

**範例**

下列作業會定義非三月、六月或九月的人員生日。

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```

+++

### subsetOf {#subset}

使用`subsetOf`函式來判斷特定陣列（陣列A）是否是另一個陣列（陣列B）的子集。 換句話說，陣列A中的所有元素都是陣列B的元素。

+++語法

```sql
{%= subsetOf(array1, array2) %}
```

**範例**

下列作業會定義造訪過其所有最喜愛城市的人。

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

+++

### 超集Of {#superset}

使用`supersetOf`函式來判斷特定陣列（陣列A）是否是另一個陣列（陣列B）的超集。 換句話說，該陣列A包含陣列B中的所有元素。

+++語法

```sql
{%= supersetOf(array1, array2) %}
```

**範例**

下列作業會定義已吃過至少一次壽司和比薩的人。

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"]) %}
```

+++

## 日期和時間函式 {#date-time}

使用日期和時間函式對值執行日期和時間作業。

### addDays {#add-days}

`addDays`函式會依指定的天數調整指定日期，使用正值增加值，使用負值減少值。

+++語法

```sql
{%= addDays(date, number) %}
```

**範例**

* 輸入： `{%= addDays(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 輸出： `2024-11-11T17:19:51Z`

+++

### addHours {#add-hours}

`addHours`函式會依指定的小時數調整指定日期，使用正值增加值，使用負值減少值。

+++語法

```sql
{%= addHours(date, number) %}
```

**範例**

* 輸入： `{%= addHours(stringToDate("2024-11-01T17:19:51Z"),1) %}`
* 輸出： `2024-11-01T18:19:51Z`

+++

### addMinutes {#add-minutes}

`addMinutes`函式會以指定的分鐘數調整指定日期，使用正值增加值，使用負值減少值。

+++語法

```sql
{%= addMinutes(date, number) %}
```

**範例**

* 輸入： `{%= addMinutes(stringToDate("2024-11-01T17:59:51Z"),10) %}`
* 輸出： `2024-11-01T18:09:51Z`

+++

### addMonths {#add-months}

`addMonths`函式會依指定的月數調整指定日期，使用正值增加值，使用負值減少值。

+++語法

```sql
{%= addMonths(date, number) %}
```

**範例**

* 輸入： `{%= addMonths(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 輸出： `2025-01-01T17:19:51Z`

+++

### addSeconds {#add-seconds}

`addSeconds`函式會以指定的秒數來調整指定日期，使用正值來遞增，使用負值來遞減。

+++語法

```sql
{%= addSeconds(date, number) %}
```

**範例**

* 輸入： `{%= addSeconds(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 輸出： `2024-11-01T17:20:01Z`

+++

### addYears {#add-years}

`addYears`函式會依指定的年數調整指定日期，使用正值增加值，使用負值減少值。

+++語法

```sql
{%= addYears(date, number) %}
```

**範例**

* 輸入： `{%= addYears(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 輸出： `2026-11-01T17:19:51Z`

+++

### 年齡 {#age}

使用`age`函式從指定日期擷取年齡。

+++語法

```sql
 {%= age(datetime) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(datetime) %}
```
-->

+++

### ageInDays {#age-days}

`ageInDays`函式會計算指定日期與目前日期之間經過的天數。 未來的日期使用負值，過去的日期使用正值。

+++語法

```sql
{%= ageInDays(date) %}
```

**範例**

currentDate = 2025-01-07T12:17:10.720122+05:30 （亞洲/加爾各答）

* 輸入： `{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* 輸出： `5`

+++

### Agenmonths {#age-months}

`ageInMonths`函式會計算指定日期與目前日期之間經過的月數。 未來的日期使用負值，過去的日期使用正值。

+++語法

```sql
{%= ageInMonths(date) %}
```

**範例**

currentDate = 2025-01-07T12:22:46.993748+05:30（亞洲/加爾各答）

* 輸入： `{%=ageInMonths(stringToDate("2024-01-01T00:00:00Z"))%}`
* 輸出： `12`

+++

### compareDates {#compare-dates}

`compareDates`函式會比較第一個輸入日期與另一個輸入日期。 如果date1等於date2，則會傳回0；如果date1在date2之前，則會傳回–1；如果date1在date2之後，則會傳回1。

+++語法

```sql
{%= compareDates(date1, date2) %}
```

**範例**

* 輸入： `{%=compareDates(stringToDate("2024-12-02T00:00:00Z"), stringToDate("2024-12-03T00:00:00Z"))%}`
* 輸出： `-1`

+++

### convertZonedDateTime {#convert-zoned-date-time}

`convertZonedDateTime`函式將日期時間轉換為指定的時區。

+++語法

```sql
{%= convertZonedDateTime(dateTime, timezone) %}
```

**範例**

* 輸入： `{%=convertZonedDateTime(stringToDate("2019-02-19T08:09:00Z"), "Asia/Tehran")%}`
* 輸出： `2019-02-19T11:39+03:30[Asia/Tehran]`

+++

### currentTimeInMillis {#current-time}

使用`currentTimeInMillis`函式擷取目前時間（以Epoch毫秒為單位）。

+++語法

```sql
{%= currentTimeInMillis() %}
```

<!--
**Example**

The following operation gets all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```
-->

+++

### dateDiff {#date-diff}

使用`dateDiff`函式來擷取兩個日期之間的天數差異。

+++語法

```sql
{%= dateDiff(datetime,datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOfMonth {#day-month}

`dayOfMonth`會傳回代表該月某日的數字。

+++語法

```sql
{%= dayOfMonth(datetime) %}
```

**範例**

* 輸入： `{%= dayOfMonth(stringToDate("2024-11-05T17:19:51Z")) %}`
* 輸出： `5`

+++

### DayOfWeek {#day-week}

使用`dayOfWeek`函式來擷取星期幾。

+++語法

```sql
{%= dayOfWeek(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOfYear {#day-year}

使用`dayOfYear`函式來擷取一年當中的第幾天。

+++語法

```sql
{%= dayOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInSeconds {#diff-seconds}

`diffInSeconds`函式傳回兩個日期之間的秒數差。

+++語法

```sql
{%= diffInSeconds(endDate, startDate) %}
```

**範例**

* 輸入： `{%=diffInSeconds(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T17:19:01Z"))%}`
* 輸出： `50`

+++

### extractHours {#extract-hours}

`extractHours`函式會從指定的時間戳記中擷取時數元件。

+++語法

```sql
{%= extractHours(date) %}
```

**範例**

* 輸入： `{%= extractHours(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `17`

+++

### extractMinutes {#extract-minutes}

`extractMinutes`函式會從指定的時間戳記中擷取分鐘元件。

+++語法

```sql
{%= extractMinutes(date) %}
```

**範例**

* 輸入： `{%= extractMinutes(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `19`

+++

### extractMonths {#extract-months}

`extractMonth`函式會從指定的時間戳記中擷取月份元件。

+++語法

```sql
{%= extractMonths(date) %}
```

**範例**

* 輸入： `{%=extractMonth(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `11`

+++

### extractSeconds {#extract-seconds}

`extractSeconds`函式會從指定的時間戳記中擷取第二個元件。

+++語法

```sql
{%= extractSeconds(date) %}
```

**範例**

* 輸入： `{%=extractSeconds(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `51`

+++

### formatDate {#format-date}

使用`formatDate`函式來格式化日期時間值。 格式應為有效的Java `DateTimeFormat`模式。

+++語法

```sql
{%= formatDate(datetime, format) %}
```

其中第一個字串是日期屬性，第二個值是您想要轉換及顯示日期的方式。

>[!NOTE]
>
> 如果日期模式無效，日期會回覆為ISO標準格式。
>
> 您可以使用[Oracle檔案](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}中摘要的Java日期格式函式

**範例**

下列作業會以下列格式傳回日期：MM/DD/YY。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

+++

#### 圖樣字元 {#pattern-characters}

有些樣式字母看起來可能類似，但代表不同的概念。

| 模式 | 含義 | 範例（針對`2023-12-31T10:15:30Z`） |
|---------|---------|--------------------------------------|
| `y` | 日曆年（標準年） | `2023` |
| `Y` | 周基準年(ISO 8601)。 可能會依年份邊界而有所不同。 | `2024` （2023年12月31日為2024年的第一週） |
| `M` | 月份（1-12或類似`Jan`， `January`的文字） | `12`或`Dec` |
| `m` | 小時制的分鐘(0-59) | `15` |
| `d` | 當月日期(1-31) | `31` |
| `D` | 年日(1-366) | `365` |

#### 支援地區設定的日期格式 {#format-date-locale}

您可以使用`formatDate`函式將日期時間值格式化為對應的語言敏感表示法，例如針對所需的地區設定。 格式應為有效的Java `DateTimeFormat`模式。

+++語法

```sql
{%= formatDate(datetime, format, locale) %}
```

其中第一個字串是日期屬性，第二個值是您想要轉換和顯示日期的方式，第三個值代表字串格式的地區設定。

>[!NOTE]
>
> 如果日期模式無效，日期會回覆為ISO標準格式。
>
> 您可以使用[Oracle檔案](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)中摘要的Java日期格式函式。
>
> 您可以使用[Oracle檔案](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)和[支援的地區設定](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html)中概述的格式設定和有效地區設定。

**範例**

下列作業會以下列格式傳回日期： MM/dd/YY和locale FRANCE。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY", "fr_FR") %}
```

+++

### getCurrentZonedDateTime {#get-current-zoned-date-time}

`getCurrentZonedDateTime`函式傳回目前日期和時間，並附上時區資訊。

+++語法

```sql
{%= getCurrentZonedDateTime() %}
```

**範例**

* 輸入： `{%= getCurrentZonedDateTime() %}`
* 輸出： `2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

+++

### diffinhours {#hours-difference}

`diffInHours`函式傳回兩個日期之間的時數差。

+++語法

```sql
{%= diffInHours(endDate, startDate) %}
```

**範例**

* 輸入： `{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* 輸出： `10`

+++

### diffinMinutes {#diff-minutes}

`diffInMinutes`函式傳回兩個日期之間的差異（以分鐘為單位）。

+++語法

```sql
{%= diffInMinutes(endDate, startDate) %}
```

**範例**

* 輸入： `{%= diffInMinutes(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T16:19:51Z"))%}`
* 輸出： `60`

+++

### diffinMonths {#months-difference}

`diffInMonths`函式傳回兩個日期之間的月差。

+++語法

```sql
{%= diffInMonths(endDate, startDate) %}
```

**範例**

* 輸入： `{%=diffInMonths(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-08-01T17:19:51Z"))%}`
* 輸出： `3`

+++

### setDays {#set-days}

使用`setDays`函式設定指定日期時間的月份日期。

+++語法

```sql
{%= setDays(datetime, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### setHours {#set-hours}

使用`setHours`函式設定日期時間的小時。

+++語法

```sql
{%= setHours(datetime, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### toDateTime {#string-to-date-time}

`toDateTime`函式將字串轉換為日期。 針對無效輸入會傳回epoch日期作為輸出。

+++語法

```sql
{%= toDateTime(string, string) %}
```

**範例**

* 輸入： `{%=toDateTime("2024-11-01T17:19:51Z")%}`
* 輸出： `2024-11-01T17:19:51Z`

+++

### toUTC {#to-utc}

使用`toUTC`函式將日期時間轉換為UTC。

+++語法

```sql
{%= toUTC(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### truncateToStartOfDay {#truncate-day}

使用`truncateToStartOfDay`函式，將指定日期時間設定為00:00的當天開始，藉此修改指定的日期時間。

+++語法

```sql
{%= truncateToStartOfDay(date) %}
```

**範例**

* 輸入： `{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* 輸出： `2024-11-01T00:00Z`

+++

### truncateToStartOfQuarter {#truncate-quarter}

使用`truncateToStartOfQuarter`函式將日期時間截斷為其季度的第一天（例如1月1日、4月1日、7月1日、10月1日），網址為00:00。

+++語法

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

**範例**

* 輸入： `{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `2024-10-01T00:00Z`

+++

### truncateToStartOfWeek {#truncate-week}

`truncateToStartOfWeek`函式將指定日期時間設定為一週的開始（星期一00:00），以修改該日期。

+++語法

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

**範例**

* 輸入： `{%= truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* 輸出： `2024-11-18T00:00Z // monday`

+++

### truncateToStartOfYear {#truncate-year}

使用`truncateToStartOfYear`函式將指定日期時間截斷為00:00一年的第一天（1月1日），以修改該日期。

+++語法

```sql
{%= truncateToStartOfYear(dateTime) %}
```

**範例**

* 輸入： `{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* 輸出： `2024-01-01T00:00Z`

+++

### weekOfYear {#week-of-year}

使用`weekOfYear`函式來擷取該年的周數。

+++語法

```sql
{%= weekOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInYear {#diff-years}

使用`diffInYears`函式以年為單位傳回兩個日期之間的差異。

+++語法

```sql
{%= diffInYears(endDate, startDate) %}: int
```

**範例**

* 輸入： `{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* 輸出： `5`

+++

## 運運算元函式 {#operators}

使用布林值和比較函式來執行邏輯評估。

### 和 {#and}

`and`函式用來建立邏輯結合。

+++語法

```sql
{%= query1 and query2 %}
```

**範例**

下列作業會傳回所有具有本國（法國）和出生年(1985)的人。

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

+++

### 或 {#or}

`or`函式用來建立邏輯分離。

+++語法

```sql
{%= query1 or query2 %}
```

**範例**

下列作業會傳回所有具有本國（法國）或出生年(1985)的人。

```sql
{%= profile.homeAddress.country = "France" or profile.person.birthYear = 1985 %}
```

+++

<!--
## Not{#not}

The `not` (or `!`) function is used to create a logical negation.

**Syntax**

```sql
not ({QUERY})
!({QUERY})
```

**Example**

The following operation will return all people who do not have their home country as Canada.

```sql
not (homeAddress.countryISO = "CA")
```
-->

### 等於 {#operator-equals}

`=` （等於）函式檢查一個值或運算式是否等於另一個值或運算式。

+++語法

```sql
{%= expression = value %}
```

**範例**

下列作業會檢查住家地址國家/地區是否為法國。

```sql
{%= profile.homeAddress.country = "France" %}
```

+++

### 不等於 {#notequal}

`!=` （不等於）函式檢查一個值或運算式是否為&#x200B;**不**&#x200B;等於另一個值或運算式。

+++語法

```sql
{%= expression != value %}
```

**範例**

下列作業會檢查住家地址國家/地區是否不是France。

```sql
{%= profile.homeAddress.country != "France" %}
```

+++

### 大於 {#greaterthan}

使用`>` （大於）函式來檢查第一個值是否大於第二個值。

+++語法

```sql
{%= expression1 > expression2 %}
```

**範例**

下列作業會嚴格定義1970年後出生的人。

```sql
{%= profile.person.birthYear > 1970 %}
```

+++

### 大於或等於 {#greaterthanorequal}

使用`>=` （大於或等於）函式來檢查第一個值是否大於或等於第二個值。

+++語法

```sql
{%= expression1 >= expression2 %}
```

**範例**

下列作業定義1970年或之後出生的人。

```sql
{%= profile.person.birthYear >= 1970 %}
```

+++

### 小於 {#lessthan}

使用`<` （小於）比較函式來檢查第一個值是否小於第二個值。

+++語法

```sql
{%= expression1 < expression2 %}
```

**範例**

下列作業定義2000年以前出生的人。

```sql
{%= profile.person.birthYear < 2000 %}
```

+++

### 小於或等於{#lessthanorequal}

使用`<=` （小於或等於）比較函式來檢查第一個值是否小於或等於第二個值。

+++語法

```sql
{%= expression1 <= expression2 %}
```

**範例**

下列作業會定義2000年或之前出生的人。

```sql
{%= profile.person.birthYear <= 2000 %}
```

+++

## 動態函式 {#dynamic-helpers}

使用動態協助程式函式，針對動態個人化使用條件式評估、反複專案和變數指派。

### 預設遞補值 {#default-value}

如果屬性為空白或null，則會使用`Default Fallback Value`協助程式傳回預裝置援值。 此機制適用於設定檔屬性和歷程事件。

+++語法

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

在此範例中，如果此設定檔的`there`屬性為空白或Null，則會顯示值`firstName`。

+++

### if （條件） {#if-function}

`if`協助程式用於定義條件區塊。
如果運算式評估傳回true，則會轉譯區塊，否則會略過該區塊。

+++語法

```sql
{%#if contains(account.accountOrganization.primaryEmailDomain, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

在`if`協助程式之後，您可以輸入`else`陳述式，以指定要執行的程式碼區塊（如果相同條件為false）。
`elseif`陳述式會指定新條件，以測試第一個陳述式是否傳回false。


**格式**

```sql
{
    {
        {%#if condition1%} element_1 
        {%else if condition2%} element_2 
        {%else%} default_element 
        {%/if%}
    }
}
```

<!-- 
**Examples**

* **Render different store links based on conditional expressions**

    ```sql
    {%#if profile.homeAddress.countryCode = "FR"%}
    <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
    {%else%}
    <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
    {%/if%}
    ```

* **Determine email address extension**

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Add a conditional link**

    The following operation adds a link to the `www.adobe.com/academia` website for profiles with '.edu' email addresses only, the `www.adobe.com/org` website for profiles with '.org' email addresses, and the default URL `www.adobe.com/users` for all other profiles:

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Conditional content based on audience membership**

    ```sql
    {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
    Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
    {%else if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"%}
    Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
    {%/if%}
    ```
-->

+++

### unless {#unless}

使用`unless`協助程式來定義條件區塊。 藉由與`if`協助程式相對，如果運算式評估傳回false，則會轉譯區塊。

+++語法

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**範例**

根據電子郵件地址副檔名轉譯某些內容：

```sql
{%#unless endsWith(account.accountOrganization.primaryEmailDomain}, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content
{%/unless%}
```

+++

### 每個 {#each}

使用`each`協助程式來反複處理陣列。

協助程式結構為```{{#each ArrayName}}``` YourContent `{{/each}}`

您可以在區塊內使用關鍵字`this`來參照個別陣列專案。 使用`{{@index}}`呈現陣列專案的索引。

+++語法

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
{{/each}}
```

**範例**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**範例**

呈現此使用者在購物車中擁有的產品清單：

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
{{/each}}
```

+++

### 替換為 {#with}

使用`with`協助程式變更範本部分的評估權杖。

+++語法

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

`with`協助程式也可用來定義捷徑變數。

**範例**

使用`with`將長變數名稱別名化為短變數名稱：

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

+++

### let {#let}

`let`函式允許將運算式儲存為變數，以便稍後在查詢中使用。

+++語法

```sql
{% let variable = expression %} {{variable}}
```

**範例**

下列範例可讓您計算購物車中價格介於100到1000之間的產品的總價。

```sql
{% let sum = 0%}
    {{#each profile.productsInCart as |p|}}
        {%#if p.price>100 and p.price<1000%}
            {%let sum = sum + p.price %}
        {%/if%}
    {{/each}}
{{sum}}
```

+++

## 執行中繼資料 {#execution-metadata}

>[!AVAILABILITY]
>
>此功能限量提供。 請聯絡您的 Adobe 代表以取得存取權。

使用`executionMetadata`以動態方式擷取自訂索引鍵/值組並儲存至訊息執行內容。

透過此功能，您可以將內容相關資訊附加至行銷活動或歷程中的任何原生動作。 使用它可將即時傳遞內容資料匯出至外部系統，以供多種用途，例如追蹤、分析、個人化和下游處理。

>[!NOTE]
>
>自訂動作不支援`executionMetadata`函式。

例如，您可以使用`executionMetadata`協助程式將特定ID附加至傳送給每個設定檔的每個傳遞。 此資訊會在執行階段產生，然後可匯出擴充的執行中繼資料，以供與外部報告平台進行下游調解。

+++語法

```
{{executionMetadata key="your_key" value="your_value"}}
```

在此語法中，`key`參考中繼資料名稱，而`value`是要儲存的中繼資料。

**運作方式**

從行銷活動或歷程內的管道內容中選取任何元素，並使用個人化編輯器將`executionMetadata`協助程式新增至此元素。

>[!NOTE]
>
>顯示內容本身時，`executionMetadata`函式不會顯示。

在執行階段中，中繼資料值已新增至現有的&#x200B;**[!UICONTROL 訊息回饋事件資料集]**，並加入下列結構描述：

```
"_experience": {
  "customerJourneyManagement": {
    "messageExecution": {
      "metadata": {
        "your_key": "your_value"
      }
    }
  }
}
```

>[!IMPORTANT]
>
>每個動作的機碼值組有2kb的上限。 如果超過2Kb限制，訊息仍會傳送，但任何索引鍵值配對都可能遭截斷。

**範例**

```
{{executionMetadata key="firstName" value=profile.person.name.firstName}}
```

在此範例中，假設`profile.person.name.firstName` = &quot;Alex&quot;，則產生的實體為：

```
{
  "key": "firstName",
  "value": "Alex"
}
```

+++

## 地圖函式 {#maps}

在個人化中使用地圖功能，讓與地圖的互動更容易。

### get {#get}

使用`get`函式為指定的索引鍵擷取對應值。

+++語法

```sql
{%= get(map, string) %}
```

**範例**

下列作業取得索引鍵`example@example.com`的識別對應值。

```sql
{%= get(identityMap,"example@example.com") %}
```

+++

### 金鑰 {#keys}

使用`keys`函式為指定的對應擷取所有索引鍵。

+++語法

```sql
{%= keys(map) %}
```

**範例**

下列作業會擷取對應`identityMap`的所有索引鍵。

```sql
{%= keys(identityMap) %}
```

+++

### 值 {#values}

`values`函式用於擷取給定對應的所有值。

+++語法

```sql
{%= values(map) %}
```

**範例**

下列作業會擷取對應`identityMap`的所有值。

```sql
{%= values(identityMap) %}
```

+++

## 數學函式 {#math}

瞭解如何在個人化編輯器中使用數學函式。

### 絕對 {#absolute}

使用`absolute`函式將數字轉換為其絕對值。

+++語法

```sql
{%= absolute(int) %}: int
```

+++

### formatnumber {#format-number}

使用`formatNumber`函式將任何數字格式化成語言感應式表示。

它接受數字和代表地區設定的字串，並傳回所需地區設定中數字的格式化字串。

+++語法

```sql
{%= formatNumber(number/double,string) %}: string
```

您可以使用[Oracle檔案](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)和[支援的語言環境](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html){_blank}中概述的格式設定和有效語言環境

**範例**

此查詢會傳回對應至123456.789的阿拉伯文字格式字串作為輸入數字。

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

+++

### random {#random}

使用`random`函式傳回0到1之間的隨機值。

+++語法

```sql
{%= random() %}: double
```

+++

### roundDown {#round-down}

使用`roundDown`函式向下舍入數字。

+++語法

```sql
{%= roundDown(double) %}: double
```

+++

### 綜述 {#round-up}

使用`roundUp`函式向上舍入數字。

+++語法

```sql
{%= roundUp(double) %}: double
```

+++

### toHexString {#to-hex-string}

`toHexString`函式將任何數字轉換成其十六進位字串。

+++語法

```sql
{%= toHexString(number) %}: string
```

**範例**

此查詢傳回158的十六進位值為9e。

```sql
{%= toHexString(158) %}
```

+++

### toInt {#to-int}

使用`toInt`函式將型別（數字、雙精度浮點數、整數、長整數、浮點數、短整數、位元組、布林值、字串）轉換為整數。

+++語法

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**範例**

此查詢傳回42.6的整數值為42。

```sql
{%= toInt(42.6) %}: integer
```

+++

### toPercentage {#to-percentage}

使用`toPercentage`函式將數字轉換為百分比。

+++語法

```sql
{%= toPercentage(double) %}: string
```

+++

### toPrecision {#to-precision}

使用`toPrecision`函式將數字轉換為所需的精確度。

+++語法

```sql
{%= toPrecision(double,int) %}: string
```

+++

### toString {#to-string}

`toString`函式將任何數字轉換成其字串表示。

+++語法

```sql
{%= toString(string) %}: string
```

**範例**

此查詢傳回`"12"`。

```sql
{%= toString(12) %} 
```

+++

## 物件函式 {#objects}

查詢物件屬性或屬性的物件函式。

### isNull {#isNull}

`isNull`函式決定物件參考是否不存在。

+++語法

```sql
{%= isNull(object) %}
```

**範例**

下列作業會檢查人員的住家地址是否不存在。

```sql
{%= isNull(person.homeAddress) %}
```

+++

### isNotNull {#isNotNull}

`isNotNull`函式決定物件參考是否存在。

+++語法

```sql
{%= isNotNull(object) %}
```

**範例**

下列作業會檢查人員的住家地址是否存在。

```sql
{%= isNotNull(person.homeAddress) %}
```

+++

## 字串函式 {#string-functions}

瞭解如何在個人化編輯器中使用字串功能。

### 駝峰式大小寫 {#camelCase}

`camelCase`函式會將字串中每個字的第一個字母大寫。

+++語法

```sql
{%= camelCase(string)%}
```

**範例**

下列函式會大寫設定檔街道位址中單詞的第一個字母。

```sql
{%= camelCase(profile.homeAddress.street) %}
```

+++

### charCodeAt {#char-code-at}

`charCodeAt`函式傳回字元的ASCII值，例如JavaScript中的`charCodeAt`函式。 它以字串和整數（定義字元的位置）作為輸入引數，並傳回其對應的ASCII值。

+++語法

```sql
{%= charCodeAt(string,int) %}: int
```

**範例**

下列函式傳回`o` (111)的ASCII值。

```sql
{%= charCodeAt("some", 1)%}
```

+++

### concat {#concate}

`concat`函式將兩個字串合併為一個。

+++語法

```sql
{%= concat(string,string) %}
```

**範例**

下列函式將個人資料城市和國家/地區結合為單一字串。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

+++

### 包含 {#contains}

使用`contains`函式來判斷字串是否包含指定的子字串。

+++語法

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `STRING_1` | 執行檢查的字串。 |
| `STRING_2` | 要在第一個字串中搜尋的字串。 |
| `CASE_SENSITIVE` | 選擇性引數，用來判斷檢查是否區分大小寫。 可能的值： true （預設） / false。 |

**範例**

* 以下函式檢查設定檔名字是否包含字母A （大寫或小寫）。 如果設定檔含有此值，則會傳回`true`。 如果沒有，則會傳回`false`。

  ```sql
  {%= contains(profile.person.name.firstName, "A", false) %}
  ```

* 下列查詢會區分大小寫，判斷人員的電子郵件地址是否包含字串`2010@gm`。

  ```sql
  {%= contains(profile.person.emailAddress,"2010@gm") %}
  ```

+++

### doesNotContain {#doesNotContain}

使用`doesNotContain`函式來判斷字串是否不包含指定的子字串。

+++語法

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引數 | 說明 |
| --------- | ----------- |
| `STRING_1` | 執行檢查的字串。 |
| `STRING_2` | 要在第一個字串中搜尋的字串。 |
| `CASE_SENSITIVE` | 選擇性引數，用來判斷檢查是否區分大小寫。 可能的值： true （預設） / false。 |

**範例**

下列查詢會區分大小寫，判斷個人的電子郵件地址是否不包含字串`2010@gm`。

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```

+++

### doesNotEndWith {#doesNotEndWith}

使用`doesNotEndWith`函式來判斷字串的結尾是否不是指定的子字串。

+++語法

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個字串中搜尋的字串。 |
| `{CASE_SENSITIVE}` | 選擇性引數，用來判斷檢查是否區分大小寫。 可能的值： true （預設） / false。 |

**範例**

下列查詢會區分大小寫判斷此人的電子郵件地址是否以`.com`結尾。

```sql
doesNotEndWith(person.emailAddress,".com")
```

+++

### doesNotStartWith {#doesNotStartWith}

使用`doesNotStartWith`函式來判斷字串是否不是以指定的子字串開頭。

+++語法

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個字串中搜尋的字串。 |
| `{CASE_SENSITIVE}` | 選擇性引數，用來判斷檢查是否區分大小寫。 可能的值： true （預設） / false。 |

**範例**

下列查詢會區分大小寫判斷人員名稱是否不是以`Joe`開頭。

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

+++

### encode64 {#encode64}

使用`encode64`函式來編碼字串以保留個人資訊(PI)，例如包含在URL中。

+++語法

```sql
{%= encode64(string) %}
```

+++

### endsWith {#endsWith}

使用`endsWith`函式來判斷字串的結尾是否為指定的子字串。

+++語法

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個字串中搜尋的字串。 |
| `{CASE_SENSITIVE}` | 選擇性引數，用來判斷檢查是否區分大小寫。 可能的值： true （預設） / false。 |

**範例**

下列查詢會區分大小寫判斷此人的電子郵件地址是否以`.com`結尾。

```sql
{%= endsWith(person.emailAddress,".com") %}
```

+++

### 等於 {#equals}

使用`equals`函式來判斷字串是否等於指定的字串，且區分大小寫。

+++語法

```sql
{%= equals(STRING_1, STRING_2) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要與第一個字串進行比較的字串。 |

**範例**

下列查詢會區分大小寫判斷人員名稱是否為`John`。

```sql
{%=equals(profile.person.name,"John") %}
```

+++

### equalsIgnoreCase {#equalsIgnoreCase}

使用`equalsIgnoreCase`函式來判斷字串是否等於指定的字串，不區分大小寫。

+++語法

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要與第一個字串進行比較的字串。 |

**範例**

下列查詢在沒有區分大小寫的情況下決定人員名稱是否為`John`。

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

+++

### extractEmailDomain {#extractEmailDomain}

使用`extractEmailDomain`函式來擷取電子郵件地址的網域。

+++語法

```sql
{%= extractEmailDomain(string) %}
```

**範例**

以下查詢會擷取個人電子郵件地址的電子郵件網域。

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

+++

### formatCurrency {#format-currency}

使用`formatCurrency`函式，根據第二個引數中作為字串傳遞的區域設定，將任何數字轉換成其對應的語言敏感型貨幣表示法。

+++語法

```sql
{%= formatCurrency(number/double,string) %}: string
```

**範例**

此查詢傳回56.00英鎊

```sql
{%= formatCurrency(56L,"en_GB") %}
```

+++

### getUrlHost {#get-url-host}

使用`getUrlHost`函式來擷取URL的主機名稱。

+++語法

```sql
{%= getUrlHost(string) %}: string
```

**範例**

```sql
{%= getUrlHost("https://www.myurl.com/contact") %}
```

傳回「www.myurl.com」

+++

### getUrlPath {#get-url-path}

使用`getUrlPath`函式在URL的網域名稱后面擷取路徑。

+++語法

```sql
{%= getUrlPath(string) %}: string
```

**範例**

```sql
{%= getUrlPath("https://www.myurl.com/contact.html") %}
```

傳回「/contact.html」

+++

### getUrlProtocol {#get-url-protocol}

使用`getUrlProtocol`函式擷取URL的通訊協定。

+++語法

```sql
{%= getUrlProtocol(string) %}: string
```

**範例**

```sql
{%= getUrlProtocol("https://www.myurl.com/contact.html") %}
```

傳回&quot;http&quot;

+++

### indexOf {#index-of}

使用`indexOf`函式傳回第二個引數第一次出現的位置（在第一個引數中）。 如果沒有相符專案，則傳回–1。

+++語法

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個引數中搜尋的字串 |

**範例**

```sql
{%= indexOf("hello world","world" ) %}
```

傳回6。

+++

### IsEmpty {#isEmpty}

使用`isEmpty`函式來判斷字串是否為空白。

+++語法

```sql
{%= isEmpty(string) %}
```

**範例**

如果設定檔的行動電話號碼空白，則以下函式會傳回「true」。 否則，它會傳回`false`。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

+++

### isNotEmpty {#is-not-empty}

使用`isNotEmpty`函式來判斷字串是否不是空的。

+++語法

```sql
{= isNotEmpty(string) %}: boolean
```

**範例**

如果設定檔的行動電話號碼非空白，則以下函式會傳回「true」。 否則，它會傳回`false`。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

+++

### lastIndexOf {#last-index-of}

使用`lastIndexOf`函式傳回第二個引數最後一次出現的位置（在第一個引數中）。 如果沒有相符專案，則傳回–1。

+++語法

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個引數中搜尋的字串 |

**範例**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

傳回7。

+++

### leftTrim {#leftTrim}

使用`leftTrim`函式移除字串開頭的空格。

+++語法

```sql
{%= leftTrim(string) %}
```

+++

### length {#length}

使用`length`函式取得字串或運算式中的字元數。

+++語法

```sql
{%= length(string) %}
```

**範例**

下列函式傳回設定檔城市名稱的長度。

```sql
{%= length(profile.homeAddress.city) %}
```

+++

### 按讚 {#like}

使用`like`函式來判斷字串是否符合指定的模式。

+++語法

```sql
{%= like(STRING_1, STRING_2) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 比對第一個字串的運算式。 建立運算式有兩個支援的特殊字元： `%`和`_`。 <ul><li>`%`用於表示零個或多個字元。</li><li>`_`只代表一個字元。</li></ul> |

**範例**

下列查詢會擷取設定檔所在且包含模式`es`的所有城市。

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

+++

### 小寫 {#lower}

使用`lowerCase`函式將字串轉換為小寫字母。

+++語法

```sql
{%= lowerCase(string) %}
```

**範例**

此函式將設定檔名字轉換為小寫字母。

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

+++

### matches {#matches}

使用`matches`函式來判斷字串是否符合特定的規則運算式。 如需規則運算式中比對模式的詳細資訊，請參閱[Oracle檔案](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)。

+++語法

```sql
{%= matches(STRING_1, STRING_2) %}
```

**範例**

下列查詢在沒有區分大小寫的情況下決定人員名稱是否以`John`開頭。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

+++

### 遮色片 {#mask}

使用`mask`函式將字串的一部分取代為「X」字元。

+++語法

```sql
{%= mask(string,integer,integer) %}
```

**範例**

下列查詢會將「123456789」字串取代為「X」字元，前兩個字元和最後兩個字元除外。

```sql
{%= mask("123456789",1,2) %}
```

查詢傳回`1XXXXXX89`。

+++

### md5 {#md5}

使用`md5`函式計算並傳回字串的md5雜湊。

+++語法

```sql
{%= md5(string) %}: string
```

**範例**

```sql
{%= md5("hello world") %}
```

傳回「5eb63bbe01eeed093cb22bb8f5acdc3」

+++

### notEqualto {#notEqualTo}

使用`notEqualTo`函式來判斷字串是否不等於指定的字串。

+++語法

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要與第一個字串進行比較的字串。 |

**範例**

下列查詢會區分大小寫判斷人員名稱是否不是`John`。

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

+++

### notEqualWithIgnoreCase {#not-equal-with-ignore-case}

使用`notEqualWithIgnoreCase`函式比較兩個字串，忽略大小寫。

+++語法

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要與第一個字串進行比較的字串。 |

**範例**

下列查詢會判斷人員名稱是否不是`john`，不區分大小寫。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

+++

### regexgroup {#regexGroup}

根據提供的規則運算式，使用`regexGroup`函式來擷取特定資訊。

+++語法

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING}` | 執行檢查的字串。 |
| `{EXPRESSION}` | 比對第一個字串的規則運算式。 |
| `{GROUP}` | 要比對的運算式群組。 |

**範例**

以下查詢會從電子郵件地址中擷取網域名稱。

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

+++

### replace {#replace}

使用`replace`函式將字串中的指定子字串取代為另一個子字串。

+++語法

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 必須取代子字串的字串。 |
| `{STRING_2}` | 要取代的子字串。 |
| `{STRING_3}` | 替代子字串。 |

**範例**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

傳回`Hello Mark, here is your monthly newsletter!`

+++

### replaceAll {#replaceAll}

使用`replaceAll`函式以指定的常值取代字串，取代符合規則運算式之文字的所有子字串。 Regex對`\`和`+`有特殊處理，並且所有regex運算式都遵循PQL逸出策略。 取代從字串的開頭到結尾進行，例如，在字串`aa`中將`b`取代為`aaa`會產生`ba`而非`ab`。

+++語法

```sql
{%= replaceAll(string,string,string) %}
```

>[!NOTE]
>
> 當當作第二個引數的運算式是特殊規則運算式字元時，請使用雙反斜線(`//`)。  特殊規則運算式字元包括：[.， +， *， ？， ^， $， (， )， [，]， {， }， |， \.]
> 
> 進一步瞭解[Oracle檔案](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}。
>

+++

### rightTrim {#rightTrim}

`rightTrim`函式移除字串結尾的空格。

+++語法

```sql
{%= rightTrim(string) %}
```

+++

### sha256 {#sha256}

`sha256`函式計算並傳回字串的sha256雜湊。

+++語法

```sql
{%= sha256(string) %} : string
```

**範例**

```sql
{%= sha256("Eliechxh")%}
```

傳回`0b0b207880b999adaad6231026abf87caa30760b6f326b21727b61139332257d`

+++

### split {#split}

使用`split`函式依指定字元分割字串。

+++語法

```sql
{%= split(string,string) %}
```

+++

### startsWith {#startsWith}

使用`startsWith`函式來判斷字串的開頭是否為指定的子字串。

+++語法

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引數 | 說明 |
| --------- | ----------- |
| `{STRING_1}` | 執行檢查的字串。 |
| `{STRING_2}` | 要在第一個字串中搜尋的字串。 |
| `{CASE_SENSITIVE}` | 選擇性引數，用來判斷檢查是否區分大小寫。 預設為true。 |

**範例**

下列查詢會區分大小寫判斷人員名稱是否以`Joe`開頭。

```sql
{%= startsWith(person.name,"Joe") %}
```

+++

### stringToDate {#string-to-date}

`stringToDate`函式將字串值轉換為日期時間值。 它需要兩個引數：日期時間的字串表示和格式化程式的字串表示。

+++語法

```sql
{= stringToDate("date-time value","formatter" %}
```

**範例**

```sql
{= stringToDate("2023-01-10 23:13:26", "yyyy-MM-dd HH:mm:ss") %}
```

+++

### string_to_integer {#string-to-integer}

使用`string_to_integer`函式將字串值轉換為整數值。

+++語法

```sql
{= string_to_integer(string) %}: int
```

+++

### stringToNumber {#string-to-number}

使用`stringToNumber`函式將字串轉換為數字。 對於無效的輸入，它會傳回相同字串作為輸出。

+++語法

```sql
{%= stringToNumber(string) %}: double
```

+++

### substr {#sub-string}

使用`substr`函式傳回開始索引和結束索引之間的字串運算式的子字串。

+++語法

```sql
{= substr(string, integer, integer) %}: string
```

+++

### titleCase {#titleCase}

使用`titleCase`函式將字串中每個字詞的首字母大寫。

+++語法

```sql
{%= titleCase(string) %}
```

**範例**

如果人員住在華盛頓大街，此函式會傳回`Washington High Street`。

```sql
{%= titleCase(profile.person.location.Street) %}
```

+++

### toBool {#to-bool}

使用`toBool`函式將引數值轉換為布林值（視其型別而定）。

+++語法

```sql
{= toBool(string) %}: boolean
```

+++

### toDateTime {#to-date-time}

使用`toDateTime`函式將字串轉換為日期。 針對無效輸入會傳回epoch日期作為輸出。

+++語法

```sql
{%= toDateTime(string, string) %}: date-time
```

+++

### toDateTimeOnly {#to-date-time-only}

使用`toDateTimeOnly`函式將引數值轉換為僅日期時間值。 針對無效輸入會傳回epoch日期作為輸出。 此函式接受字串、日期、長欄位和整數欄位型別。

+++語法

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

+++

### trim {#trim}

`trim`函式會移除字串開頭和結尾的所有空格。

+++語法

```sql
{%= trim(string) %}
```

+++

### 大寫 {#upper}

`upperCase`函式將字串轉換為大寫字母。

+++語法

```sql
{%= upperCase(string) %}
```

**範例**

此函式將設定檔姓氏轉換為大寫字母。

```sql
{%= upperCase(profile.person.name.lastName) %}
```

+++

### urlDecode {#url-decode}

使用`urlDecode`函式將url編碼的字串解碼。

+++語法

```sql
{%= urlDecode(string) %}: string
```

+++

### urlEncode {#url-encode}

使用`urlEncode`函式將字串編碼為URL。

+++語法

```sql
{%= urlEncode(string) %}: string
```

+++
