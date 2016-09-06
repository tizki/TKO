[Jenkins](https://jenkins.io/) has a great integration with groovy. There are several groovy plugins for Jenkins such as: groovy-plugin, groovy post-build plugin and many more. there is also another powerful tool which is the script console. In this post, I'll show some basic Jenkins operation that can be done with groovy.

#### Jenkins Script Console

The console can be opened from the "Manage Jenkins" -&gt; "Script Console" or directly through http://server/jenkins/script.

The basic command is getting the jenkins instance:

```Java

def jenkins = Jenkins.getInstance()
