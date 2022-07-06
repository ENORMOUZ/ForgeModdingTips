# Guide on setting up HotSwap on Java 8
Hot-Swapping is a way to "reload" your changes to the file in real-time so you do not have to restart and wait for your code to start again. There are some limitations to this, which are listed on the [HotSwapAgent website](http://hotswapagent.org/#features). <br>

## Java
To start, you need to download the latest version of Java 8 **that HotSwapAgent is supported on**. This is very important as without it, hot-swapping will not work. You can find the latest supported version of Java [here](https://github.com/dcevm/dcevm/releases). It is very likely that this is **not** the latest version of Java 8, or the version of Java that is installed on your computer. <br>

At the time of writing this guide, the latest supported version of Java is Java version **8u181**.
To download it, go to the [Java 8 archive downloads website](https://www.oracle.com/sg/java/technologies/javase/javase8-archive-downloads.html) and scroll down until you reach "Java SE Runtime Environment 8u181". Select the installer that is applicable for your operating system. For me, that is the Windows x64 .exe installer. To download it, you will need to sign up for an account at [oracle.com](https://profile.oracle.com/myprofile/account/create-account.jspx). <br>
After you have downloaded the installer, you can proceed on with the installation of Java 8.

## DCEVM
Now, you need to download the patch for the version of Java that you have installed, [here](https://github.com/dcevm/dcevm/releases). For my case, it is [Java 8u181](https://github.com/dcevm/dcevm/releases/tag/light-jdk8u181%2B2). Install the .jar and run it.

In the program, you will find the versions of Java that you have installed. Select the version which is DCEVM supported (in this case, it is Java version 1.8.0_181) and click "Install DCEVM as altjvm". I do not recommend replacing it with DCEVM as that may affect your other programs.

## Workspace
> I use IntelliJ IDEA so this workspace is IntelliJ.
In IntelliJ, go to your project and click on "Edit configurations" inside your configurations. Now, in "Application -> Minecraft Client", you can select the Java version to run your Minecraft instance. Select the Java version which you have just installed (in this case, Java 8 (named jre1.8.0_181)). Then, in "CLI arguments", enter "-XXaltjvm=dcevm". Click "Apply" and close the window.

## Notes
Now, when you start your "Minecraft Client" configuration with the Debug option, you can press Ctrl-Shift-F9 to reload your changes to your code in real-time. Note that some features (such as Events) may stop working once you reload your code and you will have to restart the configuration for them to work.
Hot-swapping will not work with things like Mixins as those are compiled at the start and cannot be reloaded.