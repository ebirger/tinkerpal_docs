API
===

Objects and methods detailed below

Global
======

eval
----

Evaluate the given String

Example
~~~~~~~

::

    var two = eval('1+1');

+------------------+--------------------------+
| Parameter Name   | Description              |
+==================+==========================+
| str              | String to be evaluated   |
+------------------+--------------------------+

toInteger
---------

Convert the given object to an integer value

Example
~~~~~~~

::

    var n = toInteger('5') + 1;

+------------------+--------------------------+
| Parameter Name   | Description              |
+==================+==========================+
| object           | Object to be converted   |
+------------------+--------------------------+

isNaN
-----

Tests if the object is NaN

Example
~~~~~~~

::

    isNaN(1); // false
    isNaN('abc'); // true

+------------------+----------------------------------+
| Parameter Name   | Description                      |
+==================+==================================+
| number           | Object to be tested for NaNity   |
+------------------+----------------------------------+

meminfo
-------

Prints platform dependent memory information

Example
~~~~~~~

::

    meminfo()

describe
--------

Print object description to the console

Example
~~~~~~~

::

    describe(describe);

+------------------+----------------------+
| Parameter Name   | Description          |
+==================+======================+
| object           | Object to describe   |
+------------------+----------------------+

compile
-------

Compiles a function for faster execution

Example
~~~~~~~

::

    var f = compile(function() { return 1 + 1; });

+------------------+------------------------------+
| Parameter Name   | Description                  |
+==================+==============================+
| function         | function\_to\_be\_compiled   |
+------------------+------------------------------+

objGraph
--------

Create a DOT graph of allocated objects

Example
~~~~~~~

::

    objGraph()

File System
===========

readFileSync
------------

Synchronously reads the entire contents of a file

Example
~~~~~~~

::

    var s = fs.readFileSync('FAT/file.txt');

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| path             | File Path     |
+------------------+---------------+

writeFileSync
-------------

Synchronously writes the entire contents of a file

Example
~~~~~~~

::

    fs.writeFileSync('FAT/file.txt', 'hello world!');

+------------------+--------------------------------+
| Parameter Name   | Description                    |
+==================+================================+
| path             | File Path                      |
+------------------+--------------------------------+
| data             | String to be written to file   |
+------------------+--------------------------------+

readdirSync
-----------

Synchronously reads the directory listing of a path

Example
~~~~~~~

::

    var s = fs.readdirSync('FAT/');

+------------------+------------------+
| Parameter Name   | Description      |
+==================+==================+
| path             | Directory Path   |
+------------------+------------------+

Array
=====

Array (constructor)
-------------------

Array Constructor

Example
~~~~~~~

::

    var a = new Array(5);
    var b = new Array(1, 2, 3);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Leng | Numb |
| th   | er   |
| or   | of   |
| [ite | entr |
| m1,  | ies  |
| item | to   |
| 2,   | Allo |
| ..]  | cate |
|      | or   |
|      | comm |
|      | a    |
|      | sepa |
|      | rate |
|      | d    |
|      | list |
|      | of   |
|      | item |
|      | s    |
|      | to   |
|      | push |
|      | to   |
|      | the  |
|      | new  |
|      | arra |
|      | y    |
+------+------+

push
----

The arguments are appended to the end of the array, in the order in
which they appear

Example
~~~~~~~

::

    var a = [];
    a.push(1);

+----------------------------+-------------------------+
| Parameter Name             | Description             |
+============================+=========================+
| item1 [, item2 [, ...] ]   | object[s] to be added   |
+----------------------------+-------------------------+

pop
---

The last element of the array is removed from the array and returned

Example
~~~~~~~

::

    var a = [2, 1];
    var one = a.pop();

forEach
-------

Calls cb once for each element present in the array, in ascending order

Example
~~~~~~~

::

    var a = [1, 2, 3];
    a.forEach(function(value, k, obj) { console.log(value + ' [' + k + '] ' + ' @ ' + obj); });

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | func |
|      | tion |
|      | that |
|      | acce |
|      | pts  |
|      | thre |
|      | e    |
|      | argu |
|      | ment |
|      | s:Va |
|      | lue  |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | Inde |
|      | x    |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | The  |
|      | obje |
|      | ct   |
|      | bein |
|      | g    |
|      | trav |
|      | erse |
|      | d    |
+------+------+
| this | [opt |
|      | iona |
|      | l]   |
|      | if   |
|      | prov |
|      | ided |
|      | ,    |
|      | used |
|      | as   |
|      | the  |
|      | 'thi |
|      | s'   |
|      | valu |
|      | e    |
|      | for  |
|      | each |
|      | invo |
|      | cati |
|      | on   |
|      | of   |
|      | 'cb' |
|      | .    |
|      | If   |
|      | not  |
|      | prov |
|      | ided |
|      | ,    |
|      | 'und |
|      | efin |
|      | ed'  |
|      | is   |
|      | used |
+------+------+

indexOf
-------

Searches for searchElement in the elements of the array

Example
~~~~~~~

::

    var a = [1, 2, 3];
    var one = a.indexOf(2);

+------------------+---------------------------------+
| Parameter Name   | Description                     |
+==================+=================================+
| searchElement    | Object to search for            |
+------------------+---------------------------------+
| fromIndex        | [optional] start search index   |
+------------------+---------------------------------+

join
----

Joins the string coversions of the elements of the array separated by
occurrences of the separator

Example
~~~~~~~

::

    var a = [1, 2, 3];
    debug.assert(a.join('-'), '1-2-3');

