# Customer Redis Example

This repo is used for the customer engineer exercise.
Instructions can be found at https://gist.github.com/jmacelroy/583831a3643eaac769f0d4cda2fd837d.

The prompt for the exercise can be found [here](PROMPT.md)

You can answer the questions from the prompt and complete the demo by creating a fork where you'll make your modifications before sharing.

## Prompt

The exercise consists of the following parts.

### How would you initially respond to the customer?

Hi Alice,

Thank you for contacting Okteto Technical Support.  I am sorry to learn about your issue.

To help us understand what is happening, please provide us with the following information:

-log files when running okteto up
-the okteto.yml manifest file
-the docker-compose.yml file

Once I receive the above information, I will review the files and provide an update.

Thank you for your help.

Best regards,
Eric

### What would your next steps be after reading their email and responding?


My initial steps after responding to the email are as follows:
1-Fork the repository provided by the customer

2-create the required files
-create a docker-compose.yml to run redis
-create a okteto.yml manifest

3-run okteto up with the okteto cli or using the ui
4-check for any error messages
5-connect to the kubernetes cluster using the Kubernetes Credentials feature under the "Setting" tab 
6-kubectl get pods -n makikorp 
-to see the redis pod
7-kubectl logs -n makikorp <pod name> 
-do this to double check that the microservice is running properly with no errors
8-kubectl exec -it -n makikorp <pod name> -- bash  
-do this to make sure that the microservice is accessible


### Summarize what work was needed for completing the demo for the customer.

Hi Alice,

I reviewed the repository "https://github.com/okteto/customer-redis-example".

I did the following:
1-I created the okteto.yml manifest and the docker-compose.yml.  
-Okteto manifest documentation can be found here:
  https://www.okteto.com/docs/reference/manifest/
-Using docker-compose documentation can be found here:
  https://www.okteto.com/docs/reference/compose/

2-I forked your repo to my github.

3-I ran at the command line prompt "okteto up".  The output should be similar to the following:

okteto up
 i  Using makikorp @ okteto.assessment.jdm.okteto.net as context
 i  Images were already built. To rebuild your images run 'okteto build' or 'okteto deploy --build'
 ✓  Kubernetes service 'redis' created
 ✓  Volume 'redis-data' created
 ✓  Service 'redis' created
 ✓  Compose 'customer-redis-example' successfully deployed
There are no available endpoints for 'customer-redis-example'
 i  Images were already built. To rebuild your images run 'okteto build' or 'okteto deploy --build'
 ✓  Persistent volume successfully attached
 ✓  Persistent volume successfully attached
 ✓  Images successfully pulled
 ✓  Files synchronized
    Context:   okteto.assessment.jdm.okteto.net
    Namespace: makikorp
    Name:      redis


4-I did the following to ensure that it worked:
  a-check for any error messages
  b-connect to the kubernetes cluster using the Kubernetes Credentials feature under the "Setting" tab 
  c-kubectl get pods -n makikorp 
  -to see the redis pod
  d-kubectl logs -n makikorp <pod name> 
  -do this to double check that the microservice is running properly with no errors
  e-kubectl exec -it -n makikorp <pod name> -- bash  
  -do this to make sure that the microservice is accessible

Please let me know if you have any questions.

Best regards,
Eric

### What improvments can Okteto make to better support this, or similar, customers in the future.

I would add full okteto.yml manifest file to document the build, deploy, and dev sections configurations more clearly.  There is good reference to each configuation. However, in my opinion, it is nice to see in an actual manifest file with each section and its configurations, even if optional configurations are commented out.
