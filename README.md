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
   5. commit and push
5. publish GitHub Pages from a branch
   1. visit https://github.com/caine-lea/maven-repo/settings
   2. click 'Pages' tab in sidebar
   3. deploy from master/(root)
   4. wait a moment for taking effect
   5. refresh the page
6. modify maven repo url
   ```
   subprojects {
       group = 'core.demo'
       version = '1.0.0'
   
       repositories {
           maven {
               url 'https://caine-lea.github.io/maven-repo/'
               content {
                   includeGroupByRegex 'core\\.framework.*'
               }
           }
       }
   }
   ```