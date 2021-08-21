---
layout: guides
navbar: Guides
title: Java and Eclipse Setup
key: 1
---

<style>
img {
  max-width: 100%;
  height: auto;

  background-color: whitesmoke;
  border-radius: 4px;
  padding: 0.25ex;
}
</style>

This guide will walkthrough the steps necessary to install the latest versions of Java and Eclipse on your local system.

## Install Java 15

You need to make sure you have the latest version of Java **Standard** Edition (SE) **Development** Kit **15** (JDK 15) installed on your system. When downloading, keep in mind:

  - Do NOT download Java 8, Java 11, or Java 14. We will be using Java 15 in class. There are some differences between Java 8, Java 11, Java 14, and Java 15, and the lecture code may not compile on your system.

  - Do NOT download Java Enterprise Edition (EE). We will be using the Standard Edition (SE) in class. Java EE is used to create enterprise applications.

  - Do NOT download just the Java Runtime Environment (JRE). The Java Development Kit (JDK) includes the JRE, which is necessary to run Java code. The JDK also includes the Java compiler, which we will need in class.

To install the Java SE 15 JDK, go to:

<https://www.oracle.com/java/technologies/javase-jdk15-downloads.html>

Download the appropriate file for your system. Run the installer and follow the prompts.

Once done, open a terminal window and verify the version using `java -version` and `javac -version`. The output will be similar to:

```shell
% java --version
java 15.0.2 2021-01-19
Java(TM) SE Runtime Environment (build 15.0.2+7-27)
Java HotSpot(TM) 64-Bit Server VM (build 15.0.2+7-27, mixed mode, sharing)
```

```shell
% javac --version
javac 15.0.2
```

Note that `%` above indicates the command prompt, and the lines below that are the output.

<i class="fas fa-info-circle"></i>
Java [removed auto-update capability](https://www.oracle.com/technetwork/java/javase/11-relnote-issues-5012449.html#Important_Changes) for Windows and MacOS systems. You will need to manually check when new versions of Java 15 are released.
{: .notification }

## Install Eclipse

![About Eclipse]({{ "/images/abouteclipse.png" | relative_url }}){: style="width: 546px;"}

You need to make sure you have the latest **Eclipse IDE for Java Developers** package for **Eclipse 2020-12**. The direct download link is:

<https://www.eclipse.org/downloads/packages/release/2020-12/r/eclipse-ide-java-developers>

Do NOT download the IDE for Java EE Developers, as we are using Java SE in class. There are installers available for Windows, Mac OSX, and Linux. Once downloaded, double-click the installer.

<i class="fas fa-info-circle"></i>
Mac Users: I recommend you move the Eclipse.app file into your "Applications" folder for easy access.
{: .notification }

## Setup Folders (Optional)

I recommend you create a `CS 212` or `cs212` folder, and within it create these subfolders:

  - `Workspace`: This will be the folder for your Eclipse workspace.

  - `Repositories`: This will be the folder for your GitHub repositories that will be used for homework and project submission (and Eclipse).

    You can configure Eclipse to always save your CS 212 code in this folder in the "Version Control (Team) » Git" settings:

    ![Git Settings]({{ "/images/config-team-git-default.png" | relative_url }}){: style="width: calc(1572px * 0.4);"}  

Eclipse does not behave well when you combine or nest the `Workspace` and `Repositories` folders. Keep these separate!
