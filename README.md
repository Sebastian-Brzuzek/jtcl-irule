# Introduction

This is an extension to [JTcl](http://jtcl.kenai.com/) that implements all the functionality F5 added to the Tcl language.

# Building

Fetch the [source](https://hg.kenai.com/hg/jtcl~jtcl-main) of [JTcl](http://jtcl.kenai.com/) using mercurial and replace the maven-jar-plugin config with the following in order to generate the test jar 

     <plugin>
        <artifactId>maven-jar-plugin</artifactId>
        <version>2.2</version>
        <executions>
          <execution>
            <id>default-jar</id>
            <phase>package</phase>
            <goals>
              <goal>jar</goal>
            </goals>
            <configuration>
              <archive>
                <manifest>
                  <mainClass>tcl.lang.Shell</mainClass>
                </manifest>
                <manifestEntries />
              </archive>
            </configuration>
          </execution>
          <execution>
            <goals>
              <goal>test-jar</goal>
            </goals>
          </execution>
        </executions>
      </plugin>

If you're using Mac Os X and don't have mercurial installed, I recommend using the [Source Tree](http://www.sourcetreeapp.com/) app from the app store.
It has excellent support for both git and mercurial.
The next step, is to build and install the artifacts into your local maven repository using

    mvn clean install -DskipTests
    
Next, fetch the source code of this project, and build code using 

    mvn clean package

This will generate a jar file named *jtcl-irule.jar* in the _target_ directory.
This jar file has to be added to the classpath of the JTcl shell script in order to override som of the functionality found in JTcl.
Place it in front of the other jar file - it will take precedence.

# What has been implemented so far
All the special irule operators except for the following have been implemented:
* and
* or
* not

# License
Both jtcl-irule and JTcl are released under a BSD-style license. 