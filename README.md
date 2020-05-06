# DEVOPS1


JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

SOLUTION:Created a job named test_storage and test_env for this ,the developer when commits it pushes to github
           automatically using git post-commit hook and github webhook triggered job test_storage where the code is copied
           and after successfull copy the next job which is chained it with gets initiated and the docker is launched with
           the configurations  same as that of production environment and when Qat team certified it is merged using remote trigger 
           through jenkins

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

SOLUTION:Created a job named prod_storage and prod_env for this ,the developer when commits it pushes to github
           automatically using git post-commit hook and github webhook triggered job test_storage where the code is copied
           and after successfull copy the next job which is chained it with gets initiated and the docker is launched with
           the configurations as done and is again trigerred when qat team certified the test branch code.

JOB#3
Jenkins will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

SOLUTION: all configurations are done at the JEnkins with job named QAT_MERGE and it is triggered by remote trigger and it also                    initiates the JOb2 and merge the contents by first building the test branch code files and then merge it to the origin/master             branch and  chnage sseen inn production environment.


I also used the concept of PORT ADDRESS TRANSLATION FOR PRODUCTION ENVIRONMENT and THE CONCEPT OF TUNNELING ALSO used do that everyone can access my dite and alo github can trigerr the job of jenkin. As public ip can't connect directly to private ip we have to make it public so i used tunneling process


URL OF PROJECT REPO:
     https://github.com/raghav1674/homework.git 



[SITE URL]:
        http://2cb84be3.ngrok.io/




