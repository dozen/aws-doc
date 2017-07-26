[ :ref:`aws <cli:aws>` ]

.. _cli:aws stepfunctions:


*************
stepfunctions
*************



===========
Description
===========

 

AWS Step Functions is a web service that enables you to coordinate the components of distributed applications and microservices using visual workflows. You build applications from individual components that each perform a discrete function, or *task* , allowing you to scale and change applications quickly. Step Functions provides a graphical console to visualize the components of your application as a series of steps. It automatically triggers and tracks each step, and retries when there are errors, so your application executes in order and as expected, every time. Step Functions logs the state of each step, so when things do go wrong, you can diagnose and debug problems quickly.

 

Step Functions manages the operations and underlying infrastructure for you to ensure your application is available at any scale. You can run tasks on the AWS cloud, on your own servers, or an any system that has access to AWS. Step Functions can be accessed and used with the Step Functions console, the AWS SDKs (included with your Beta release invitation email), or an HTTP API (the subject of this document).



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  create-activity
  create-state-machine
  delete-activity
  delete-state-machine
  describe-activity
  describe-execution
  describe-state-machine
  get-activity-task
  get-execution-history
  list-activities
  list-executions
  list-state-machines
  send-task-failure
  send-task-heartbeat
  send-task-success
  start-execution
  stop-execution
