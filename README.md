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
