Calculating weekday for a given date

# Weekday of a given date

### Year Code
Given YY, the last 2 digits of the year (for 1986, YY = 86)
```js
var yearCode = (YY + Math.floor((YY / 4))) % 7
```

### Month Code

```js
var month = 2 // february
const monthCodes = [0, 3, 3, 6, 1, 4, 6, 2, 5, 0, 3, 5];
var monthCode = monthCodes[month-1];
```

### Century Code
Given CC, the first 2 digits of the year(for 1986, CC = 19)
```js
centuryCode = CC % 4;
switch (centuryCode) {
    case 0:
        centuryCode = 6;
        break;
    case 1:
        centuryCode = 4;
        break;
    case 2:
        centuryCode = 2;
        break;
    case 3:
        centuryCode = 0;
        break;
}
```

### Leap Year Code
If the year is leap and date is in january / february, subtract one from the total right before returning
```js
var leapYearCode = 0;
if (isLeap(year)) leapYearCode = 1;
```

### Final Calculation
```js
const dayOfTheWeek = (yearCode + monthCode + centuryCode + day - leapYearCode) % 7;
```