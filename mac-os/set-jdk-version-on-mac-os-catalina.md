# Set JDK version on MAC OS \(Catalina\)

See the JDK versions installed: 

`$ /usr/libexec/java_home -V`

Then set the version with vim ~/.zshrc \(in this example 1.8.0\_231\)

`export JAVA_HOME=$(/usr/libexec/java_home -v 1.8.0_231)`

You have to open another terminal window in order to see the change.

