form-serializer
===============

A Simple jQuery plug-in that helps serializing the forms in better yet simplest way possible.

>**Note:** Incase when there is multiple form elements are selected, it will only serialize the first form element.

Usages:
-------
### 1. [serialize()](#serialize)
### 2. [populate()](#populate)

**serialize()**
---------------
**Get form data as JSON Object** (by passing `type` as **json**).
```javascript
	$('#formId').serialize('json');
```
**Get form as Query String.**

```javascript
	$('#formId').serialize();  //same as jQuery's $('#formId').serialize()
```
But if you pass `type` as **queryString**
```javascript
	$('#formId').serialize('queryString');
```
then Instead of this kind of Query String: 
```javascript
	hobby=football&hobby=tennis  //output of $('#formId').serialize()
```
it will return this: 
```javascript
	hobby=football,tennis  //output of $('#formId').serialize('queryString')
```
You can also set **custom elements selector** inside a **Form**.
```javascript
	//serialize only `input` tags' value
	$('#formId').serialize({type: 'queryString', inputSelector: 'input'}); 
```
```javascript
	//serialize only `input` tags' value which has type="text"
	$('#formId').serialize({type: 'queryString', inputSelector: 'input[type="text"]'}); 
```
You can also serialize `disabled` elements by setting `serializeDisabled` as `true`.
```javascript
	$('#formId').serialize({type: 'queryString', serializeDisabled: true}); 
```
**populate()**
--------------

**Populate/Fill Form with JSON Object**
```javascript
	$('#formId').populate(jsonObject);
```
**Populate/Fill Form with QueryString Object**
```javascript
	$('#formId').populate(queryString);
```
You can pass `inputSelector` to populate custom selected elements.
```javascript
	$('#formId').populate(queryString, {inputSelector: "input[type='text']"});
```
If you have multiple values in **comma separated manner** in query param (e.g. Serialized with **$('#formId').serialize('queryString')**), you need set `separateMultiParam` option to true for populate() to work.
```javascript
	$('#formId').populate(queryString, {separateMultiParam: true});
```