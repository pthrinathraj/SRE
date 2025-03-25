# 🧱 Section A: Maven

## ✅ 1. Introduction

Maven is a powerful build automation and dependency management tool primarily used for Java projects. It uses a declarative XML configuration file (`pom.xml`) to define project structure, dependencies, build lifecycle, and plugins. Maven is widely adopted in enterprise DevOps and CI/CD pipelines for building, testing, and deploying Java-based applications.

---

## ✅ 2. Key Components

- **POM (Project Object Model)** – Central XML configuration file (`pom.xml`) that drives the build.
- **Dependencies** – External libraries the project needs, automatically downloaded from Maven Central or private repositories.
- **Repositories** – Locations from which Maven downloads (remote) or caches (local) dependencies.
- **Phases** – Part of the Maven lifecycle (`compile`, `test`, `package`, `install`, `deploy`).
- **Plugins** – Extend Maven functionality (e.g., compiler plugin, surefire for testing).
- **Goals** – Tasks that are bound to lifecycle phases (e.g., `compile`, `clean`, `test`).

---

## ✅ 3. Common Commands

| Command | Description |
|---------|-------------|
| `mvn clean` | Deletes `target/` directory and cleans build. |
| `mvn compile` | Compiles Java source code. |
| `mvn test` | Runs unit tests using Surefire plugin. |
| `mvn package` | Packages the compiled code into a `.jar` or `.war`. |
| `mvn install` | Installs built artifact into local repository (`~/.m2`). |
| `mvn deploy` | Deploys artifact to remote repository (e.g., Nexus, Artifactory). |
| `mvn dependency:tree` | Shows project dependencies and hierarchy. |
| `mvn versions:display-dependency-updates` | Displays available updates. |

---

## ✅ 4. Pros & Cons

### ✅ Pros:
- Standardization across Java projects
- Excellent dependency management and transitive resolution
- Integration with IDEs and CI/CD tools (Jenkins, GitHub Actions)
- Plugin ecosystem for testing, code coverage, deployment
- Supports multi-module projects

### ❌ Cons:
- XML configuration can become verbose
- Complex dependency resolution can be difficult to debug
- Slower for large projects unless optimized

---

✅ Maven is a foundational tool for Java-based DevOps pipelines and integrates well with automation servers like Jenkins.
# 🧱 Section B: Maven Interview Prep – Basic Questions (40)

This section covers 40 basic Maven interview questions with examples and simple explanations.

---

### ✅ 1. What is Maven?
Maven is a build automation tool used primarily for Java projects, providing project management, dependency management, and standardized build lifecycles.

---

### ✅ 2. What file defines a Maven project?
`pom.xml` – the Project Object Model file.

---

### ✅ 3. How do you compile a Maven project?
```bash
$ mvn compile
```

---

### ✅ 4. How do you clean a Maven project?
```bash
$ mvn clean
```

---

### ✅ 5. How do you build a `.jar` file using Maven?
```bash
$ mvn package
```

---

### ✅ 6. How do you run unit tests?
```bash
$ mvn test
```

---

### ✅ 7. What does `mvn install` do?
Installs the built artifact to the local Maven repository.

---

### ✅ 8. Where is the local Maven repository?
`~/.m2/repository`

---

### ✅ 9. What command is used to deploy an artifact to a remote repository?
```bash
$ mvn deploy
```

---

### ✅ 10. What is a Maven plugin?
A collection of goals that extend Maven’s build capabilities.

---

### ✅ 11. What are Maven coordinates?
Group ID, Artifact ID, Version – used to uniquely identify a dependency.

---

### ✅ 12. What is the default packaging type in Maven?
`jar`

---

### ✅ 13. How do you skip tests during build?
```bash
$ mvn install -DskipTests
```

---

### ✅ 14. What is a dependency in Maven?
An external library required by your project.

---

### ✅ 15. How does Maven resolve transitive dependencies?
Maven automatically downloads nested dependencies from repositories.

---

