# Text box

![Default appearance for the 'text-box' field plug-in](extras/preview-images/default.jpg)

|<img src="extras/preview-images/max.jpg" width="100px">|<img src="extras/preview-images/count.jpg" width="100px">|<img src="extras/preview-images/six_rows.jpg" width="100px">|
|:---:|:---:|:---:|
|Max|Count|6 rows|

## Description

Use this field plug-in if text responses will be somewhat longer, and you would like to have a larger text box to enter the data. You can also use this field plug-in to put in a limit to the amount of text that can be entered, without needing to check it against a *constraint*.

[![Download now](extras/readme-images/download-button.png)](https://github.com/surveycto/text-box/raw/master/text-box.fieldplugin.zip)

### Features

* Larger text box with customizable size
* Limit number of characters that can be entered
* Show character count
* Set to expand to fit content, just like in fields without field plug-ins.
* Set maximum expansion size.

This field plug-in also inherits functionality from the [baseline-text](https://github.com/surveycto/baseline-text/blob/master/README.md) field plug-in.

### Data format

This field returns the text entered into the text box.

## How to use

### Getting started

**To use this field plug-in as-is:**

1. Download the [sample form](https://github.com/surveycto/text-box/blob/master/extras/sample-form/Text%20box%20sample%20form.xlsx?raw=true) from this repo and upload it to your SurveyCTO server.
1. Download the [text-box.fieldplugin.zip](https://github.com/surveycto/text-box/raw/master/text-box.fieldplugin.zip) file from this repo, and attach it to the sample form on your SurveyCTO server.

### Parameters

|Name|Description|
|---|---|
|`rows` (optional)|The number of rows in the text box shown at a time. In other words, the height of the text box. Behavior is different if `expand` has a value of `1`; [see below](#expand) for details.<br>Default: 3|
|`max` (optional)|The maximum number of characters that can be entered into the text box. If this parameter has no value, then there is no limit.|
|`count` (optional)|Whether or not to show the character count so far. [See below](#count) for more details.|
|`expand` (optional|If this parameter has a value of `1`, then the text box will expand to fit the content.|

This field also inherits the parameter from the [baseline-text](https://github.com/surveycto/baseline-text/blob/master/README.md) field plug-in.

#### count

The behavior of the `count` parameter will depend on the value of the `max` parameter:

* **`max` has a numeric value, and `count` is not specified**: The field will show the number of characters remaining.
* **`max` has a numeric value, and `count` has a value of `0`**: The count will be hidden.
* **`max` has no value, and `count` is not specified**:  The count will be hidden.
* **`max` has no value, and `count` has a value of `1`**: The field will show the number of characters entered so far.

#### expand

If this parameter has a value of `1`, then the text box will grow to fit the content, so the enumerator does not have to scroll to view all of the content. This is the behavior of fields without field plug-ins.

Also, instead of the `rows` parameter being used to determine the number of rows that will be shown, it defines the maximum number of rows it will expand to. For example, if `expand` has a value of `1`, and `rows` has a value of `5`, then the text box will expand until it is 5 rows tall, and then the enumerator will have to scroll to view the rest of the content.

### Default SurveyCTO feature support

| Feature / Property | Support |
| --- | --- |
| Supported field type(s) | `text`|
| Default values | Yes |
| Constraint message | Uses default behavior |
| Required message | Uses default behavior |
| Read only | Yes *(shows the current value, if present)* |
| media:image | Yes |
| media:audio | Yes |
| media:video | Yes |
| `numbers` appearance | Yes |
| `numbers-decimal` appearance | Yes |
| `numbers-phone` appearance | Yes |

## More resources

* **Sample form**  
You can find a form definition in this repo here: [extras/sample-form](extras/sample-form).

* **Developer documentation**  
More instructions for developing and using field plug-ins can be found here: [https://github.com/surveycto/Field-plug-in-resources](https://github.com/surveycto/Field-plug-in-resources)