+------------------+--------------------------------------------------------------+
| Parameter Name   | Description                                                  |
+==================+==============================================================+
| separator        | [optional] string. If not provided, a single comma is used   |
+------------------+--------------------------------------------------------------+

map
---

Calls cb once for each element present in the array, in ascending order,
and constructs a new Array from the results

Example
~~~~~~~

::

    var a = [1, 2, 3];
    var b = a.map(function(value, k, obj) { return value + 1 });
    debug.assert(b, [2, 3, 4]);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | func |
|      | tion |
|      | that |
|      | acce |
|      | pts  |
|      | thre |
|      | e    |
|      | argu |
|      | ment |
|      | s:Va |
|      | lue  |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | Inde |
|      | x    |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | The  |
|      | obje |
|      | ct   |
|      | bein |
|      | g    |
|      | trav |
|      | erse |
|      | d    |
+------+------+
| this | [opt |
|      | iona |
|      | l]   |
|      | if   |
|      | prov |
|      | ided |
|      | ,    |
|      | used |
|      | as   |
|      | the  |
|      | 'thi |
|      | s'   |
|      | valu |
|      | e    |
|      | for  |
|      | each |
|      | invo |
|      | cati |
|      | on   |
|      | of   |
|      | 'cb' |
|      | .    |
|      | If   |
|      | not  |
|      | prov |
|      | ided |
|      | ,    |
|      | 'und |
|      | efin |
|      | ed'  |
|      | is   |
|      | used |
+------+------+

slice
-----

Creates a new array with elements from the specified array starting from
index 'start' up to index 'end'

Example
~~~~~~~

::

    [1, 2, 3].slice(1); // [2, 3]

+------------------+--------------------------------------------------------+
| Parameter Name   | Description                                            |
+==================+========================================================+
| start            | Element index to start from, may be undefined          |
+------------------+--------------------------------------------------------+
| end              | Last element index (not inclusive), may be undefined   |
+------------------+--------------------------------------------------------+

sort
----

Sorts the array elements

Example
~~~~~~~

::

    [3, 1, 2].sort(); // [1, 2, 3]

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| comp | Func |
| aref | tion |
| n    | rece |
|      | ivin |
|      | g    |
|      | (x,  |
|      | y)   |
|      | and  |
|      | retu |
|      | rns  |
|      | a    |
|      | nega |
|      | tive |
|      | valu |
|      | e    |
|      | if x |
|      | < y, |
|      | zero |
|      | if x |
|      | = y  |
|      | or a |
|      | posi |
|      | tive |
|      | valu |
|      | e    |
|      | if x |
|      | > y  |
+------+------+

filter
------

Calls cb once for each element present in the array, in ascending order,
and constructs a new Array from any element for which cb returned 'true'

Example
~~~~~~~

::

    var a = [1, 2, 3];
    var b = a.filter(function(value) { return value > 1 });
    b; // [2, 3]

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | func |
|      | tion |
|      | that |
|      | acce |
|      | pts  |
|      | thre |
|      | e    |
|      | argu |
|      | ment |
|      | s:Va |
|      | lue  |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | Inde |
|      | x    |
|      | of   |
|      | the  |
|      | elem |
|      | ent, |
|      | The  |
|      | obje |
|      | ct   |
|      | bein |
|      | g    |
|      | trav |
|      | erse |
|      | d    |
+------+------+
| this | [opt |
|      | iona |
|      | l]   |
|      | if   |
|      | prov |
|      | ided |
|      | ,    |
|      | used |
|      | as   |
|      | the  |
|      | 'thi |
|      | s'   |
|      | valu |
|      | e    |
|      | for  |
|      | each |
|      | invo |
|      | cati |
|      | on   |
|      | of   |
|      | 'cb' |
|      | .    |
|      | If   |
|      | not  |
|      | prov |
|      | ided |
|      | ,    |
|      | 'und |
|      | efin |
|      | ed'  |
|      | is   |
|      | used |
+------+------+

concat
------

Concatanates a given array with a list of items. If an item is an array
itself, its members are used

Example
~~~~~~~

::

    var a = [1, 2, 3];
    var b = a.concat([4, 5, 6], 7); // [1, 2, 3, 4, 5, 6, 7]

+-------------------------------+-----------------------------------------+
| Parameter Name                | Description                             |
+===============================+=========================================+
| [item1 [, item2 [, item3]]]   | optional list of items to concatanate   |
+-------------------------------+-----------------------------------------+

String
======

String (constructor)
--------------------

String Constructor

Example
~~~~~~~

::

    var s = new String('hello');

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| String           | String        |
+------------------+---------------+

split
-----

Breaks a string into substrings based on occurences of 'separator'

Example
~~~~~~~

::

    var s = '1|2|3';
    var a = s.split('|');
    debug.assert(a, [ '1', '2', '3' ]);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| separator        | Delimiter     |
+------------------+---------------+

indexOf
-------

Search for occurences of 'searchString' in a given string

Example
~~~~~~~

::

    var s = 'looking for me';
    var i = s.indexOf('for');
    debug.assert(i, 8);

+------------------+------------------------+
| Parameter Name   | Description            |
+==================+========================+
| searchString     | String to search for   |
+------------------+------------------------+

substring
---------

Creates a new string based on a subset of a given string

Example
~~~~~~~

::

    var s = 'a big string';
    var big = s.substring(2, 5);

