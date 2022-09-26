# Cấu hình SDK

Để tạo một ứng dụng Android hỗ trợ VoIP:

1. Cầu hình setting.gradle của Project như sau:

```
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        jcenter() // Warning: this repository is going to shut down soon
        maven {
            url("https://vihat.jfrog.io/artifactory/vihat-local-repo")
            credentials {
                username = "anonymous"
            }
        }
    }
}
```

2\. Cấu hình trong File build.gradle ở thư mục app như sau :&#x20;

`implementation 'vn.vihat.omicall:omisdk:0.9.0'`

3\. Add library required by SDK

```
implementation 'androidx.core:core-ktx:1.7.0'
implementation 'androidx.fragment:fragment-ktx:1.4.0'
implementation 'androidx.activity:activity-ktx:1.4.0'
implementation 'androidx.appcompat:appcompat:1.5.0'
implementation 'com.google.android.material:material:1.6.1'
implementation 'com.google.firebase:firebase-messaging-ktx:23.0.8'
implementation 'com.google.android.flexbox:flexbox:3.0.0'
implementation "com.google.code.gson:gson:2.8.6"

```

&#x20;4\. Bổ sung đoạn mã sau ở đầu File  build.gradle:

```
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'
apply plugin: 'kotlin-kapt'

```

`5.` Sync project with gradle
