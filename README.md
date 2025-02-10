# Expo Android Build Failure: Non-Zero Exit Value 2

This repository demonstrates a common issue encountered when building Android APKs using the Expo CLI. The build process fails with a non-zero exit value 2, usually stemming from conflicts between AndroidX libraries or issues related to ProGuard/R8 code shrinking and obfuscation.

## Problem Description

The `bug.js` file contains a simplified project structure illustrating the problem. This might not directly reproduce the error, but serves as a basis for understanding the context.  The error message often points to `transformClassesWithDexBuilderForDebug` task failure, hinting at problems during the DEX (Dalvik Executable) creation, a crucial step in Android application packaging.

## Solution

The solution is found in `bugSolution.js`. It showcases common fixes, including:

* **Careful Dependency Management:** Ensuring all dependencies are compatible by checking `package.json`.  Resolving version conflicts between AndroidX libraries is paramount. 
* **ProGuard/R8 Configuration (if applicable):** Sometimes, more fine-grained control is needed over ProGuard or R8 rules, as specified in the `proguard-rules.pro` or equivalent configuration file (depending on the build system).
* **Clean and Rebuild:** A simple clean and rebuild often resolves transient issues.
* **Checking for Native Modules:** If your application uses native modules, ensure that they are properly configured for Android.
* **Gradle Configuration (Advanced):** In complex scenarios, adjustments to Gradle settings might be needed.