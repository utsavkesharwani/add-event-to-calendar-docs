# Yahoo

## Official documentation
There is no official documentation.

## Basic URL
`https://calendar.yahoo.com/`

[Add a test event](https://calendar.yahoo.com/?v=60&st=st20201231T193000&DUR=0200&desc=With%20clowns%20and%20stuff&in_loc=North%20Pole)

## Parameters

### v
required: yes

format: number

example: `v=60`

description: Must be 60. Possibly a version number?

### title
required: yes

format: date/datetime

example: `title=Birthday`

description: Event title.
Line feeds will appear in the confirmation screen, but will not be saved.
May not contain HTML.

### st
required: yes

format: datetime (ISO8601)

example: `st=20201231T193000Z`

description: Event start time. Options:
 - `20201231T193000Z`: Event start time in UTC. Will be converted to the user's time zone.
 - `20201231T193000`: Event start time in user's local time
 - `20201231`: vent start time for an all day event. `DUR` value is ignored if this form is used.


### dur
required: no

format: time (`HHmm`)

example: `dur=0200`

description: Duration of the event.
Format is HHMM, zero-padded.
MM may range up to 99, and is converted into hours appropriately.
HH values over 24 hours appear to be modulated by 24.
Durations that span midnight behave strangely.
Leave this blank if the event has no specific end time, or if this is an all-day event.

### type
required: no

format: number

example: `type=10`

description: event's type
 - 11   Anniversay
 - 10   Appointment (default)
 - 12   Bill Payment
 - 13   Birthday
 - 27   Breakfast
 - 14   Call
 - 19   Chat
 - 37   Class
 - 26   Club Event
 - 24   Concert
 - 29   Dinner
 - 15   Graduation
 - 30   Happy Hour
 - 16   Holiday
 - 17   Interview
 - 28   Lunch
 - 18   Meeting
 - 23   Movie
 - 21   Net Event
 - 20   Other
 - 31   Party
 - 32   Performance
 - 33   Reunion
 - 34   Sports Event
 - 25   Travel
 - 22   TV Show
 - 35   Vacation
 - 36   Wedding

### desc
required: no

format: text

example: `desc=With clowns and stuff`

description: description of your event.
This may contain line breaks (encoded in the usual manner, these become %0A).
This may contain HTML, but all tags will be stripped out.
This appears to accept quite a large amount of text,
considering that it is being passed through on a query string.

### URL
required: no

format: URL

example: `URL=https://example.com`

description: If present, the URL will be used to create a link out of the event title.

### in_loc
required: no

format: text

example: `in_loc=North Pole`

description: event location.

### in_st
required: no

format: text

example: `in_st=Main str.`

description: Street address.

### in_csz
required: no

format: text

example: `in_csz=Atlanta, GA, 30307`

description: City / State / Zip.

### in_ph
required: no

format: text

example: `in_ph=404-589-1228`

description: Phone.

### RPAT
required: no

format: text

example: `RPAT=01Wk`

description: Used to specify a recurring event.
If this is present, then `REND` is also required.
Examples:
 - Day: `01Dy`
 - Week: `01Wk`
 - Month: `01Mh`
 - Year: `01Yr`
 - Mon Wedn Fri: `01MoWeFr`
 - Tues Thurs: `01TuTh`
 - Mon – Fri: `01MoTuWeThFr`
 - Sat – Sun: `01SuSa`


### REND
required: no (yes if `RPAT` specified)

format: datetime (`YYYYMMDD`)

example: `REND=20191231`

description: Used to specify when a recurring event pattern ends.
Date format: `YYYYMMDD`

 
