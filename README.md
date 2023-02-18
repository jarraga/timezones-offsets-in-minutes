### Timezones list
---
List of all timezones obtained from browser:

```javascript
Intl.supportedValuesOf('timeZone')
```

With offset in minutes and utc text

```javascript
{
    "tzLabel": "America/Argentina/Rio_Gallegos",
    "offsetInMinutes": 180,
    "utcText": "GTM -3:00"
}
```

You can get local time using a function to add minutes with libraries like [date-fns](https://www.npmjs.com/package/date-fns)

```javascript
import { addMinutes } from "date-fns"

// get client timezone and offset
const tz = Intl.DateTimeFormat().resolvedOptions().timeZone
const tzOffset = jsonArray.find(item => item.tzLabel === tz).offsetInMinutes

// sum minutes
const localDate = addMinutes(new Date(), tzOffset)
```

