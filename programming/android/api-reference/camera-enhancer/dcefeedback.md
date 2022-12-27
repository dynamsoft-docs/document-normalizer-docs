---
layout: default-layout
title: Android DCEFeedback Class - Dynamsoft Document Normalizer Documents
description: This is the documentation - Android DCEFeedback Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android, DCEFeedback
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
breadcrumbText: Android DCEFeedback Class
---

# DCEFeedback

| Method | Description |
| ------ | ----------- |
| [`vibrate`](#vibrate) | Trigger a vibration when the method is called. |
| [`beep`](#beep) | Trigger a beep when the method is called. |

## vibrate

Trigger a vibration when the method is called.

```java
static void vibrate(Context context)
```

**Code Snippet**

```java
DCEFeedback.vibrate(MainActivity.this);
// For example, if `vibrate` is called in the TextResultCallback of DBR, the device will trigger a vibration each time when barcode result is detected.
mReader.setTextResultListener(new TextResultListener() {
    @Override
    public void textResultCallback(int id, ImageData imageData, TextResult[] textResults) {
        ...
        DCEFeedback.vibrate(MainActivity.this);
    }
});
```

## beep

Trigger a beep when the method is called.

```java
static void beep(Context context)
```

**Code Snippet**

```java
DCEFeedback.beep(MainActivity.this);
// For example, if `beep` is called in the TextResultCallback of DBR, the device will trigger a beep each time when barcode result is detected.
mReader.setTextResultListener(new TextResultListener() {
    @Override
    public void textResultCallback(int id, ImageData imageData, TextResult[] textResults) {
        ...
        DCEFeedback.beep(MainActivity.this);
    }
});
```
