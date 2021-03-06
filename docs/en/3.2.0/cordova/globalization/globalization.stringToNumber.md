---
license: >
    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
---

# globalization.stringToNumber

Parses a number formatted as a string according to the client's user
preferences and returns the corresponding number.

    navigator.globalization.stringToNumber(string, successCallback, errorCallback, options);

## Description

Returns the number to the `successCallback` with a `properties` object
as a parameter. That object should have a `value` property with a
`Number` value.

If there is an error parsing the number string, then the
`errorCallback` executes with a `GlobalizationError` object as a
parameter. The error's expected code is
`GlobalizationError.PARSING\_ERROR`.

The `options` parameter is optional, and defaults to the following
values:

    {type:'decimal'}

The `options.type` can be `decimal`, `percent`, or `currency`.

## Supported Platforms

- Amazon Fire OS
- Android
- BlackBerry WebWorks 5.0+
- iOS
- Windows Phone 8

## Quick Example

When the browser is set to the `en\_US` locale, this should display a
popup dialog with text similar to `number: 1234.56`:

    navigator.globalization.stringToNumber(
        '1234.56',
        function (number) {alert('number: ' + number.value + '\n');},
        function () {alert('Error getting number\n');},
        {type:'decimal'}
    );

## Full Example

    <!DOCTYPE HTML>
    <html>
      <head>
        <title>stringToNumber Example</title>
        <script type="text/javascript" charset="utf-8" src="cordova.js"></script>
        <script type="text/javascript" charset="utf-8">

        function checkNumber() {
          navigator.globalization.stringToNumber(
            '1234.56',
            function (number) {alert('number: ' + number.value + '\n');},
            function () {alert('Error getting number\n');},
            {type:'decimal'}
          );
        }

        </script>
      </head>
      <body>
        <button onclick="checkNumber()">Click for parsed number</button>
      </body>
    </html>

