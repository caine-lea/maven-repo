# What is this?

maven repo for core-ng

# How to publish this repo?

1. update the least core-ng-project
   1. visit https://github.com/caine-lea/core-ng-project
   2. sync fork
2. reset to a commit on local
   1. open 'Git Log' tab in IDEA
   2. input version number, e.g. 8.1.4 and search
   3. right-click 'Reset Current Branch to Here...'
3. generate a release package using the following commands, for further information, please refer to 'core-ng-project/build.gradle'
   ```BASH
   cd /c/Caine/Code/caine-lea/core-ng-project/
   ./gradlew -PmavenURL=/c/Caine/Code/caine-lea/maven-repo clean publish
   ```

   ```PowerShell
   cd C:\Caine\Code\caine-lea\core-ng-project\
   .\gradlew -PmavenURL=C:\Caine\Code\caine-lea\maven-repo clean publish
   ```
4. commit and push https://github.com/caine-lea/maven-repo
   1. open the project /maven-repo using IDEA
   2. right-click 'Reload from Disk' in 'Project' tab
   3. open 'Commit' tab
   4. check all Changes and Unversioned Files
   5. Commit
 




1. install JDK 11
2. set JAVA_HOME environment variable
3. use JDK 11 as the project SDK
4. create a new folder (maven-repo)
5. to publish the package, run the below commands
6. 
7. 



6. commit and push /maven-repo
7. visit https://github.com/food-truck/core-ng-for-test-executor/settings/pages
8. deploy from master
9. refresh the page
10. copy the URL of this repo (https://food-truck.github.io/core-ng-for-test-executor/)

# How to use this repo?
https://food-truck.github.io/core-ng-for-test-executor/maven-repo

<pre>
subprojects {
    group = 'core.demo'
    version = '1.0.0'

    repositories {
        maven {
            url 'https://food-truck.github.io/core-ng-for-test-executor/maven-repo/'
            content {
                includeGroupByRegex 'core\\.framework.*'
            }
        }
    }
}
</pre>