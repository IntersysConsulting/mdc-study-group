# Interactive Notebooks with Apache Zeppelin

By Oscar Vargas Torres

## About

This talk is to help people interested in using Apache Zeppelin capabilities to leverage different interpreters in the same Notebook.
Part of the difficulties may be to setup the installation of Zeppelin, and one of the purposes is to document the process on Mac OS X. 

## How this talk will help me to become a better consultant (developer/software engineer)

+ You will learn how to install Apache Zeppelin to leverage the different interpreters it has: Spark (with Scala and Python), SQL, R, and others that are commonly used with *Big Data*.

## How to use talk material

The material of this talk is a mainly the documentation and a Zeppelin Notebook: `HelloZeppelin.json`.

1. an Anaconda installation with Python 3.6.5
2. a clone of master branch of Zeppelin repository. [Github mirror here](git@github.com:apache/zeppelin.git).
3. `git`, Java SDK (>= 7.0), maven (`mvn`), `R` installed with `evaluate` packages (see the following instruction)

    ```
    > install.packages("evaluate", dependencies=TRUE)
    ```
4. Inside the `zeppelin` repo, update all the `pom.xml` to use scala 2.11 with

    ```
    # update all pom.xml to use scala 2.11
    ./dev/change_scala_version.sh 2.11
    ```

    as explained in the official docs: https://zeppelin.apache.org/docs/0.7.3/install/build.html

5. Build with something similar to this (I had to modify the `flink/pom.xml` to use `<scala.macros.version>2.1.1</scala.macros.version>`):

    ```
    mvn package \
    --batch-mode package \
    -Phelium-dev \
    -Pscala-2.11 \
    -Dscala.version=2.11.12 \
    -Dscala.binary.version=2.11 \
    -Pbuild-distr \
    -Pspark-2.1 \
    -Dspark.version=2.1.1 \
    -Pr \
    -Phadoop-2.7 \
    -Dhadoop.version=2.7.3 \
    -Dmaven.findbugs.enable=false \
    -Drat.skip=true \
    -Dcheckstyle.skip=true \
    -DskipTests
    ```

6. Create an alias for the `zeppelin-daemon.sh`. Mine (declared in my `~/.zshenv`) is: 

    ```
    alias zep='/Users/ovargas/gitRepos/zeppelin/zeppelin-distribution/target/zeppelin-0.9.0-SNAPSHOT/zeppelin-0.9.0-SNAPSHOT/bin/zeppelin-daemon.sh'
    ```

7. Use your alias to start/stop/restart your zeppelin server.
8. After Zeppelin has started successfully, go to http://localhost:8080 with your web browser.
9. (Optional) Install `graph-tool` into an Anaconda environment, following [this tutorial](https://medium.com/@ronie/installing-graph-tool-for-python-3-on-anaconda-3f76d9004979). It worked for me with an environment having Python 3.6.5 only (tried with 3.6.4 version first, which is a different version of Python3 that successfuly installs `graph-tool` with brew cask).