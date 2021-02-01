Windows:
Copy to c:/tmp/napBrowser

Linux:
1. install  java min. 8

2. If toolkit error:
https://askubuntu.com/questions/695560/assistive-technology-not-found-awterror
Description:
This can be done by editing the accessibility.properties file for OpenJDK 8 (change the version to whichever is actually in use on your system):
sudo vim /etc/java-8-openjdk/accessibility.properties
Comment out the following line:
#assistive_technologies=org.GNOME.Accessibility.AtkWrapper

3. If libgconf-2-4 error:
https://support.circleci.com/hc/en-us/articles/360004086734-error-while-loading-shared-libraries-libgconf-2-so-4-cannot-open-shared-object-file-No-such-file-or-directory?utm_medium=SEM&utm_source=gnb&utm_campaign=SEM-gnb-DSA-Eng-ni&utm_content=&utm_term=dynamicSearch-&gclid=EAIaIQobChMIvoOB_fnj7AIVRht7Ch1W0QulEAAYASAAEgIGPPD_BwE
sudo apt-get install libgconf-2-4


========================
BUILD OUTPUT DESCRIPTION
========================

When you build an Java application project that has a main class, the IDE
automatically copies all of the JAR
files on the projects classpath to your projects dist/lib folder. The IDE
also adds each of the JAR files to the Class-Path element in the application
JAR files manifest file (MANIFEST.MF).

To run the project from the command line, go to the dist folder and
type the following:

java -jar "NapBrowser.jar" 

To distribute this project, zip up the dist folder (including the lib folder)
and distribute the ZIP file.

Notes:

* If two JAR files on the project classpath have the same name, only the first
JAR file is copied to the lib folder.
* Only JAR files are copied to the lib folder.
If the classpath contains other types of files or folders, these files (folders)
are not copied.
* If a library on the projects classpath also has a Class-Path element
specified in the manifest,the content of the Class-Path element has to be on
the projects runtime path.
* To set a main class in a standard Java project, right-click the project node
in the Projects window and choose Properties. Then click Run and enter the
class name in the Main Class field. Alternatively, you can manually type the
class name in the manifest Main-Class element.
