# Report of Jason Zhang

# Individual Report

### Part 1 UML

#### 1.



![coursework](../../../../Desktop/coursework.jpeg)

## 

#### 2.Improment:

The view assembly was changed from java class to xml file,  so the contrller class was binded to the xml attributes.Having the view layer as xml will separate the code from the user interface and so as to make it easy to maintain and design the user interface.

Remove unused StringStack class to make StandardCalculator more convient to use.

Refactor all meaningless class name, method name and fields.Refactor the strcture of calculator.




## Part2: Answers for given question

### 1.(a) 

Firstly, automatically updating everyone's FallPackage would lead to jealous confusion, where the logic of the code each person was modifying could be broken by the other at any time. These updates may even contain a lot of bugs themselves. This will cause a developer to be unable to complete his development work smoothly.

Secondly, because logging the username, date and time for every update consumes a lot of resources and doesn't have any information to look up every update. Such records are not readable.

Thirdly, allows anyone to wind back any file will lead to code confusion and loss of business logic.

### (b)

A delta is a change made between two versions of a single file. In SVN, we prefer negative deltas because in this case the latest version of the trunk is fully available. When we roll back, it's like taking each delta to the previous version. This will perform faster because most of the time we only need to roll back a partial version

### (c)

i.Sync merge is merging all trunk changes into the current working child branch.

ii.SVN compares the files modified in the current commit with the same files in the previous version.

iii.Because this reduces the chance of conflicts, resolving conflicts can be time-consuming and error-prone.

iv. 

Step:

1 Check out a working copy of branch.

2 Merge the changes from the trunk into working copy. 

3 Commit the merged changes into branch.

4 Delete the working copy.

v.Conflicts may occur when the content of the file you modify is different from the remote one. This is because someone else has modified the code since you last updated the project, and the code modified by other people is different from the code you submitted this time. At this time, SVN needs us to resolve the conflict.

Step of solving conflict: Check if the code really has business logic conflicts. If there is, you need to confirm with other developers again. If there is no logical conflict, keep the respective modifications according to the code situation.

### (d)

The productivity of software engineers can be clearly displayed because SVN tracks every change made using commits, along with the time, date and who performed it. By going through the SVN revision and commit records, we can clearly see how much time this software engineer puts in every day. In addition, you can see all the attempts made by engineers to solve a business requirement.

### (e)

SVN is like a story line that reflects a lot of information. For example, we may judge whether the engineer follows TDD in development based on the order of commit submission. You can judge whether the engineer follows the principle of small-step submission based on the content and number of commits. It can be seen if he will refactor his code.



### 2.(a)

i.First, there is too much code reliance on third-party companies, which means that any changes can lead to overall larger changes and unpredictable bugs. At the same time, retrofitting code for third-party systems means that code is no longer a black box, and Jim may need to spend more time understanding it. 

ii.The adapter pattern should be used in this case, it will change the existing interface of the IndPers system to make it more useful and suitable for our code. Using the adapter pattern, we can simply use aggregation or composition and delegation. A single adapter method might delegate to methods in various instances, so we're still using the previous API, but hiding its details so our clients can use it in a consistent way.

### (b)

i.It's a bad idea for us to use freda's code because we don't all understand freda's code correctly. The complexity of the code can lead to errors when using it, and it's always more difficult to troubleshoot someone else's code. By the way, continuing to use guru's code without understanding it won't improve your coding skills, and you may not be able to use it again the next time a similar request comes up.


ii.The Facade mode will be very suitable to solve this problem. Its main role is to hide complexity by decoupling complex systems, where one subsystem can provide multiple facades. By using the facade pattern, people can only see the interfaces they need, which reduces errors when implementing more code using the system.

### (c)

i.Although canvas has a wide range of applicability, its performance is easily affected. For example, when we use images in the interface, the problem of incomplete display lights occurs. Another issue is user experience. Canvas may present the same page to every user, which means that the experience for different end users may be very different.


ii.Bridge mode can be used to support encoding Windows systems on different platforms. Bridging work between implementations and code, using multiple implementations of some system without changing the code. For each platform, it delegates to different interface implementations like JavaFX and Swing from the same code.

## 





### 