+------------------+-------------------------------------------------+
| Parameter Name   | Description                                     |
+==================+=================================================+
| start            | Character position to start from                |
+------------------+-------------------------------------------------+
| end              | Character position to end with (not including   |
+------------------+-------------------------------------------------+

charAt
------

Creates a new string containing the character at a position

Example
~~~~~~~

::

    var s = 'a string';
    var a = s.charAt(0);

+------------------+-------------------------+
| Parameter Name   | Description             |
+==================+=========================+
| pos              | Position of character   |
+------------------+-------------------------+

charCodeAt
----------

Get the ASCII value of the character at a position

Example
~~~~~~~

::

    var s = 'a string';
    var ninty_seven = s.charCodeAt(0);

+------------------+-------------------------+
| Parameter Name   | Description             |
+==================+=========================+
| pos              | Position of character   |
+------------------+-------------------------+

toLowerCase
-----------

Convert a string to lower case characters

Example
~~~~~~~

::

    var s = 'Hello World';
    s.toLowerCase(); // 'hello world'

toUpperCase
-----------

Convert a string to upper case characters

Example
~~~~~~~

::

    var s = 'Hello World';
    s.toUpperCase(); // 'HELLO WORLD'

Function
========

Function (constructor)
----------------------

Function Constructor

Example
~~~~~~~

::

    var f = new Function('a', 'b', 'return a+b');
    console.log('1+2=' + f(1, 2));

+-------------------------+--------------------------+
| Parameter Name          | Description              |
+=========================+==========================+
| [arg1, [arg2, [.. ]]]   | Formal Parameter Names   |
+-------------------------+--------------------------+
| Body                    | Function Body            |
+-------------------------+--------------------------+

call
----

Invoke function call

Example
~~~~~~~

::

    function fun() { this.prop = 'prop' }
    var obj = {};
    fun.call(obj);
    obj; // { prop : 'prop' }

+-------------------+--------------------------------------------+
| Parameter Name    | Description                                |
+===================+============================================+
| thisArg           | The 'this' value on function invocation    |
+-------------------+--------------------------------------------+
| arg1, arg2, ...   | [optional] arguments to pass to function   |
+-------------------+--------------------------------------------+

apply
-----

Invoke function call

Example
~~~~~~~

::

    function fun(a, b) { return a + b; }
    fun.apply(undefined, [1, 2]); // 3

+------------------+-----------------------------------------------------+
| Parameter Name   | Description                                         |
+==================+=====================================================+
| thisArg          | The 'this' value on function invocation             |
+------------------+-----------------------------------------------------+
| argArray         | [optional] Array of arguments to pass to function   |
+------------------+-----------------------------------------------------+

bind
----

Returns a new Function object based on the current function object, but
the 'this' value is bound to thisArg

Example
~~~~~~~

::

    function fun() { return this.prop; }
    var f = fun.bind({ prop : 1});
    f(); // 1

+------------------+-------------------------------------------+
| Parameter Name   | Description                               |
+==================+===========================================+
| thisArg          | The 'this' value on function invokation   |
+------------------+-------------------------------------------+

ArrayBuffer
===========

ArrayBuffer (constructor)
-------------------------

ArrayBuffer Constructor

Example
~~~~~~~

::

    var a = new ArrayBuffer(5);

+------------------+-----------------------------------+
| Parameter Name   | Description                       |
+==================+===================================+
| Size             | Number of bytes in Array Buffer   |
+------------------+-----------------------------------+

ArrayBufferView
===============

Int8Array (constructor)
-----------------------

Int8Array Constructor

Example
~~~~~~~

::

    var a = new Int8Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

Uint8Array (constructor)
------------------------

Uint8Array Constructor

Example
~~~~~~~

::

    var a = new Uint8Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

Int16Array (constructor)
------------------------

Int16Array Constructor

Example
~~~~~~~

::

    var a = new Int16Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

Uint16Array (constructor)
-------------------------

Uint16Array Constructor

Example
~~~~~~~

::

    var a = new Uint16Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

Int32Array (constructor)
------------------------

Int32Array Constructor

Example
~~~~~~~

::

    var a = new Int32Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

Uint32Array (constructor)
-------------------------

Uint32Array Constructor

Example
~~~~~~~

::

    var a = new Uint32Array(5);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| Arra | Arra |
| y/Ar | y,   |
| rayB | Arra |
| uffe | yBuf |
| r/Si | fer  |
| ze   | or   |
|      | Numb |
|      | er   |
|      | of   |
|      | Elem |
|      | ents |
|      | in a |
|      | newl |
|      | y    |
|      | crea |
|      | ted  |
|      | Arra |
|      | yBuf |
|      | fer  |
+------+------+

subarray
--------

Return a partial typed array based on the typed arrayIf end is
unspecified, the subarray contains all elements from begin to the end of
the TypedArray. If either begin or end are negative, they are calculated
from the end of the array

Example
~~~~~~~

::

    var a = new Int8Array(16);
    var b = a.subarray(1, 5);

+------------------+-------------------------------------+
| Parameter Name   | Description                         |
+==================+=====================================+
| begin            | Start offset (inclusive)            |
+------------------+-------------------------------------+
| end              | (Optional) End offset (exclusive)   |
+------------------+-------------------------------------+

Object
======

Object (constructor)
--------------------

Object Constructor

Example
~~~~~~~

::

    var o = new Object(5);

toString
--------

The object is converted to a string

Example
~~~~~~~

::

    var a = 1;
    debug.assert(a.toString(), '1');

+------------------+-----------------------------------------+
| Parameter Name   | Description                             |
+==================+=========================================+
| radix            | (optional) radix to use in conversion   |
+------------------+-----------------------------------------+

on
--

Adds a listener for the specified event

Example
~~~~~~~

::

    a.on('data', function() { console.log('data!'); });

+------------------+-------------------------------------+
| Parameter Name   | Description                         |
+==================+=====================================+
| event            | event to listen on                  |
+------------------+-------------------------------------+
| cb               | callback function called on event   |
+------------------+-------------------------------------+

emit
----

Execute each of the listeners on the event

Example
~~~~~~~

::

    a.emit('data');

+------------------+----------------------+
| Parameter Name   | Description          |
+==================+======================+
| event            | event to listen on   |
+------------------+----------------------+

removeAllListeners
------------------

removes listeners on a specified event, or all events

Example
~~~~~~~

::

    a.removeAllListeners('data');

+------------------+-----------------------------------------+
| Parameter Name   | Description                             |
+==================+=========================================+
| event            | (optional) event to stop listening on   |
+------------------+-----------------------------------------+

listeners
---------

Returns an array with listeners for the specified event

Example
~~~~~~~

::

    a.listeners('data');

+------------------+--------------------------------+
| Parameter Name   | Description                    |
+==================+================================+
| event            | event for fetching listeners   |
+------------------+--------------------------------+

debug
=====

assert
------

Panic on mismatch between two objects

Example
~~~~~~~

::

    debug.assert(1, 1);

+------------------+-------------------------+
| Parameter Name   | Description             |
+==================+=========================+
| object1          | Object for comparison   |
+------------------+-------------------------+
| object2          | Object for comparison   |
+------------------+-------------------------+

assert\_cond
------------

Panic if object is false

Example
~~~~~~~

::

    debug.assert_cond(1 == 1);

+------------------+------------------+
| Parameter Name   | Description      |
+==================+==================+
| object           | Object to test   |
+------------------+------------------+

assert\_exception
-----------------

Panic if calling cb() does not raise an exception

Example
~~~~~~~

::

    debug.assert_exception(function() { throw 'error'; });

+------------------+--------------------+
| Parameter Name   | Description        |
+==================+====================+
| cb               | function to test   |
+------------------+--------------------+

dump\_env
---------

Dump global environment information to the console

Example
~~~~~~~

::

    debug.dump_env();

Math
====

sin
---

Compute the sine of an angle

Example
~~~~~~~

::

    var zero = Math.sin(Pi);

+------------------+--------------------+
| Parameter Name   | Description        |
+==================+====================+
| angle            | angle in radians   |
+------------------+--------------------+

asin
----

Compute the arc sine of a number

Example
~~~~~~~

::

    var pi = Math.asin(1) * 2;

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

cos
---

Compute the cosine of an angle

Example
~~~~~~~

::

    var one = Math.cos(0);

+------------------+--------------------+
| Parameter Name   | Description        |
+==================+====================+
| angle            | angle in radians   |
+------------------+--------------------+

acos
----

Compute the arc cosine of a number

Example
~~~~~~~

::

    var zero = Math.acos(1);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

tan
---

Compute the tangent of an angle

Example
~~~~~~~

::

    var half =  Math.tan(0.463648);

+------------------+--------------------+
| Parameter Name   | Description        |
+==================+====================+
| angle            | angle in radians   |
+------------------+--------------------+

atan
----

Compute the arc tangent of a number

Example
~~~~~~~

::

    var pi = Math.atan(1) * 4;

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

sqrt
----

Compute the square root of a number

Example
~~~~~~~

::

    var three = Math.sqrt(9);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

log
---

Compute the natural logarithm of a number

Example
~~~~~~~

::

    var zero = Math.log(1);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

exp
---

Compute the base-e exponent of a number

Example
~~~~~~~

::

    var e = Math.exp(1);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

floor
-----

Compute the largest integral value not greater than the argument

Example
~~~~~~~

::

    var three = Math.floor(3.5);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

ceil
----

Compute the smallest integral value not less than the argument

Example
~~~~~~~

::

    var three = Math.ceil(2.5);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

round
-----

Round to nearest integer, away from zero

Example
~~~~~~~

::

    var three = Math.round(2.7);
    var two = Math.round(2.2);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

abs
---

Compute the absolute value of an integer

Example
~~~~~~~

::

    var two = Math.abs(-2);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+

atan2
-----

Compute the arc tangent of two variables

Example
~~~~~~~

::

    var pi = Math.atan2(1, 1) * 4;

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+
| y                | number        |
+------------------+---------------+

pow
---

Power function

Example
~~~~~~~

::

    var hundred = Math.pow(10, 2);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| x                | number        |
+------------------+---------------+
| y                | number        |
+------------------+---------------+

Module
======

require
-------

Searches for a module and evaluates its code

Example
~~~~~~~

::

    var as = require('assert');

+------------------+-----------------------------------------+
| Parameter Name   | Description                             |
+==================+=========================================+
| module\_name     | String containing module name to load   |
+------------------+-----------------------------------------+

Timer
=====

setTimeout
----------

Schedule 'cb' to run in ms milliseconds

Example
~~~~~~~

::

    setTimeout(function() { console.log('Timer Expired'); }, 1000);

+------------------+---------------------------+
| Parameter Name   | Description               |
+==================+===========================+
| cb               | Callback to be run        |
+------------------+---------------------------+
| ms               | Timeout in milliseconds   |
+------------------+---------------------------+

setInterval
-----------

Schedule 'cb' to run periodically every ms milliseconds

Example
~~~~~~~

::

    setInterval(function() { console.log('.'); }, 1000);

+------------------+--------------------------+
| Parameter Name   | Description              |
+==================+==========================+
| cb               | Callback to be run       |
+------------------+--------------------------+
| ms               | Period in milliseconds   |
+------------------+--------------------------+

clearTimeout
------------

Cancel timeout timer if timeout hadn't expired

Example
~~~~~~~

::

    var to = setTimeout(function() { console.log('timeout'); }, 1000);
    clearTimeout(to);

+------------------+----------------------+
| Parameter Name   | Description          |
+==================+======================+
| tid              | Timer ID to cancel   |
+------------------+----------------------+

clearInterval
-------------

Cancel periodic timer

Example
~~~~~~~

::

    var to = setInterval(function() { console.log('.'); }, 1000);
    clearInterval(to);

+------------------+----------------------+
| Parameter Name   | Description          |
+==================+======================+
| tid              | Timer ID to cancel   |
+------------------+----------------------+

getTime
-------

Get number of seconds since system startup

Example
~~~~~~~

::

    console.log('Up for ' + getTime() + ' seconds');

Netif
=====

linkStatus
----------

Get link status

Example
~~~~~~~

::

    var e = new ENC28J60(SPI1, GPIO_PE3, GPIO_PF4);
    console.log('link status: ' + e.linkStatus ? 'connected' : 'disconnected')

MACAddrGet
----------

Get Interface MAC Address

Example
~~~~~~~

::

    var e = new ENC28J60(SPI1, GPIO_PE3, GPIO_PF4);
    console.log(e.MACAddrGet());

IPAddrGet
---------

Get Interface IP Address

Example
~~~~~~~

::

    var e = new NetifINET('eth0');
    console.log(e.IPAddrGet());

onPortChange
------------

Calls 'cb' when link state has changed

Example
~~~~~~~

::

    var e = new ENC28J60(SPI1, GPIO_PE3, GPIO_PF4);
    e.onPortChange(function() { console.log('port state changed!'); });

+------------------+---------------------------------------------------------+
| Parameter Name   | Description                                             |
+==================+=========================================================+
| cb               | callback function called when link status has changed   |
+------------------+---------------------------------------------------------+

IPConnect
---------

Obtain IP Address

Example
~~~~~~~

::

    var e = new ENC28J60(SPI1, GPIO_PE3, GPIO_PF4);
    e.IPConnect();

+------------------+------------------------------------------------------+
| Parameter Name   | Description                                          |
+==================+======================================================+
| cb (optional)    | callback function called on IP address availablity   |
+------------------+------------------------------------------------------+

IPDisconnect
------------

Release IP Address

Example
~~~~~~~

::

    var e = new ENC28J60(SPI1, GPIO_PE3, GPIO_PF4);
    e.IPDisconnect();

TCPConnect
----------

Connect to a TCP IP:PORT

Example
~~~~~~~

::

    var e = new NetifINET();
    e.TCPIPConnect('192.168.1.10', 80, function() { console.log('connected'); });

+------------------+------------------------------------------------+
| Parameter Name   | Description                                    |
+==================+================================================+
| ip               | IP address to connect to                       |
+------------------+------------------------------------------------+
| port             | tcp port to connect to                         |
+------------------+------------------------------------------------+
| cb               | callback function called on TCP connectivity   |
+------------------+------------------------------------------------+

TCPDisconnect
-------------

Release TCP connection

Example
~~~~~~~

::

    var e = new NetifINET();
    e.TCPIPConnect('192.168.1.10', 80, function() { console.log('connected'); e.TCPDisconnect() });

onTCPData
---------

Calls 'cb' when TCP data is available

Example
~~~~~~~

::

    var e = new NetifINET();
    e.onTCPData(function() { console.log('TCP data ready!'); });

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | call |
|      | back |
|      | func |
|      | tion |
|      | call |
|      | ed   |
|      | when |
|      | TCP  |
|      | data |
|      | is   |
|      | avai |
|      | labl |
|      | e.   |
|      | Empt |
|      | y    |
|      | call |
|      | back |
|      | remo |
|      | ves  |
|      | the  |
|      | list |
|      | ener |
+------+------+

onTCPDisconnect
---------------

Calls 'cb' when TCP stream is disconnected

Example
~~~~~~~

::

    var e = new NetifINET();
    e.onTCPDisconnect(function() { console.log('TCP disconnected!'); });

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | call |
|      | back |
|      | func |
|      | tion |
|      | call |
|      | ed   |
|      | when |
|      | TCP  |
|      | stre |
|      | am   |
|      | is   |
|      | disc |
|      | onne |
|      | cted |
|      | .    |
|      | Empt |
|      | y    |
|      | call |
|      | back |
|      | remo |
|      | ves  |
|      | the  |
|      | list |
|      | ener |
+------+------+

TCPWrite
--------

Writes data to the TCP socket

Example
~~~~~~~

::

    var e = new NetifINET();
    e.TCPIPConnect('192.168.1.10', 80, function() { e.TCPWrite('GET / HTTP 1.0

    '); });

+------------------+---------------------------------------------------+
| Parameter Name   | Description                                       |
+==================+===================================================+
| data             | Data (byte/array/string/typed array) to be sent   |
+------------------+---------------------------------------------------+

TCPRead
-------

Reads data from the TCP socket

Example
~~~~~~~

::

    var e = new NetifINET();
    e.onTCPData(function() { console.log(n.TCPRead()); });
    e.TCPIPConnect('192.168.1.10', 80, function() { e.TCPWrite('GET / HTTP 1.0

    '); });

ENC28J60 (constructor)
----------------------

ENC28J60 Ethernet Constructor

Example
~~~~~~~

::

    var enc = new ENC28J60(SPI0, GPIO_PF0, GPIO_PF1);
    console.log('link status: ' + enc.linkStatus() ? 'connected' : 'disconnected');

+------------------+-----------------------+
| Parameter Name   | Description           |
+==================+=======================+
| SPI port         | SPI Port              |
+------------------+-----------------------+
| CS               | SPI Chip Select Pin   |
+------------------+-----------------------+
| Interrupt        | Interrupt Pin         |
+------------------+-----------------------+

ESP8266 (constructor)
---------------------

ESP8266 Wi-Fi Constructor

Example
~~~~~~~

::

    var esp = new ESP8266(function() {
    esp.IPConnect(function() { console.log('connected'); });
    }, UART4);

+--------------------------+----------------------------------------------+
| Parameter Name           | Description                                  |
+==========================+==============================================+
| cb                       | Callback to be called when device is ready   |
+--------------------------+----------------------------------------------+
| Serial port (optional)   | Serial Port                                  |
+--------------------------+----------------------------------------------+

StellarisEth (constructor)
--------------------------

Stellaris Ethernet Object Constructor

Example
~~~~~~~

::

    var enc = new StellarisEth();
    console.log('link status: ' + enc.linkStatus() ? 'connected' : 'disconnected');

NetifINET (constructor)
-----------------------

INET Network Interface Object Constructor

Example
~~~~~~~

::

    var  n = new NetifINET('eth0');
    console.log('link status: ' + n.linkStatus() ? 'connected' : 'disconnected');

+------------------+--------------------------+
| Parameter Name   | Description              |
+==================+==========================+
| Net Device       | Network Interface Name   |
+------------------+--------------------------+

LinuxPacketEth (constructor)
----------------------------

Linux Packet Ethernet Object Constructor

Example
~~~~~~~

::

    var  n = new LinuxPacketEth('eth0');
    console.log('link status: ' + n.linkStatus() ? 'connected' : 'disconnected');

+------------------+--------------------------------+
| Parameter Name   | Description                    |
+==================+================================+
| Net Device       | Linux Network Interface Name   |
+------------------+--------------------------------+

ESP8266\_WIFI (constructor)
---------------------------

ESP8266 Wi-Fi Constructor

Example
~~~~~~~

::

    var esp = new ESP8266_WIFI();
    esp.IPConnect();

console
=======

set
---

Sets TinkerPal console to a given serial port

Example
~~~~~~~

::

    console.set(new Serial(UART1));

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| serial           | Serial object   |
+------------------+-----------------+

log
---

Logs object to the console

Example
~~~~~~~

::

    console.log('Hello World');

+------------------+---------------------+
| Parameter Name   | Description         |
+==================+=====================+
| object           | Object to display   |
+------------------+---------------------+

Graphics
========

Graphics (constructor)
----------------------

Graphics Constructor

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.stringDraw(0, 0, 'Hello World!', 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| Canvas           | Canvas Object   |
+------------------+-----------------+

stringDraw
----------

Prints string on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.stringDraw(0, 0, 'Hello World!', 0xffff);

+------------------+----------------------+
| Parameter Name   | Description          |
+==================+======================+
| x                | X coordinate         |
+------------------+----------------------+
| y                | Y coordinate         |
+------------------+----------------------+
| str              | String to be drawn   |
+------------------+----------------------+
| color            | Color                |
+------------------+----------------------+

circleDraw
----------

Draws a circle on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.circleDraw(20, 20, 10, 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| x                | X coordinate    |
+------------------+-----------------+
| y                | Y coordinate    |
+------------------+-----------------+
| radius           | Circle Radius   |
+------------------+-----------------+
| color            | Color           |
+------------------+-----------------+

circleFill
----------

Draws a circle on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.circleFill(20, 20, 10, 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| x                | X coordinate    |
+------------------+-----------------+
| y                | Y coordinate    |
+------------------+-----------------+
| radius           | Circle Radius   |
+------------------+-----------------+
| color            | Color           |
+------------------+-----------------+

lineDraw
--------

Draws a line on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.lineDraw(10, 10, 20, 20, 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| x0               | X0 coordinate   |
+------------------+-----------------+
| y0               | Y0 coordinate   |
+------------------+-----------------+
| x1               | X1 coordinate   |
+------------------+-----------------+
| y1               | Y1 coordinate   |
+------------------+-----------------+
| color            | Color           |
+------------------+-----------------+

rectDraw
--------

Draws a rectangle on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.rectDraw(10, 10, 20, 20, 0xffff);

+------------------+----------------+
| Parameter Name   | Description    |
+==================+================+
| x                | X coordinate   |
+------------------+----------------+
| y                | Y coordinate   |
+------------------+----------------+
| w                | Width          |
+------------------+----------------+
| h                | Height         |
+------------------+----------------+
| color            | Color          |
+------------------+----------------+

roundRectDraw
-------------

Draws a round rectangle on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.roundRectDraw(10, 10, 20, 20, 4, 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| x                | X coordinate    |
+------------------+-----------------+
| y                | Y coordinate    |
+------------------+-----------------+
| w                | Width           |
+------------------+-----------------+
| h                | Height          |
+------------------+-----------------+
| r                | Corner Radius   |
+------------------+-----------------+
| color            | Color           |
+------------------+-----------------+

roundRectFill
-------------

Draws a filled round rectangle on LCD

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    var g = new Graphics(lcd);
    g.roundRectFill(10, 10, 20, 20, 4, 0xffff);

+------------------+-----------------+
| Parameter Name   | Description     |
+==================+=================+
| x                | X coordinate    |
+------------------+-----------------+
| y                | Y coordinate    |
+------------------+-----------------+
| w                | Width           |
+------------------+-----------------+
| h                | Height          |
+------------------+-----------------+
| r                | Corner Radius   |
+------------------+-----------------+
| color            | Color           |
+------------------+-----------------+

rectFill
--------

Draws a filled rectangle on LCD

Example
~~~~~~~

::

    var lcd = new ST7735();
    var g = new Graphics(lcd);
    g.rectFill(10, 10, 20, 20, g.RED);

+------------------+----------------+
| Parameter Name   | Description    |
+==================+================+
| x                | X coordinate   |
+------------------+----------------+
| y                | Y coordinate   |
+------------------+----------------+
| w                | Width          |
+------------------+----------------+
| h                | Height         |
+------------------+----------------+
| color            | Color          |
+------------------+----------------+

Canvas
======

pixelDraw
---------

Draw a pixel on the screen

Example
~~~~~~~

::

    var l = new ILI93XX();
    l.pixelDraw(10, 10, 1);

+------------------+----------------+
| Parameter Name   | Description    |
+==================+================+
| x                | X Coordinate   |
+------------------+----------------+
| y                | Y Coordinate   |
+------------------+----------------+
| value            | Color Value    |
+------------------+----------------+

fill
----

Fills the canvas with a color

Example
~~~~~~~

::

    var l = new ILI93XX();
    l.fill(0xfe);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| value            | Color Value   |
+------------------+---------------+

flip
----

Publishes stored buffer onto canvas

Example
~~~~~~~

::

    var l = new SSD1306();
    l.pixelDraw(1, 1, 1);
    l.flip();

SSD1306 (constructor)
---------------------

SSD1306 Constructor

Example
~~~~~~~

::

    var lcd = new SSD1306();
    lcd.pixelDraw(10, 10, 1);

ST7920 (constructor)
--------------------

ST7920 Constructor

Example
~~~~~~~

::

    var lcd = new ST7920();
    lcd.pixelDraw(10, 10, 1);

ST7735 (constructor)
--------------------

ST7735 Constructor

Example
~~~~~~~

::

    var lcd = new ST7735();
    lcd.pixelDraw(10, 10, 1);

DummyCanvas (constructor)
-------------------------

Dummy Canvas Constructor

Example
~~~~~~~

::

    var lcd = new DummyCanvas();
    lcd.pixelDraw(10, 10, 1);

SSD1329 (constructor)
---------------------

SSD1329 Constructor

Example
~~~~~~~

::

    var lcd = new SSD1329();
    lcd.pixelDraw(10, 10, 1);

SDLScreen (constructor)
-----------------------

SDL screen Constructor

Example
~~~~~~~

::

    var lcd = new SDLScreen();
    lcd.pixelDraw(10, 10, 1);

ILI93XX (constructor)
---------------------

ili93xx Constructor

Example
~~~~~~~

::

    var lcd = new ILI93XX();
    lcd.pixelDraw(10, 10, 1);

Dogs102x6 (constructor)
-----------------------

Dogs102x6 Constructor

Example
~~~~~~~

::

    var lcd = new Dogs102x6();
    lcd.pixelDraw(10, 10, 1);

PCD8544 (constructor)
---------------------

PCD8544 Constructor

Example
~~~~~~~

::

    var lcd = new PCD8544();
    lcd.pixelDraw(10, 10, 1);

MMC
===

MMC (constructor)
-----------------

MMC Constructor

Example
~~~~~~~

::

    new MMC();

SPI
===

SPI (constructor)
-----------------

SPI Object Constructor

Example
~~~~~~~

::

    var s = new SPI(SPI1);
    s.send(0xff);

+------------------+------------------+
| Parameter Name   | Description      |
+==================+==================+
| Port ID          | HW SPI Port ID   |
+------------------+------------------+

send
----

Sends data via SPI bus

Example
~~~~~~~

::

    var s = new SPI(SPI1);
    s.send(0x1f);

+------------------+------------------------------------------+
| Parameter Name   | Description                              |
+==================+==========================================+
| data             | Data to be sent on SPI (integer/array)   |
+------------------+------------------------------------------+
| cs               | Chip select pin (optional)               |
+------------------+------------------------------------------+

receive
-------

Reads data via SPI bus (dummy data is sent)

Example
~~~~~~~

::

    var s = new SPI(SPI1);
    var data = s.receive();

GPIO
====

digitalWrite
------------

Set the digital value of a GPIO or a number of GPIOs

Example
~~~~~~~

::

    digitalWrite(GPIO_PF2, true); /* Turn on PF2 */
    digitalWrite([GPIO_PF1, GPIO_PF2, GPIO_PF3], 0x5); /* Turn on PF1 & PF3 */

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| pin[ | Sing |
| s]   | le   |
|      | GPIO |
|      | ID   |
|      | or   |
|      | arra |
|      | y    |
|      | of   |
|      | GPIO |
|      | IDs  |
+------+------+
| valu | Bool |
| e    | ean  |
|      | for  |
|      | a    |
|      | sing |
|      | le   |
|      | GPIO |
|      | In   |
|      | case |
|      | of   |
|      | an   |
|      | arra |
|      | y,   |
|      | valu |
|      | e    |
|      | is   |
|      | cons |
|      | ider |
|      | ed   |
|      | an   |
|      | inte |
|      | ger  |
|      | wher |
|      | e    |
|      | thef |
|      | irst |
|      | arra |
|      | y    |
|      | elem |
|      | ent  |
|      | maps |
|      | to   |
|      | the  |
|      | MSB  |
+------+------+

digitalPulse
------------

Create a digital pulse on a GPIO pin for a given period

Example
~~~~~~~

::

    digitalPulse(GPIO_PF2, true, 0.1);

+------------------+--------------------------------+
| Parameter Name   | Description                    |
+==================+================================+
| pin              | GPIO pin ID                    |
+------------------+--------------------------------+
| value            | Boolean                        |
+------------------+--------------------------------+
| ms               | Pulse period in milliseconds   |
+------------------+--------------------------------+

digitalRead
-----------

Read the digital state of a GPIO pin or a number of pins

Example
~~~~~~~

::

    var state = digitalRead(GPIO_PF2);
    var a = digitalRead([GPIO_PF0, GPIO_PF1, GPIO_PF2

+------------------+----------------------------------------+
| Parameter Name   | Description                            |
+==================+========================================+
| pin[s]           | GPIO pin ID or array of GPIO pin IDs   |
+------------------+----------------------------------------+

analogWrite
-----------

Set the analog value of a GPIO pin

Example
~~~~~~~

::

    analogWrite(GPIO_PF2, 0.5);

+----------------------+------------------------------------------+
| Parameter Name       | Description                              |
+======================+==========================================+
| pin                  | GPIO pin ID                              |
+----------------------+------------------------------------------+
| value                | Floating point number with range [0-1]   |
+----------------------+------------------------------------------+
| options (Optional)   | Object: { freq : }                       |
+----------------------+------------------------------------------+

analogRead
----------

Read the analog value of a GPIO pin

Example
~~~~~~~

::

    var f = analogRead(GPIO_PF2);

+------------------+---------------+
| Parameter Name   | Description   |
+==================+===============+
| pin              | GPIO pin ID   |
+------------------+---------------+

setWatch
--------

Calls a function whenever the GPIO pin changes state

Example
~~~~~~~

::

    setWatch(function() { console.log('button changed state'); }, GPIO_PF0);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| cb   | call |
|      | back |
|      | func |
|      | tion |
|      | :The |
|      | func |
|      | tion |
|      | may  |
|      | rece |
|      | ive  |
|      | an   |
|      | obje |
|      | ct   |
|      | of   |
|      | type |
|      | :{   |
|      | time |
|      | stam |
|      | p:   |
|      | in   |
|      | seco |
|      | nds, |
|      | stat |
|      | e:   |
|      | curr |
|      | ent  |
|      | pin  |
|      | stat |
|      | e}   |
+------+------+
| pin  | GPIO |
|      | pin  |
|      | ID   |
+------+------+
| opti | opti |
| ons  | onal |
|      | opti |
|      | ons  |
|      | obje |
|      | ct   |
|      | of   |
|      | type |
|      | {    |
|      | qlen |
|      | :    |
|      | int  |
|      | //   |
|      | numb |
|      | er   |
|      | of   |
|      | pend |
|      | ing  |
|      | samp |
|      | les  |
|      | for  |
|      | proc |
|      | essi |
|      | ng   |
|      | smal |
|      | ler  |
|      | than |
|      | 128, |
|      | must |
|      | be   |
|      | powe |
|      | r    |
|      | of   |
|      | 2.   |
|      | Defa |
|      | ult  |
|      | =1 } |
+------+------+

Serial
======

Serial (constructor)
--------------------

Serial Constructor

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.print('Hello World!);

+------+------+
| Para | Desc |
| mete | ript |
| r    | ion  |
| Name |      |
+======+======+
| UART | HW   |
|      | UART |
|      | ID   |
+------+------+
| opti | opti |
| ons  | onal |
|      | opti |
|      | ons  |
|      | obje |
|      | ct   |
|      | of   |
|      | type |
|      | {    |
|      | baud |
|      | \_ra |
|      | te   |
|      | :    |
|      | int  |
|      | //   |
|      | Seri |
|      | al   |
|      | Baud |
|      | Rate |
|      | }    |
+------+------+

enable
------

Enable a serial port

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.enable();

disable
-------

Disable a serial port

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.disable();

print
-----

Prints string

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.print('Hello World!');

+------------------+---------------------------------------+
| Parameter Name   | Description                           |
+==================+=======================================+
| string           | String to be printed to serial port   |
+------------------+---------------------------------------+

write
-----

Writes data to the serial port

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.write(255);
    s.write([1,2,3])

+------------------+---------------------------------------------------+
| Parameter Name   | Description                                       |
+==================+===================================================+
| data             | Data (byte/array/string/typed array) to be sent   |
+------------------+---------------------------------------------------+

onData
------

Calls 'cb' when data is available on serial port. If cb is undefined,
removes the previously set cb

Example
~~~~~~~

::

    var s = new Serial(UART1);
    s.onData(function(e) { s.print(e.data); });

+------------------+---------------------------------------------+
| Parameter Name   | Description                                 |
+==================+=============================================+
| cb               | callback function accepting a data object   |
+------------------+---------------------------------------------+
