Jenkins has a great integration with groovy. There are several groovy plugins for Jenkins such as: groovy-plugin, groovy post-build plugin and many more. there is also another powerful tool which is the script console. In this post, I'll show some basic Jenkins operation that can be done with groovy.
#### Jenkins Script Console
The console can be opened from the "Manage Jenkins" -> "Script Console" or directly through http://server/jenkins/script.
The basic command is getting the jenkins instance:
```Java
def jenkins = Jenkins.getInstance()
```
Let’s see how we can get some information about our Jenkins environment
Print current running version
```Java
println Jenkins.getInstance().getVersion()
```
Printing all available JDKs
```Java
println jenkins.getInstance().getJDKs()
```
Printing all nodes
```Java
Jenkins.getInstance().getNodes().each{ 
  println it.displayName}
}
```

Another option is to call Jenkins’ actions, for example:
```Java
jenkins.restart()
jenkins.safeRestart()
jenkins.reload()
```

Lastly, let’s get instances of other object, for example:
Getting a job name “foo”
```Java
jenkins.getItem(“foo”)
```
Getting a computer named “bar”
```Java
jenkins.getComputer(“bar”)
```
Getting a plugin
```Java
Jenkins.getInstance().getPlugin("matrix-project")
```
