## Services overview

    ├── ...
    ├── modules
    │   ├── services
    │   |   ├── build-config
    │   │   |   └── build.gradle.kts
    │   |   ├── api-v1
    │   |   ├── resources
    │   |   └── core

As it was mentioned previously, services is basically application utility modules

### 1. Build config service module

For example, we have `:build-config` module, which will contain only `build.gradle.kts` plugin for `BuildKonfig`
creation

```kotlin
plugins {
    kotlin("jvm")
    id("com.github.gmazzo.buildconfig")
}

buildConfig {
    className("BuildKonfig")
    packageName("com.myproject.sample.buildkonfig")
    buildConfigStringField("MY_SECRET_KEY", "\"Wow! It's really secret!\"")
}
```

This module, `:build-config` is fully independent.

Furthermore, it's fully reusable in other projects!

And of course, it can be reused in other project modules.

So, eventually, with this gradle project architecture, we have reusable fully independent gradle module for our project.

### 2. Resources service module

Usually, resource of the project are reused by other modules.

So here, in `:resources`, we can extract our shared resources like themes, splash, colors, some drawables and etc.

Of course feature-modules will contain some specific string resources or drawables.

### 3. Core services module

Core services module may contain basic extension for application.

For example, BaseViewModel, BaseRepository, StringProvider and etc.

### 4. api-v1

`:api-v1` can be any swagger-generated api of your backend.

It shouldn't contain any repositories.

It can contain custom token interceptor logic etc if needed.