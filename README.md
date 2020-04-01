# KoTest MacOs native bug

To repro: run `./gradlew macosTest`

You should get something like this:
```
➜  kotest-mac ./gradlew macosTest

> Configure project :
Kotlin Multiplatform Projects are an experimental feature.

> Task :compileTestKotlinMacos FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileTestKotlinMacos'.
> Could not resolve all files for configuration ':macosTestCompileKlibraries'.
   > Could not resolve io.kotest:kotest-assertions-core-native:4.0.1.
     Required by:
         project :
      > Unable to find a matching variant of io.kotest:kotest-assertions-core-native:4.0.1:
          - Variant 'metadata-api' capability io.kotest:kotest-assertions-core-native:4.0.1:
              - Incompatible attribute:
                  - Required org.jetbrains.kotlin.platform.type 'native' and found incompatible value 'common'.
              - Other attributes:
                  - Found org.gradle.status 'release' but wasn't required.
                  - Required org.gradle.usage 'kotlin-api' and found compatible value 'kotlin-api'.
                  - Required org.jetbrains.kotlin.native.target 'macos_x64' but no value provided.
          - Variant 'native-api' capability io.kotest:kotest-assertions-core-native:4.0.1:
              - Incompatible attribute:
                  - Required org.jetbrains.kotlin.native.target 'macos_x64' and found incompatible value 'linux_x64'.
              - Other attributes:
                  - Found org.gradle.status 'release' but wasn't required.
                  - Required org.gradle.usage 'kotlin-api' and found compatible value 'kotlin-api'.
                  - Required org.jetbrains.kotlin.platform.type 'native' and found compatible value 'native'.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 876ms
2 actionable tasks: 1 executed, 1 up-to-date

```