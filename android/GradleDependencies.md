### Important Gradle Dependencies

#### Navigation
```kotlin
    implementation("androidx.navigation:navigation-compose:2.7.6")
    implementation("androidx.navigation:navigation-runtime-ktx:2.7.6")
```

#### ViewModel Compose
```kotlin
    implementation("androidx.lifecycle:lifecycle-viewmodel-compose:2.6.2")
```

#### Material Icon
```kotlin
    implementation("androidx.compose.material:material-icons-extended:1.5.1")
```

#### SplashScreen
```kotlin
    implementation("androidx.core:core-splashscreen:1.0.1")
```

#### Kapt
```kotlin
    plugins {
        ...
        kotlin("kapt")
    }
```

#### Retrofit kit
```kotlin
    implementation("com.squareup.retrofit2:retrofit:2.9.0")
    implementation("com.squareup.retrofit2:converter-gson:2.9.0")
    implementation("com.squareup.okhttp3:okhttp:5.0.0-alpha.11")
    implementation("com.squareup.okhttp3:logging-interceptor:5.0.0-alpha.11")
```

#### Room 
```kotlin 
    implementation("androidx.room:room-ktx:2.5.2")
    //noinspection KaptUsageInsteadOfKsp
    kapt("androidx.room:room-compiler:2.5.2")
```

#### Preferences DataStore
```kotlin
    implementation("androidx.datastore:datastore-preferences:1.0.0")
```
#### DaggerHilt
```kotlin
    plugins {
        id("dagger.hilt.android.plugin")
    }

    ...

    implementation("com.google.dagger:hilt-android:2.48")
    implementation("androidx.hilt:hilt-work:1.1.0")
    implementation("androidx.work:work-runtime-ktx:2.9.0")
    implementation("androidx.hilt:hilt-navigation-compose:1.1.0")
    kapt("com.google.dagger:hilt-android-compiler:2.48")
```

```kotlin
    // Top level gradle
    plugins {
        ...
        id("com.google.dagger.hilt.android") version "2.48" apply false
    }   
```