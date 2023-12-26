# Day 1: Days alive calculator challenge

For today's challenge you need to create a program that asks someone for their date of birth as separate numbers. For example ask them for their day of birth, then their month of birth and finally their year of birth. Your program will need to display on the screen how many days they have been alive.

## Step 1: Getting their date of birth

We're going to use the `input` function to ask the user for their date of birth 3 times (day, month and year). You can find out more information about this function here: (https://docs.python.org/3/library/functions.html#input). The `input` function takes one argument (which is what you want the user to see on the screen to prompt them to do something), for example:

```
name = input("Please enter your name: ")
```

Python will return the users input as a string, so if you're expecting a number you'll need to convert it to a number first.

# Step 2: Calculating number of days

Calculating dates is quite tricky, there are different days in a month and your calculation might change depending on where we currently are in the year. You could take the number of whole years inbetween and multiply it by 365 and try to add on the remaining days but it gets messy. Don't forget about leap years!

Fortunately, Python has a special `datetime` function which can do all of this for you. You can find out more information about this here: (https://docs.python.org/3/library/datetime.html#datetime-objects)

At this point you should have you date as 3 separate numbers. This isn't a date yet, so we'll have to convert it. To convert it you need to pass in the 3 numbers into `datetime`:

```
date = datetime(year, month, day)
```

So long as each of the 3 numbers are valid (i.e. month is between 1-12, etc), the `date` variable will contain your date.

We have one date but we need two dates to calculate the difference in days. Think about what we are doing, what would the other date be? It needs to be today's date. We don't need to tell Python what today's date is, it already knows. You can use `datetime.now()` and read more about this here: (https://docs.python.org/3/library/datetime.html#datetime.datetime.now)

Finally, we can work out the number of days. Think about how we can do this, forget for a moment that these are 2 dates a pretend they're just numbers, what would we do? In maths we can work out the difference by subtracting the bigger number from the smaller number (in our case the bigger number will be today's date and the smaller number would be the entered date):

```
difference = now - date
```

`difference` won't be a date because it's the difference between the two dates, Python calls this a `timedelta` which you can read more about here: (https://docs.python.org/3/library/datetime.html#timedelta-objects). You don't need to understand how to use this, simply know we can read from it and find out useful information.

```
difference.days          # how many days different
difference.seconds       # how many seconds different
difference.microseconds  # how many micro seconds different
difference.milliseconds  # how many milliseconds different
difference.minutes       # how many minutes different
difference.hours         # how many hours different
difference.weeks         # how many weeks different
```

So for the number of days we can just say `difference.days` to get our answer.

# Step 3: Tell the user how many days

We need to tell the user how many days they've been alive for. To display text on the screen we can use a function called `print` which you can find out more here: (https://docs.python.org/3/library/functions.html#print)

`print` works by placing what you want to display inside `""` so for example `print("MY MESSAGE")` and we can also join things we want to display together for example `print("My name is " + name)` this is called concatenation.

# Step 4: Running the code

```
python day_1/code.py
```

