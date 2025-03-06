![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-21 17:30:38 | rand=27700

Auto-commit on 2025-02-21 17:42:35 | rand=74858

Auto-commit on 2025-02-21 17:54:33 | rand=85566

Auto-commit on 2025-02-21 18:06:34 | rand=75109

Auto-commit on 2025-02-22 00:24:50 | rand=7003

Auto-commit on 2025-02-22 00:36:59 | rand=63445

Auto-commit on 2025-02-22 00:49:01 | rand=52133

Auto-commit on 2025-02-22 01:01:03 | rand=69581

Auto-commit on 2025-02-22 01:13:05 | rand=55694

Auto-commit on 2025-02-22 01:25:13 | rand=53909

Auto-commit on 2025-02-22 01:37:12 | rand=1280

Auto-commit on 2025-02-22 01:49:18 | rand=58930

Auto-commit on 2025-02-22 02:01:16 | rand=87236

Auto-commit on 2025-02-22 02:13:25 | rand=478

Auto-commit on 2025-02-22 02:25:31 | rand=87901

Auto-commit on 2025-02-22 02:37:41 | rand=34424

Auto-commit on 2025-02-22 02:49:44 | rand=22279

Auto-commit on 2025-02-22 03:01:56 | rand=25363

Auto-commit on 2025-02-22 03:14:06 | rand=78903

Auto-commit on 2025-02-22 14:54:00 | rand=35298

Auto-commit on 2025-02-22 15:06:06 | rand=8623

Auto-commit on 2025-02-22 15:18:11 | rand=85920

Auto-commit on 2025-02-22 15:30:17 | rand=6716

Auto-commit on 2025-02-22 15:42:17 | rand=63751

Auto-commit on 2025-02-22 15:54:23 | rand=51716

Auto-commit on 2025-02-22 16:06:29 | rand=57780

Auto-commit on 2025-02-22 16:18:28 | rand=98902

Auto-commit on 2025-02-22 16:30:28 | rand=48485

Auto-commit on 2025-02-22 16:42:29 | rand=62996

Auto-commit on 2025-02-22 16:54:33 | rand=74184

Auto-commit on 2025-02-22 17:06:33 | rand=52171

Auto-commit on 2025-02-22 17:18:43 | rand=69640

Auto-commit on 2025-02-22 17:30:44 | rand=53463

Auto-commit on 2025-02-22 17:42:49 | rand=62979

Auto-commit on 2025-02-24 13:57:37 | rand=90254

Auto-commit on 2025-02-24 14:09:39 | rand=24752

Auto-commit on 2025-02-24 14:21:39 | rand=60110

Auto-commit on 2025-02-24 14:33:46 | rand=90027

Auto-commit on 2025-02-24 14:45:53 | rand=85457

Auto-commit on 2025-02-24 14:57:53 | rand=16871

Auto-commit on 2025-02-24 15:09:59 | rand=29730

Auto-commit on 2025-02-24 15:22:03 | rand=90041

Auto-commit on 2025-02-24 15:34:12 | rand=15925

Auto-commit on 2025-02-24 15:46:22 | rand=71689

Auto-commit on 2025-02-24 15:58:32 | rand=34524

Auto-commit on 2025-02-24 16:10:32 | rand=62745

Auto-commit on 2025-02-24 16:22:28 | rand=67236

Auto-commit on 2025-02-24 16:34:35 | rand=16326

Auto-commit on 2025-02-24 16:46:40 | rand=22832

Auto-commit on 2025-02-24 17:58:53 | rand=44897

Auto-commit on 2025-02-24 18:10:54 | rand=61679

Auto-commit on 2025-02-24 18:22:56 | rand=40140

Auto-commit on 2025-02-24 18:35:04 | rand=56213

Auto-commit on 2025-02-24 18:47:11 | rand=99231

Auto-commit on 2025-02-24 18:59:15 | rand=60621

Auto-commit on 2025-02-24 19:11:26 | rand=98721

Auto-commit on 2025-02-24 19:23:30 | rand=25523

Auto-commit on 2025-02-24 19:35:29 | rand=41447

Auto-commit on 2025-02-24 19:47:30 | rand=20909

Auto-commit on 2025-02-24 19:59:35 | rand=96882

Auto-commit on 2025-02-24 20:11:40 | rand=7361

Auto-commit on 2025-02-24 20:23:45 | rand=99109

Auto-commit on 2025-02-24 20:35:48 | rand=6959

Auto-commit on 2025-02-24 20:47:47 | rand=25312

Auto-commit on 2025-02-25 12:21:31 | rand=81687

Auto-commit on 2025-02-25 12:33:31 | rand=78278

Auto-commit on 2025-02-25 12:45:39 | rand=69144

Auto-commit on 2025-02-25 12:57:40 | rand=79709

Auto-commit on 2025-02-25 13:09:42 | rand=56151

Auto-commit on 2025-02-25 13:21:50 | rand=13694

Auto-commit on 2025-02-25 13:33:57 | rand=12892

Auto-commit on 2025-02-25 13:45:55 | rand=41184

Auto-commit on 2025-02-25 13:57:59 | rand=49753

Auto-commit on 2025-02-25 14:10:00 | rand=20046

Auto-commit on 2025-02-25 14:22:07 | rand=10309

Auto-commit on 2025-02-25 14:34:10 | rand=61810

Auto-commit on 2025-02-25 14:46:17 | rand=59664

Auto-commit on 2025-02-25 14:58:21 | rand=41278

Auto-commit on 2025-02-25 15:10:28 | rand=42324

Auto-commit on 2025-03-06 14:51:28 | rand=7171

Auto-commit on 2025-03-06 15:02:52 | rand=25651

Auto-commit on 2025-03-06 15:14:09 | rand=94880

Auto-commit on 2025-03-06 15:50:34 | rand=23039

Auto-commit on 2025-03-06 16:01:49 | rand=76641

Auto-commit on 2025-03-06 16:13:08 | rand=85780

Auto-commit on 2025-03-06 16:24:24 | rand=86284

Auto-commit on 2025-03-06 16:35:42 | rand=91110

Auto-commit on 2025-03-06 16:46:59 | rand=3422

Auto-commit on 2025-03-06 16:58:17 | rand=91066

Auto-commit on 2025-03-06 19:58:30 | rand=20796

Auto-commit on 2025-03-06 20:38:34 | rand=7543

Auto-commit on 2025-03-06 20:50:19 | rand=27757

Auto-commit on 2025-03-06 21:01:43 | rand=39624
