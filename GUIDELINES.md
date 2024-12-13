# Guidelines for Adaptation

This is a starter repository for a Kotlin project composed of multiples inter-related subprojects.
Each subproject can be developed and deployed autonomously, but they share fundamental common definitions.
Examples:
- Kotlin Application with libraries
- Set of related Service Applications

## Gradle Multi Projects

A gradle multi project is introduced [here](https://docs.gradle.org/current/userguide/intro_multi_project_builds.html).
![Gradle Multi project example](./images/gradle-basic-9.png "How it works")

A deeper explanation is found in [Sharing Build Logic between Subprojects](https://docs.gradle.org/current/userguide/sharing_build_logic_between_subprojects.html), using convention plugins.
![Sharing Build Logic](./images/structuring-builds-3.png "Simplest build logic sharing")

This repo was built from the IntelliJ IDE new kotlin project with generated multi-module build code.  

## Adapting

Instructions on how to adapt this for your project.

### Components

Component samples:
- [utils](./utils) is a shareable library sample.
- [app](./app) is an executable sample, such as an application or a service, that depends on project libraries.

These samples can be used as a starting point, been adapted and extended to create new similar components.

Each component has a configuration file ("build.gradle.kts") defining dependencies and the component's specific characteristics.
See [application](./app/build.gradle.kts) and [library](./utils/build.gradle.kts). 

### Version Dependencies Catalog

A [dependencies catalog](./gradle/libs.versions.toml) defines the proper version for each dependency.

### Common Build Logic

A Convention Plugin with common build logic is defined into [buildSrc](./buildSrc/src/main/kotlin/kotlin-jvm.gradle.kts) to enable easy reusability of definitions and build configurations.

### Artifact Publishing

Artifact publishing for each component can be easily adapted, including the repository.
Full instructions [here](https://docs.gradle.org/current/userguide/publishing_maven.html).
