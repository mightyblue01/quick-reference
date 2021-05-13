(1) First run /usr/libexec/java_home -V which will output something like the following:

    Matching Java Virtual Machines (3):
    1.8.0_05, x86_64:   "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_05.jdk/Contents/Home
    1.6.0_65-b14-462, x86_64:   "Java SE 6" /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
    1.6.0_65-b14-462, i386: "Java SE 6" /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home

(2) Pick the version you want to be the default (1.6.0_65-b14-462 for arguments sake) then:

    export JAVA_HOME=`/usr/libexec/java_home -v 1.6.0_65-b14-462`

    Now when you run java -version you will see:

    java version "1.6.0_65"
    Java(TM) SE Runtime Environment (build 1.6.0_65-b14-462-11M4609)
    Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-462, mixed mode)
    Add the export JAVA_HOME… line to your shell’s init file.

(3) For Bash :

    export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)
    For Fish 

    set -x JAVA_HOME (/usr/libexec/java_home -d64 -v1.8)
    Updating the .zshrc file should work:

    nano ~/.zshrc

    export JAVA_HOME=$(/usr/libexec/java_home -v 1.8.0)
    Press CTRL+X to exit the editor Press Y to save your changes

(4) Source -  

    source ~/.zshrc
    echo $JAVA_HOME
    java -version
