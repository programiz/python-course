# Python `datetime` module

**Video link:** [https://youtu.be/r1Iv4d6CO2Q](https://youtu.be/r1Iv4d6CO2Q)

In this video, we learned about the `datetime` module to manipulate date and time in Python.

**Programs in the Video**

- [Get Current Date](#get-current-date)
- [The datetime.date Class](#the-datetimedate-class)
- [The datetime.time Class](#the-datetimetime-class)
- [The datetime.datetime Class](#the-datetimedatetime-class)
- [Getting current date and time](#getting-current-date-and-time)
- [The datetime.timedelta Class](#the-datetimetimedelta-class)
- [Python `strftime()` method](#python-strftime-method)
- [Python `strptime()` method](#python-strptime-method)

---

## Get Current Date
We can find the current local date using the `today()` method of the `date` class of the `datetime` module:

```python
import datetime as dt

current_date = dt.date.today()
print(current_date)
```

**Output**
```
2021-02-10
```

Similar to the `date` class, the `datetime` module has many other useful classes to work with date and time:

* `date` class - to work with date
* `time` class - to work with time
* `datetime` class - combination of `date` and `time` classes

---

## The datetime.date Class

The `date` class of the `datetime` module is used to create `date` objects that can store year, month and day.

```python
import datetime as dt

date1 = dt.date(2021, 1, 21)
print(date1)

print("Year:", date1.year)
print("Month:", date1.month)
print("Day:", date1.day)
```

**Output**

```
2021-01-21
Year: 2021
Month: 1
Day: 21
```

---

## The datetime.time Class

The `time` class of the `datetime` module is used to create `time` objects that can store time of day like hours, minutes, seconds, and microseconds.

The time class takes in all optional integer arguments. By default all of them are `0`.
- The first argument is hour from `0` to `24`
- The second one is minutes from `0` to `60`
- The third is seconds from `0` to `60`
- The fourth is microsecond from `0` to `999999`

```python
import datetime as dt

time1 = dt.time(10, 47, 20, 234566)
print(time1)

print("Hour:", time1.hour)
print("Minute:", time1.minute)
print("Second:", time1.second)
print("Microsecond:", time1.microsecond)

```

**Output**

```
10:47:20.234566
Hour: 10
Minute: 47
Second: 20
Microsecond: 234566
```

>**Note:** If you want more control and functionalities on time, use the `time` module.

---

## The datetime.datetime Class

The `datetime` class of the `datetime` module is used to create objects that contain all the information from a `date` object as well as a `time` object.

```python
import datetime as dt
datetime_obj = dt.datetime(2021, 11, 28, 23, 55, 59)

print(datetime_obj)

print(datetime_obj.date())
print(datetime_obj.time())
```

**Output**
```
2021-11-28 23:55:59
2021-11-28
23:55:59
```

Like with `date` and `time` objects, we can also access individual attributes like `year`, `month` and `hour` as previously discussed.

---

## Getting current date and time

To get the current local date and time at once, we can use the `now()` method of the `datetime` object.

```python
import datetime as dt

current_time = dt.datetime.now()

print(current_time)
```

**Output**
```
2021-01-21 05:56:45.817533
```

---

## The datetime.timedelta Class

A timedelta object represents the difference between two dates or times.

Let's find out the time difference between now and the next new year.

```python
import datetime as dt

current_time = dt.datetime.now()
next_new_year = dt.datetime(2022, 1, 1)

time_remaining = next_new_year - current_time

print(time_remaining)
print(type(time_remaining))
```

**Output**
```
324 days, 13:31:29.981402
<class 'datetime.timedelta'>
```

This `timedelta` object can also be added or subtracted from `datetime` objects to get new `datetime` objects.

---

## Python `strftime()` method

The `strftime()` method returns a string representing date and time for the datetime object.

There are many formats to write the date and time depending on your location.

If you are in the US, you probably use the `mm-dd-yyyy` format while if you're in the UK you will generally use the `dd-mm-yyyy` format. 

The `strftime()` method allows us to display the date and time in a custom specific format.

```python
import datetime as dt

current_datetime = dt.datetime.now()
print(current_datetime)

string_date = current_datetime.strftime("%A, %B %d, %Y")
print(string_date)
```

**Output**
```
2021-01-21 06:20:19.627086
Thursday, January 21, 2021
```

Here,
- `%A` represents the weekday name i.e. `Thursday`
- `%B` represents the month's full name
- `%d` represents the day of the month
- `%Y` represents the year

There are many other format codes:

| Directive | Meaning                                   | Example             |
|-----------|-------------------------------------------|---------------------|
| `%a`        | Abbreviated weekday name                  | Sun, Mon, ...       |
| `%A`       | Full weekday name                         | Sunday, Monday, ... |
| `%w`        | Weekday as a decimal number               | 0, 1, ..., 6        |
| `%d`        | Day of the month as a zero-padded decimal | 01, 02, ..., 31     |
| `%b`        | Abbreviated month name                    | Jan, Feb, ..., Dec  |
| `%p`        | Locale’s AM or PM                         | AM, PM              |

---

## Python `strptime()` method

The `strptime()` method converts strings to datetime objects.

```python
import datetime as dt

date_string = "21 June, 2021"

date_object = dt.datetime.strptime(date_string, "%d %B, %Y")
print("date_object:", date_object)
```

**Output**
```
date_object: 2018-06-21 00:00:00
```