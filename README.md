[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-ErrorView-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1285)

ErrorView
=========
A custom view that displays an error image, a title, and a subtitle given an HTTP status code. It can be used for various other purposes like displaying other kinds of errors, or just messages with images.

<p align="center">
<img src="/graphics/screenshots/ss_01.png" />
</p>

# Usage
### Add as a dependency
```groovy
    compile 'com.github.xiprox.errorview:library:2.+'
````
**Note:** It's safe to use a `+` sign after the major version number. There won't be any backwards incompatible changes within the same version number. If such a change is to happen, major version number will be incremented and this file will be updated. This means that you can safely use the `+` sign without having to worry about your builds breaking.

### Set the error by HTTP Status Code
You just need to pass your HTTP status code using `setError(int)` and ErrorView will show the associated error description for you.

### Set the error manually
In order to set the title or the subtitle manually, you can make use of the `setTitle(String)`, `setTitle(int)`, `setSubtitle(String)`, and `setSubtitle(int)` methods.

### Configs
Configs are like packages that hold the ErrorView state. You can use configs to define a very common error and reuse it all around your app.

```java
    mErrorView.setConfig(Config);
```
```java
    mErrorView.getConfig();
```

#### Defining a Config
```java
    ErrorView.Config.create()
            .image(int)
            .image(Drawable)
            .image(Bitmap)
            .title(String)
            .titleColor(int)
            .subtitle(String)
            .subtitleColor(int)
            .retryVisible(boolean)
            .retryText(String)
            .retryTextColor(int)
            .build();
```

### Catch Retry Events
To catch retry events, you can make use of the `setOnRetryListener(RetryListener)` method.

### More Methods
Check out the [source code](../master/library/src/main/java/tr/xip/errorview/ErrorView.java) for other methods and their explanations.

### XML Attributes
```xml
<tr.xip.errorview.ErrorView xmlns:errorview="http://schemas.android.com/apk/res-auto"
    android:id="@+id/error_view"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    errorview:ev_title="@string/..."
    errorview:ev_titleColor="@color/..."
    errorview:ev_subtitle="@string/..."
    errorview:ev_subtitleColor="@color/..."
    errorview:ev_errorImage="@drawable/..."
    errorview:ev_showTitle="boolean"
    errorview:ev_showSubtitle="boolean"
    errorview:ev_showRetryButton="boolean"
    errorview:ev_retryButtonText="@string/..."
    errorview:ev_retryButtonBackground="@drawable/..."
    errorview:ev_retryButtonTextColor="@color/..." />
```

# Sample App
<a href="https://play.google.com/store/apps/details?id=tr.xip.errorview.sample">
<img alt="Get it on Google Play"
src="https://developer.android.com/images/brand/en_generic_rgb_wo_45.png" />
</a>

# Apps using ErrorView
Check out [this](https://github.com/xiprox/ErrorView/wiki/Apps-using-ErrorView) wiki page for the list of apps using ErrorView. If you are using ErrorView in your app, please take a moment to add your app to the list. I really appreciate it.

# License
```
Copyright (C) 2015 Ihsan Isik

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
