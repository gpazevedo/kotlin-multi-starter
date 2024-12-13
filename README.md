# Kotlin Multi-Project Starter

This is a starter repository for a Kotlin project composed of multiples inter-related subprojects.
Each subproject can be developed and deployed autonomously, but they share fundamental common definitions.
Examples:
- Kotlin Application with libraries.
- Set of related Service Applications with/without shared libraries.

The [Guidelines](./GUIDELINES.md) explain the structure of this repository, and has instructions on how to adapt it for your own project.

## Instructions

This project uses [Gradle](https://gradle.org/).

To build and run the application, use the *Gradle* tool window by clicking the Gradle icon in the right-hand toolbar,
or run it directly from the terminal:

* Run `./gradlew run` to build and run the application.
* Run `./gradlew build` to only build the application.
* Run `./gradlew check` to run all checks, including tests.
* Run `./gradlew clean` to clean all build outputs.
* Run `./gradlew publish` to publish all artifacts.
* Run `./gradlew jacocoTestReport` to generate a report with test coverage, example: [utils report](./utils/build/reports/jacoco/test/html/index.html).

Note the usage of the Gradle Wrapper (`./gradlew`).
This is the suggested way to use Gradle in production projects.

[Learn more about the Gradle Wrapper](https://docs.gradle.org/current/userguide/gradle_wrapper.html).

[Learn more about Gradle tasks](https://docs.gradle.org/current/userguide/command_line_interface.html#common_tasks).

This project follows the suggested multi-module setup and consists of the `app` and `utils` subprojects.
The shared build logic was extracted to a convention plugin located in `buildSrc`.

This project uses a version catalog (see `gradle/libs.versions.toml`) to declare and version dependencies
and also both a build cache and a configuration cache (see `gradle.properties`).