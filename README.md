# phpdatetimeapp

### Application implementing date and time functionality in PHP

I used the Carbon API to make this app. To make this app work,, you will need to include the 
carbon files in your project. There are two ways you can add the files: Manually or by using composer. I'd recommend using composer because it makes work so much easier.

## Installation

### With Composer

```
$ composer require nesbot/carbon
```

```json
{
    "require": {
        "nesbot/carbon": "~1.21"
    }
}
```

```php
<?php
require 'vendor/autoload.php';

use Carbon\Carbon;

printf("Now: %s", Carbon::now());
```

<a name="install-nocomposer"/>
### Without Composer

Why are you not using [composer](http://getcomposer.org/)? Download [Carbon.php](https://github.com/briannesbitt/Carbon/blob/master/src/Carbon/Carbon.php) from the repo and save the file into your project path somewhere.

```php
<?php
require 'path/to/Carbon.php';

use Carbon\Carbon;

printf("Now: %s", Carbon::now());
```
I've given a few examples on [index.php](https://github.com/masterimpaler/phpdatetimeapp/blob/master/index.php). But I'll list them here as well.

```php
//creating an object
$date = new Carbon();
//outputs the date object created above
var_dump($date);
echo "<br>";

//displays todays date
echo $date->today();
echo "<br>";

// can show dates in the following format
echo $date->format('d M Y');
echo "<br>";

echo $date->format('D M Y');
echo "<br>";

/*HINT: The d m y initals display different when you change case. Play around with their cases and see the effect*/

//create a new object. Enter your own values between the quotation marks.
$date2 = new Carbon('+10 days');

//really cool stuff. Reads the object and gives you sweet human friendly date/time versions. 
echo $date2->diffForHumans();
echo "<br>";
echo "<br>";
echo "<br>";

/*
 * CARBON GETTERS: Grabbing sections of the date. Eg Month only, year only, etc 
 *  
 */
echo "CARBON GETTERS" . "<br><br>";
$date = Carbon::now();

echo "Month: ";
echo $date->month;
echo "<br>";
echo 'Year: ';
echo $date->year;
echo "<br>";
echo 'Day: ';
echo $date->day;
echo "<br>";
echo 'Day of Week: ';
echo $date->dayOfWeek;
echo "<br>";
echo 'Hour: ';
echo $date->hour;
echo "<br>";
echo 'Quarter: ';
echo $date->quarter;
echo "<br>";
echo 'Day of Year: ';
echo $date->dayOfYear;
echo "<br>";
echo 'Timestamp: ';
echo $date->timestamp;
echo "<br><br>";

//You can even get someones age if you know when they were born. Pass in their date to the following function

echo "Get a persons age given their birth dates.";
echo "<br>";

$date3 = new Carbon('30th August 1980');
echo $date3->age;
echo "<br>";

// OR you can use this different format.

$date4 = new Carbon('1990-6-17');
echo $date4->age;
echo "<br><br>";

/*
 * Setting date on object 
 *  */

echo "SETTING DATE ON OBJECT";
echo "<br><br>";

$setdate = new Carbon();

$setdate->day = 8;
$setdate->month = 7;
$setdate->year = 2016;

var_dump($setdate);
echo "<br>";

//buh thats a lot of work. This does the same thing. :)

$setdate2 = new Carbon();
$setdate2->setDate(2013, 5, 4);
var_dump($setdate2);
echo "<br>";

//other options to explowe: setTime, setDateTime...

