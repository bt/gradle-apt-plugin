Gradle Apt Plugin
=================

A Gradle plugin for the Java annotation processor tool.

Usage
-------------------

Add the plugin to your `buildscript`'s `dependencies` and add the Jitpack repository to download it:

```groovy
buildscript {
  dependencies {
      repositories {
        maven {
          url "https://jitpack.io"
        }
        ...
      }
      
      classpath 'com.github.bt:gradle-apt-plugin:{latest-version}'
      ...
  }
}
```

Apply the `apt` plugin:

`apply plugin: 'apt'`

Add annotation processors dependencies using the `apt` configuration, i.e.:

`apt 'com.squareup.dagger:dagger-compiler:2.0.2'`

Run `gradle build`.

By default, the generated files in the `build/source/apt/` directory.

Options
-------

You can set various options for the plugin. To set the options, after the `apply plugin: 'apt'` line, add the following:

```groovy
apt {
  // The output directory for the generated source files.
  outputDirName = 'build/source/apt'
}
```

Credits
-------

This plugin is a fork of the original project by [@Jimdo](https://github.com/Jimdo/gradle-apt-plugin). As the project was discontinued, I have a need for annotation processing as one of my applications is heavily dependent on [Dagger2](https://google.github.io/dagger/).

This plugin is a slightly modified/cleaned-up version of [this Stackoverflow answer](http://stackoverflow.com/questions/16683944/androidannotations-nothing-generated-empty-activity)