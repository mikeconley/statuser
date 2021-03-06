#Statuser
Statuser tracks user status in Firefox. You can get it here:
https://chutten.github.io/statuser/dist/

The current version is 0.0.7.

* If the user is considered active, it will take the shape of a red square.
* If the user is considered inactive, it will take the shape of a blue circle.
* If there is a toplevel navigation load happening, it will spin.
* If there has been a Gecko-main event delay longer than the specified threshold (see below), the badge counter will increment and change colour.

Click the Statuser button to access settings:

* **Count thread hangs**: choose this option to count the number of times the main thread stopped for too long.
    * Changing this value will clear the count.
* **Count event loop lags**: choose this option to count the number of times the event loop takes too long.
    * Changing this value will clear the count.
* **Minimum hang threshold**: the minimum number of milliseconds before a hang/lag is added to the count. Hangs/lags shorter than this are ignored.
    * Note that this value is rounded up to the nearest histogram bucket. That means the actual threshold may be somewhat higher.
* **Clear count**: reset the badge counter to 0.

Development
-----------

To build the extension, use `jpm xpi`. To build an XPI for distribution, simply run `./build.sh`.

When changing version numbers, make sure to update them in the following places:

* In paragraph 2 of this README.
* In `package.json`, under `version`.
* In `dist/update.rdf`, under `em:version`.
* In the link to the XPI for `dist/index.html`.
