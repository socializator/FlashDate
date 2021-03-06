# CookieSession

**CookieSession** is a very light library to manage easily and simply the Session and Cookie with PHP 7+ (and without spending time by configuring and securing them).


## Composer Installation

 You can add it easily in your projec by using [Composer](https://getcomposer.org/).


```bash
$ composer require ph-7/cookiesession
 ```

Then, include Composer's autoload

```PHP
require_once 'vendor/autoload.php';
```

## Manual Installation

If you don't use Composer, you can install it without Composer by including the following

```PHP
require 'src/autoloader.php';
```


## Usage for Session

```PHP
<?php
use PH7\CookieSession\Session\Session;

$oSession = new Session;

$oSession->set('lang_pref', 'English');

// Create some sessions with an array
$aData = [
    'my_session' => 'The value',
    'another_session' => 'Another value',
    'my_name' => 'Pierre-Henry'
];
// Add these sessions
$oSession->set($aData);


// Get session
echo $oSession->get('lang_pref'); // Will display 'English'
echo $oSession->get('another_session'); // Will display 'Another value'

echo ($oSession->exists('my_name')) ? $oSession->get('my_name') : 'Well, well, we dont have a name in the session'; // Will display 'Pierre-Henry'

$oSession->remove('my_name'); // Remove 'my_name' session

echo $oSession->get('my_name'); // Will display nothing (empty string) as 'my_name' session has been removed
```


## Usage with Cookie (very similar)

```PHP
<?php
use PH7\CookieSession\Cookie\Cookie;

$oCookie = new Cookie;

$oCookie->set('mycookie', 'Amazing Value!');

// Create some cookies in array
$aCookies = [
    'name' => 'Pierre-Henry',
    'city' => 'Manchester',
    'job' => 'Software Engineer'
];
$oCookie->set($aCookies);

if ($oCookie->exists($aCookies)) {
    echo 'All the following cookies exist: ' . implode(', ', $aCookies);
}

echo $oCookie->get('name'); // Will display 'Pierre-Henry'
echo $oCookie->get('mycookie'); // Will display 'Amazing Value!'

$oCookie->remove($aCookies); // Remove all cookies

echo $oCookie->get('name');  // Will display nothing (empty string)

```


## Requirements

- PHP 7 or higher


## The Author

I'm **Pierre-Henry Soria**, **Software Developer** passionate about a lot of things and currently living in Manchester city, UK


## Contact

You can send an email at **pierrehenrysoria [AT] gmail {D0T} COM** or at **phy {AT} hizup [D0T] UK**


## License

Under [General Public License 3](http://www.gnu.org/licenses/gpl.html) or later.