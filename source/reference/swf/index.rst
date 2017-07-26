[ :ref:`aws <cli:aws>` ]

.. _cli:aws swf:


***
swf
***



===========
Description
===========

 

The Amazon Simple Workflow Service (Amazon SWF) makes it easy to build applications that use Amazon's cloud to coordinate work across distributed components. In Amazon SWF, a *task* represents a logical unit of work that is performed by a component of your workflow. Coordinating tasks in a workflow involves managing intertask dependencies, scheduling, and concurrency in accordance with the logical flow of the application.

 

Amazon SWF gives you full control over implementing tasks and coordinating them without worrying about underlying complexities such as tracking their progress and maintaining their state.

 

This documentation serves as reference only. For a broader overview of the Amazon SWF programming model, see the `Amazon SWF Developer Guide`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  count-closed-workflow-executions
  count-open-workflow-executions
  count-pending-activity-tasks
  count-pending-decision-tasks
  deprecate-activity-type
  deprecate-domain
  deprecate-workflow-type
  describe-activity-type
  describe-domain
  describe-workflow-execution
  describe-workflow-type
  get-workflow-execution-history
  list-activity-types
  list-closed-workflow-executions
  list-domains
  list-open-workflow-executions
  list-workflow-types
  poll-for-activity-task
  poll-for-decision-task
  record-activity-task-heartbeat
  register-activity-type
  register-domain
  register-workflow-type
  request-cancel-workflow-execution
  respond-activity-task-canceled
  respond-activity-task-completed
  respond-activity-task-failed
  respond-decision-task-completed
  signal-workflow-execution
  start-workflow-execution
  terminate-workflow-execution


.. _Amazon SWF Developer Guide: http://docs.aws.amazon.com/amazonswf/latest/developerguide/
