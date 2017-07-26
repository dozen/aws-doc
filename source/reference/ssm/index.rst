[ :ref:`aws <cli:aws>` ]

.. _cli:aws ssm:


***
ssm
***



===========
Description
===========

 

Amazon EC2 Systems Manager is a collection of capabilities that helps you automate management tasks such as collecting system inventory, applying operating system (OS) patches, automating the creation of Amazon Machine Images (AMIs), and configuring operating systems (OSs) and applications at scale. Systems Manager lets you remotely and securely manage the configuration of your managed instances. A *managed instance* is any Amazon EC2 instance or on-premises machine in your hybrid environment that has been configured for Systems Manager.

 

This reference is intended to be used with the `Amazon EC2 Systems Manager User Guide <http://docs.aws.amazon.com/systems-manager/latest/userguide/>`_ .

 

To get started, verify prerequisites and configure managed instances. For more information, see `Systems Manager Prerequisites <http://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-setting-up.html>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags-to-resource
  cancel-command
  create-activation
  create-association
  create-association-batch
  create-document
  create-maintenance-window
  create-patch-baseline
  create-resource-data-sync
  delete-activation
  delete-association
  delete-document
  delete-maintenance-window
  delete-parameter
  delete-parameters
  delete-patch-baseline
  delete-resource-data-sync
  deregister-managed-instance
  deregister-patch-baseline-for-patch-group
  deregister-target-from-maintenance-window
  deregister-task-from-maintenance-window
  describe-activations
  describe-association
  describe-automation-executions
  describe-available-patches
  describe-document
  describe-document-permission
  describe-effective-instance-associations
  describe-effective-patches-for-patch-baseline
  describe-instance-associations-status
  describe-instance-information
  describe-instance-patch-states
  describe-instance-patch-states-for-patch-group
  describe-instance-patches
  describe-maintenance-window-execution-task-invocations
  describe-maintenance-window-execution-tasks
  describe-maintenance-window-executions
  describe-maintenance-window-targets
  describe-maintenance-window-tasks
  describe-maintenance-windows
  describe-parameters
  describe-patch-baselines
  describe-patch-group-state
  describe-patch-groups
  get-automation-execution
  get-command-invocation
  get-default-patch-baseline
  get-deployable-patch-snapshot-for-instance
  get-document
  get-inventory
  get-inventory-schema
  get-maintenance-window
  get-maintenance-window-execution
  get-maintenance-window-execution-task
  get-parameter
  get-parameter-history
  get-parameters
  get-parameters-by-path
  get-patch-baseline
  get-patch-baseline-for-patch-group
  list-associations
  list-command-invocations
  list-commands
  list-document-versions
  list-documents
  list-inventory-entries
  list-resource-data-sync
  list-tags-for-resource
  modify-document-permission
  put-inventory
  put-parameter
  register-default-patch-baseline
  register-patch-baseline-for-patch-group
  register-target-with-maintenance-window
  register-task-with-maintenance-window
  remove-tags-from-resource
  send-command
  start-automation-execution
  stop-automation-execution
  update-association
  update-association-status
  update-document
  update-document-default-version
  update-maintenance-window
  update-managed-instance-role
  update-patch-baseline
