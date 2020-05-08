# Stage Two

This stage is set to expand further on the ansible configuration.

The goal is to create a set of default applications to install into a new development machine build.

This includes:
- Git
- Java JDK 11
- Maven

The aim is for the machine to be able to be built up with these components - be able to pull a specific commit using git and
is able to run maven tests on the code to verify it is correct.

For this to work we also need to be able to check the versions are installed correctly.

We want to check that:
- `java -version` outputs 11
- `echo $JAVA_HOME` outputs a path to the JDK folder, just check it isn't empty.
