# Jenkins

*Each test number corresponds to a folder number in Data. All data is saved in the appropriate folder*

***

*1. Сreate a job*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/1%20First%20job/Item%20name.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/1%20First%20job/Steps.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/1%20First%20job/Output.png)
</details>

***

*2. Display the "Second Job" text, current date and time in the console output*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/2%20Second%20job/Config.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/2%20Second%20job/Output.png)
</details>

***

*3. Successful execution of one job triggers the start of another job*

<details>
  <summary>Screens&Video</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/3%20Job%20triggers/Build%20job.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/3%20Job%20triggers/Git%20job.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/3%20Job%20triggers/Second%20job.png)
  
  [![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/intro%201.png)](https://drive.google.com/file/d/1rmcNToZZjplnCUBxZ2WQk1Pvo0WaXFbx/view?usp=share_link)
</details>

*** 

*4. Trigger new builds remotely by accessing a special predefined URL*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/Build%20%238.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/Build%20steps.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/Build%20triggers.png)
  
  `http://localhost:8080/job/Build-AutoTrigger-1/build?token=my_token` - paste the link in the address bar
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/URL.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/%238%20was%20created.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/Output%20%238.png)
  
  `$ curl http://localhost:8080/job/Build-AutoTrigger-1/build?token=my_token` - creating a new build from the command line using the link
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/CL.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/4%20Build%20AutoTrigger-1/Output.png)
</details>

***

*5. Create a new build automatically every 2 min*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/5%20Every%202%20min/Build-AutoTrigger-3.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/5%20Every%202%20min/Configuration.png)
</details>

***

*6. One job triggers another which shows the last 10 commits from my "githubrepo" repository*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/6%20Git%20Job/Git_Job_before_build.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/6%20Git%20Job/githubrepo.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/6%20Git%20Job/Build_Job.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/6%20Git%20Job/Git_job_after_build.png)
  
</details>

***

*7. Checks every 2 minutes whether a new commit has appeared on GitHub. If yes, create a new build. If not, then nothing happens*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/7%20Build-AutoTrigger-4/new%20commit.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/7%20Build-AutoTrigger-4/github.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/7%20Build-AutoTrigger-4/new%20build1.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/7%20Build-AutoTrigger-4/31.png)
</details>

***

*8. Delegate job to the "Windows_Node" Agent*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/8%20Delegated%20job/Agent%20Windows%20Node.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/8%20Delegated%20job/Build%20%232.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/8%20Delegated%20job/Output.png)
</details>

***

*9. Delegating the job to a Jenkins agents*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/9%20Agent%20scripted%20job/Pipeline.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/9%20Agent%20scripted%20job/Node.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/9%20Agent%20scripted%20job/Output.png)
  
  *Pipeline script:*
  pipeline {
    agent {
        label 'Windows_Node'
    }
    stages {
			stage('Design') {
				steps {
					echo 'Creating the World'
            }
			}
            stage('Coding') {
				steps {
					echo 'Coding the World'
            }
			}
            stage('Testing') {
				steps {
					echo 'Testing the World'
            }
			}
            stage('Release') {
				steps {
					echo 'Releasing the World'
            }
			}
            stage('Support') {
				steps {
					echo 'Supporting the World'
            }
        }
    }
}

</details>

***

*10. Create a pipeline*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/10%20Create%20a%20pipeline/1.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/10%20Create%20a%20pipeline/2.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/10%20Create%20a%20pipeline/3.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/10%20Create%20a%20pipeline/4.png)
</details>

***

*11. Сlone git repository to create a local copy on my local computer and sync between the two locations*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/11%20PipelineGitDemo_1/Build%20%231.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/11%20PipelineGitDemo_1/Pipeline%20script.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/11%20PipelineGitDemo_1/githubrepo.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/11%20PipelineGitDemo_1/Stage%20Logs.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/11%20PipelineGitDemo_1/Folder.png)
</details>

***

*12. I cloned the git repository on my local computer. Placed the "simple.bat" file script in GitHub, pull my data file from my GitHub repository to my Jenkins machine and execute it in Jenkins*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/12%20PipelineGitDemo_2/Executed.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/12%20PipelineGitDemo_2/Script.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/12%20PipelineGitDemo_2/bat%20file.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/12%20PipelineGitDemo_2/clone_repo.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/12%20PipelineGitDemo_2/Stage%20Logs.png)
</details>

***

*13. Creating Jenkinsfile, placing it on my GitHub repository and implement pipeline in jenkins. Jenkins was able to pull the script and run it*

<details>
  <summary>Screens</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/13%20Jenkinsfile/Pipeline.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/13%20Jenkinsfile/Jenkinsfile.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/13%20Jenkinsfile/Stages.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/13%20Jenkinsfile/Output.jpg)
</details>

***

*14. Jenkins CLI*

`$ java -jar jenkins-cli.jar -s http://localhost:8080/ who-am-i` - display my credential and permissions
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ create-job First_job` - create the "First_job" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ build First_job` - build the "First_job" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ create-view MyView` - create the "NewView" view
`$  java -jar jenkins-cli.jar -s http://localhost:8080/ set-build-description First_job 1 sometext` - set the "sometext" description of the first "First_job" build.
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ add-job-to-view MyView Second_Job ...` - add the "Second_Job" job to the "MyView" view.
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ copy-job First_job First_job_copy` - copy the "First_job" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ list-jobs MyView` - display all jobs in the "MyView" view
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ disable-job NAME` - disable the "First_job_copy" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ enable-job NAME` - enable the "First_job_copy" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ delete-builds First_job 1` - delete the "First_job" job first build
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ remove-job-from-view MyView First_job ...`remove the "First_job" job from the "MyView" view
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ delete-job First_job_copy ...` - delete the "First_job_copy" job
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ delete-view MyView ...` - delete the "MyView" view
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ restart` - restart Jenkins
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ safe-restart` - safe restart Jenkins
`$ java -jar jenkins-cli.jar -s http://localhost:8080/ safe-shutdown` - put Jenkins into the quiet mode, wait for existing builds to be completed, and then shut down Jenkins. 

***

*15. Integrate my GitHub Repository to my Jenkins Project. I created a new commit in the local repository and pushed it to the GitHub. Jenkins checked GitHub repo, 'found' the commit in the repository, automatically created a new build and executed the "simple.bat" file script. Every time I publish my changes to Github, GitHub will trigger my new Jenkins job*

<details>
  <summary>Screens&Video</summary>
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/15%20GitHub%20-%20WebHook/Git%20Bush.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/15%20GitHub%20-%20WebHook/file2.txt.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/15%20GitHub%20-%20WebHook/simple.bat.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/15%20GitHub%20-%20WebHook/Console%20Output%201.png)
  
  ![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/15%20GitHub%20-%20WebHook/Console%20Output%202.png)
  
  [![Jenkins](https://github.com/Meiliger/Jenkins/blob/main/Data/intro%202.png)](https://drive.google.com/file/d/19_EBb4kPmnk1ecizMAg69Zrc3A9UD-0k/view?usp=share_link)
</details>