### ✅ 16. What is the purpose of the `clean` phase?
Deletes the `target/` directory to ensure a fresh build.

---

### ✅ 17. How do you list all dependencies of a project?
```bash
$ mvn dependency:tree
```

---

### ✅ 18. What is the Maven lifecycle?
Phases: `validate`, `compile`, `test`, `package`, `verify`, `install`, `deploy`.

---

### ✅ 19. How do you add a dependency in `pom.xml`?
```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-core</artifactId>
  <version>5.3.0</version>
</dependency>
```

---

### ✅ 20. How do you run a Maven project with a specific profile?
```bash
$ mvn install -Pproduction
```

---

### ✅ 21. What is a parent POM?
Defines common configuration and dependencies for child projects.

---

### ✅ 22. What is a multi-module project in Maven?
A project that aggregates multiple submodules under a parent POM.

---

### ✅ 23. What does `mvn validate` do?
Checks if the project is correct and all necessary information is available.

---

### ✅ 24. How do you re-download dependencies?
```bash
$ mvn dependency:purge-local-repository
```

---

### ✅ 25. How do you override a plugin version?
Declare the version in the `plugins` section of the `build` block in `pom.xml`.

---

### ✅ 26. How do you configure Maven settings globally?
Using `~/.m2/settings.xml`

---

### ✅ 27. What is the effective POM?
Merged result of all POMs affecting the project. View it using:
```bash
$ mvn help:effective-pom
```

---

### ✅ 28. What is Maven Central?
The default public repository for downloading dependencies.

---

### ✅ 29. What is the purpose of the `target/` directory?
Holds all build outputs (compiled classes, packaged JARs, reports).

---

### ✅ 30. What is the `compile` scope in Maven?
Dependency is available at compile time and included in the final artifact.

---

### ✅ 31. How do you exclude a transitive dependency?
```xml
<exclusions>
  <exclusion>
    <groupId>...</groupId>
    <artifactId>...</artifactId>
  </exclusion>
</exclusions>
```

---

### ✅ 32. How do you specify a plugin in Maven?
```xml
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
</plugin>
```

---

### ✅ 33. What is a goal in Maven?
A specific task that contributes to building and managing a project (e.g., `compile`, `install`).

---

### ✅ 34. How do you run a specific goal?
```bash
$ mvn dependency:tree
```

---

### ✅ 35. What happens when you run `mvn package`?
It runs all phases before `package` (clean → validate → compile → test → package).

---

### ✅ 36. What is a snapshot version?
A development version that can change frequently (e.g., `1.0-SNAPSHOT`).

---

### ✅ 37. What are the common scopes of dependencies?
- `compile`
- `provided`
- `runtime`
- `test`
- `system`
- `import`

---

### ✅ 38. How do you enable verbose output in Maven?
```bash
$ mvn install -X
```

---

### ✅ 39. How do you check for outdated dependencies?
```bash
$ mvn versions:display-dependency-updates
```

---

### ✅ 40. How do you add a plugin repository?
```xml
<pluginRepositories>
  <pluginRepository>
    <id>my-repo</id>
    <url>https://repo.example.com/maven2</url>
  </pluginRepository>
</pluginRepositories>
```

---

✅ Next: Intermediate Maven Questions
# 🧱 Section B: Maven Interview Prep – Intermediate Questions (40)

This section covers 40 intermediate-level Maven interview questions with explanations and examples tailored for real-world DevOps and CI/CD usage.

---

### ✅ 1. What is the difference between `mvn clean install` and `mvn install`?
- `clean install`: deletes previous build outputs before building.
- `install`: skips cleaning; may cause issues if stale files exist.

---

### ✅ 2. How do you create a multi-module Maven project?
Define a parent POM with `<modules>` section pointing to each child module folder.

---

### ✅ 3. What is the role of the `<dependencyManagement>` tag?
It allows defining common versions and scopes in the parent POM, which child modules can inherit.

---

