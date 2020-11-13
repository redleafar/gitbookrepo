# Setup a pipeline for Android with Jenkins and Bitbucket

* Integrate Jenkins with Bitbucket: [https://www.youtube.com/watch?v=mTPsnR17MIM](https://www.youtube.com/watch?v=mTPsnR17MIM)
  * For the webhook just put the jenkins server and add /bitbucket-hook: http://jenkins-server:8080/bitbucket-hook/
  * Look here: [https://www.youtube.com/watch?v=rcRQRJ7yRag](https://www.youtube.com/watch?v=rcRQRJ7yRag)
* For pipeline configuration [https://medium.com/appgambit/build-android-application-with-jenkins-pipeline-9e2f6667bae1](https://medium.com/appgambit/build-android-application-with-jenkins-pipeline-9e2f6667bae1)
* Installing Android SDK [https://medium.com/appgambit/setup-android-sdk-on-centos-9a420b928e35](https://medium.com/appgambit/setup-android-sdk-on-centos-9a420b928e35)
  * If having problems with the sdkmanager follow:

    [https://stackoverflow.com/questions/60440509/android-command-line-tools-sdkmanager-always-shows-warning-could-not-create-se](https://stackoverflow.com/questions/60440509/android-command-line-tools-sdkmanager-always-shows-warning-could-not-create-se) \(I did: Okay, after moving the contents of `cmdline-tools` under `cmdline-tools\latest`, `sdkmanager` appears to be working. \)
* For the Jenkinsfile you can follow [https://blog.unosquare.com/how-to-setup-a-ci/cd-pipeline-for-android-using-jenkins-and-docker-part-2](https://blog.unosquare.com/how-to-setup-a-ci/cd-pipeline-for-android-using-jenkins-and-docker-part-2)
  * If having problems with Android SDK when running the job try: [https://stackoverflow.com/questions/43705311/error-with-sdk-package-download-in-android-studio](https://stackoverflow.com/questions/43705311/error-with-sdk-package-download-in-android-studio) \(I did: Delete folders which starts with dot\(**.**\), they are temporary download files\)
  * If having problems with memory try[ https://stackoverflow.com/questions/54533710/java-program-failing-to-map-native-memory-allocation](https://github.com/docker-library/elasticsearch/issues/131) I did `sudo sysctl -w vm.max_map_count=262144`
* In case that you have a Bitbucket server [https://www.jenkins.io/blog/2020/01/08/atlassians-new-bitbucket-server-integration-for-jenkins/](https://www.jenkins.io/blog/2020/01/08/atlassians-new-bitbucket-server-integration-for-jenkins/)

Notes:

* Use the pipeline option when creating the job
* I had this weird problem when running the job. Tried downgrading the gradle plugin version in Android but it did not work. Is surely something unrelated but I tried to update Android Studio, then it froze when downloading the updates, but after pushing again it worked. 

  ```text
  AAPT2 aapt2-4.0.2-6197926-linux Daemon #1: Unexpected error during link, attempting to stop daemon
  ```

* Don't forget to create a swapfile \(aws EC2 instances don't have one by default\)

  ```text
  sudo fallocate -l 1G /swapfile
  sudo chmod 600 /swapfile
  sudo mkswap /swapfile
  sudo swapon /swapfile
  ```



