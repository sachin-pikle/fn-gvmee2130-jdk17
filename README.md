# fn-gvmee2130-jdk17
Function with GraalVM Enterprise Native Image 21.3.0 JDK 17

Generated using Shaun Smith's [GraalVM Native Image-based function init-images](https://github.com/shaunsmith/graalvm-fn-init-images)

## Prerequisites

GraalVM Enterprise container images are stored in `https://container-registry.oracle.com`. You will need an Oracle account (doesn't require a credit card!) to accept the GraalVM Enterprise license on `container-registry.oracle.com >> GraalVM >> native-image-ee`.

1. Go to https://container-registry.oracle.com.

2. Go to `GraalVM >> native-image-ee`.

3. Click `Sign in`.

4. You will see the Oracle Login screen. If you have an account, enter your user and password to login. If you don't have an account scroll down to the Create a new Account section and create you free account (no credit card required).

5. Once you've signed in, view and accept license.

## Deploy your function

1. From a terminal like OCI Cloud Shell (or on local), login to the container registry.

    ```shell
    docker login container-registry.oracle.com -u <ORACLE_ACCOUNT_USER_NAME>
    ```
    When prompted, enter your password and hit enter.

2. Once you've logged in to container-registry.oracle.com, run `fn deploy`.

    ```shell
    fn -v deploy --app <app-name>
    ```
    This will use a multistage docker build as per the steps in the [Dockerfile](./Dockerfile) to generate an ahead-of-time compiled native executable for the function and deploy it to OCI.

3. (Optional) From the console, go to the function application and enable function logs and traces.

4. Invoke the function and check the time it takes to run.

    ```shell
    fn invoke <app-name> fn-gvmee2130-jdk17
    ```