### ✅ 4. How do you create and use custom build profiles?
```xml
<profiles>
  <profile>
    <id>dev</id>
    <properties>
      <env>development</env>
    </properties>
  </profile>
</profiles>
```
Run with: `mvn install -Pdev`

---

### ✅ 5. What’s the difference between `<dependency>` and `<plugin>`?
- `<dependency>`: libraries used during build/runtime.
- `<plugin>`: tools used during build process (e.g., compiler, surefire).

---

### ✅ 6. How do you override dependency versions in transitive dependencies?
Use `<dependencyManagement>` or declare the dependency explicitly with the desired version.

---

### ✅ 7. What is the purpose of the `maven-compiler-plugin`?
Compiles Java code. Used to configure Java version:
```xml
<configuration>
  <source>1.8</source>
  <target>1.8</target>
</configuration>
```

---

### ✅ 8. How do you generate source JARs in Maven?
```bash
$ mvn source:jar
```

---

### ✅ 9. How do you skip integration tests but still run unit tests?
```bash
$ mvn verify -DskipITs
```

---

### ✅ 10. What are lifecycle bindings?
The default goals that are bound to lifecycle phases, e.g., `compile` phase → `compiler:compile`

---

### ✅ 11. What is the `site` phase used for?
Generates project documentation using `maven-site-plugin`.

---

### ✅ 12. What is the difference between `compile` and `provided` scope?
- `compile`: required for compile and runtime.
- `provided`: required for compile, but provided by container at runtime (e.g., servlet-api).

---

### ✅ 13. What does the `dependency:analyze` goal do?
Analyzes used/unused declared dependencies and suggests cleanup.

---

### ✅ 14. How do you deploy a snapshot version to a repository?
Ensure the version ends in `-SNAPSHOT`, and run:
```bash
$ mvn deploy
```

---

### ✅ 15. How do you configure a corporate proxy in Maven?
Add to `settings.xml`:
```xml
<proxies>
  <proxy>
    <id>corp</id>
    <active>true</active>
    <protocol>http</protocol>
    <host>proxy.company.com</host>
    <port>8080</port>
  </proxy>
</proxies>
```

---

### ✅ 16. What is the difference between `install` and `deploy` phases?
- `install`: copies artifact to local repository.
- `deploy`: uploads artifact to remote repository.

---

### ✅ 17. How do you create a `.war` file instead of `.jar`?
Set `<packaging>war</packaging>` in your `pom.xml`.

---

### ✅ 18. How do you run only failed tests again?
```bash
$ mvn test -Dsurefire.rerunFailingTestsCount=1
```

---

### ✅ 19. What is the role of `maven-enforcer-plugin`?
Enforces project rules (e.g., dependency versions, Java version) during build.

---

### ✅ 20. How do you publish to Nexus or Artifactory?
Configure `<distributionManagement>` in `pom.xml`, and credentials in `settings.xml`.

---

### ✅ 21. How do you generate a dependency report?
```bash
$ mvn project-info-reports:dependencies
```

---

### ✅ 22. How do you analyze classpath issues?
Use:
```bash
$ mvn dependency:build-classpath
```

---

### ✅ 23. How do you include resources (e.g., config files) in the final JAR?
Ensure they're placed in `src/main/resources/`

---

### ✅ 24. What is the `<exclusions>` tag used for?
To prevent unwanted transitive dependencies from being included.

---

### ✅ 25. What is the Maven Wrapper?
A script (`mvnw`) that allows a project to build with a specific Maven version without requiring a global install.

---

### ✅ 26. How do you run Maven with custom JVM options?
```bash
$ MAVEN_OPTS="-Xmx1024m" mvn package
```

---

### ✅ 27. How do you enforce consistent formatting or linting?
Use plugins like `formatter-maven-plugin` or `checkstyle-maven-plugin`.

---

### ✅ 28. What does `mvn dependency:purge-local-repository` do?
Forces re-download of all dependencies by clearing the local repo.

---

### ✅ 29. How do you override values in `pom.xml` via CLI?
```bash
$ mvn install -Dmyprop=value
```

---

