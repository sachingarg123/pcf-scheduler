# pcf-scheduler
This repository has example of PCF scheduler app to be used in PCF env

# Prerequiste
1) Install Scheduler PCF via marketplace in PCF via UI
2) or run command cf create-service scheduler-for-pcf standard pcf-scheduler

# Deploy
1) Deploy application using command cf push. it will push application in PCF
2) bind application with app using command cf bind-service pcf-scheduler-app pcf-scheduler

# Create and Schedule Job
1) cf create-job pcf-scheduler-app my-demo ".java-buildpack/open_jdk_jre/bin/java -cp ./BOOT-INF/classes ninja.spring.pcfscheduler.Scheduler"
2) cf schedule-job my-demo "0/1 * ? * *"

# Note:

1) Install scheduler plugin to run create-call and creat-job commands via link https://network.pivotal.io/products/p-scheduler-for-pcf
2) install commnd used is : cf install-plugin scheduler-for-pcf-cliplugin-windows64-exe-1.2.1-build.4


# Reference
1) https://medium.com/@christophef/scheduler-with-cloud-foundry-2f98d3daef35
2) https://github.com/christophe-f/pcf-scheduler-demo/blob/master/README.md
3) https://dzone.com/articles/scheduling-jobs-using-pcf-scheduler