### ✅ 30. What is the order of POM inheritance?
Child POM → Parent POM → Super POM

---

### ✅ 31. How do you add a custom plugin repository?
```xml
<pluginRepositories>
  <pluginRepository>
    <id>custom</id>
    <url>https://repo.example.com/maven2</url>
  </pluginRepository>
</pluginRepositories>
```

---

### ✅ 32. How do you run a plugin goal without affecting lifecycle?
```bash
$ mvn dependency:tree
```

---

### ✅ 33. How do you skip a specific test?
```bash
$ mvn test -Dtest=!MySpecificTest
```

---

### ✅ 34. How do you bind a plugin to a specific phase?
```xml
<execution>
  <phase>package</phase>
  <goals><goal>shade</goal></goals>
</execution>
```

---

### ✅ 35. What is a BOM in Maven?
Bill Of Materials – a POM that manages dependency versions across multiple modules.

---

### ✅ 36. How do you view the final resolved list of dependencies?
```bash
$ mvn dependency:tree -Dverbose
```

---

### ✅ 37. How do you attach a classifier to an artifact?
Set `<classifier>javadoc</classifier>` or `sources`, etc.

---

### ✅ 38. What is the use of `build-helper-maven-plugin`?
Adds additional source folders, attach artifacts, or manage build properties.

---

### ✅ 39. How do you validate your `pom.xml` syntax?
```bash
$ mvn validate
```

---

### ✅ 40. What happens if you don't specify version in a dependency?
Build fails unless the version is inherited from `<dependencyManagement>`.

---

✅ Next: Advanced Maven Questions

# 🧱 Section B: Maven Interview Prep – Advanced Questions (40)

This section includes 40 advanced Maven interview questions for experienced developers and DevOps engineers, covering plugin internals, build performance, CI/CD integration, and troubleshooting.

---

### ✅ 1. How does Maven resolve dependency conflicts?
Maven uses "nearest definition" and "first declared wins" strategy when resolving conflicting transitive dependencies.

---

### ✅ 2. What is the role of the Super POM?
It’s the base POM from which all POMs inherit by default, containing default configurations like the central repository.

---

### ✅ 3. How do you override Super POM configurations?
By redefining them in your own `pom.xml` or a parent POM.

---

### ✅ 4. What is dependency mediation?
The process Maven uses to resolve version conflicts among transitive dependencies.

---

### ✅ 5. What is the use of the `maven-invoker-plugin`?
Used to run integration tests on Maven projects (e.g., test generated artifacts or plugins).

---

### ✅ 6. How do you debug a Maven plugin execution?
Use:
```bash
$ mvn -X
```
Or inspect logs generated with `debug` level.

---

### ✅ 7. What are extension points in Maven?
Maven allows plugins to hook into the lifecycle phases via `goals`.

---

### ✅ 8. How do you run Maven behind a corporate proxy with authentication?
Configure `<proxies>` and `<servers>` with credentials in `settings.xml`.

---

### ✅ 9. How do you create a custom Maven plugin?
Create a new Java project with `mojo` annotations and define goals, then package with:
```bash
$ mvn plugin:descriptor
```

---

### ✅ 10. How do you build a Maven plugin to modify compiled bytecode?
Use plugins like ASM/Byte Buddy or integrate your custom logic in a lifecycle-bound plugin.

---

### ✅ 11. What is the use of `maven-shade-plugin`?
Creates a "fat" or "uber" JAR with all dependencies bundled, also supports package relocation.

---

### ✅ 12. How do you exclude a dependency from the shaded JAR?
Use `<filters>` in the shade plugin configuration.

---

### ✅ 13. What is a transitive dependency and how is it resolved?
A dependency pulled in by another dependency; Maven resolves them recursively from the repository.

---

### ✅ 14. What are plugin goals?
Specific tasks that a plugin can perform (e.g., `compiler:compile`, `clean:clean`).

---

### ✅ 15. How do you enforce dependency convergence in Maven?
Use the `enforcer` plugin with `requireUpperBoundDeps` rule.

---

### ✅ 16. How do you analyze duplicate or conflicting dependencies?
```bash
$ mvn dependency:tree -Dverbose
```

---

### ✅ 17. What is the role of the `project.build.outputDirectory` property?
Specifies the path for compiled `.class` files (typically `target/classes`).

---

### ✅ 18. How do you build an OSGi bundle using Maven?
Use the `maven-bundle-plugin`.

---

### ✅ 19. How does Maven handle checksum validation?
When downloading artifacts, it verifies their checksum against `.sha1` files.

---

### ✅ 20. How do you pass environment variables to Maven during build?
Use:
```bash
$ export VAR=value && mvn install
```
or define `<env>` properties in profiles.

---

### ✅ 21. How can you override a POM dependency with a newer version in the command line?
```bash
$ mvn install -Dversion.property=1.2.3
```

---

### ✅ 22. What happens if two dependencies bring in conflicting classes?
Runtime may throw `ClassNotFoundException` or `NoSuchMethodError`.

---

### ✅ 23. How do you analyze which dependency introduced a specific transitive artifact?
Use:
```bash
$ mvn dependency:tree -Dincludes=groupId:artifactId
```

---

### ✅ 24. How do you build a release version in Maven?
Remove `-SNAPSHOT`, tag it, and deploy to the release repo.

---

### ✅ 25. How do you prevent snapshot dependencies in release builds?
Use `enforcer` plugin with `requireReleaseDeps`.

---

### ✅ 26. What is the difference between `target/classes` and `target/test-classes`?
- `target/classes`: compiled main source code.
- `target/test-classes`: compiled test classes.

---

### ✅ 27. How do you validate the classpath at runtime?
Add diagnostic steps in tests or log `System.getProperty("java.class.path")`.

---

### ✅ 28. How do you manage third-party JARs not in public repositories?
Install them to local repo with:
```bash
$ mvn install:install-file -Dfile=lib/custom.jar -DgroupId=com.example ...
```

---

### ✅ 29. What is the difference between `pom` packaging and `jar`?
`pom`: used for parent or aggregator projects, no build artifacts.
`jar`: produces a `.jar` file.

---

### ✅ 30. How does Maven support parallel builds?
```bash
$ mvn -T 1C install
```
Builds modules in parallel using threads based on CPU cores.

---

### ✅ 31. How do you disable a plugin during build?
Use:
```bash
$ mvn install -Dplugin.skip=true
```
Where the plugin supports the skip flag.

---

### ✅ 32. How do you profile Maven build performance?
Use `mvn -X` or `mvn -Dorg.slf4j.simpleLogger.log.org.apache.maven.cli.transfer.Slf4jMavenTransferListener=debug`

---

### ✅ 33. How do you deploy different artifacts from the same build?
Use classifiers or attach artifacts via `build-helper-maven-plugin`.

---

### ✅ 34. How do you configure CI/CD builds to publish snapshots only?
Check for `-SNAPSHOT` version before invoking `mvn deploy`.

---

### ✅ 35. What is the use of `<optional>true</optional>` in dependency?
Prevents transitive propagation of the dependency to other modules.

---

### ✅ 36. What is the Maven "wagon"?
Transport abstraction layer used by Maven to fetch artifacts (HTTP, FTP, S3, etc.)

---

### ✅ 37. How do you analyze the order of plugin execution?
Use `mvn help:effective-pom` or enable `-X` debug mode.

---

### ✅ 38. How do you clean up a corrupted `.m2` cache?
Delete corrupted artifacts manually or use:
```bash
$ mvn dependency:purge-local-repository
```

---

### ✅ 39. What is the impact of using snapshot dependencies in production?
Snapshots are mutable, non-repeatable, and discouraged in production environments.

---

### ✅ 40. How do you create a reproducible Maven build?
- Use dependency locking.
- Avoid snapshots.
- Pin plugin and dependency versions.
- Build inside a container.

---

✅ Next: Scenario-Based Maven Questions
