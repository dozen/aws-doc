[ :ref:`aws <cli:aws>` ]

.. _cli:aws ssm:


***
ssm
***



===========
Description
===========



Simple Systems Manager (SSM) enables you to remotely manage the configuration of your Amazon EC2 instance. Using SSM, you can run scripts or commands using either EC2 Run Command or SSM Config. (SSM Config is currently available only for Windows instances.) 

 



 **Run Command**  

Run Command provides an on-demand experience for executing commands. You can use pre-defined Amazon SSM documents to perform the actions listed later in this section, or you can create your own documents. With these documents, you can remotely configure your instances by sending commands using the **Commands** page in the `Amazon EC2 console`_ , `AWS Tools for Windows PowerShell`_ , or the `AWS CLI`_ .

 

Run Command reports the status of the command execution for each instance targeted by a command. You can also audit the command execution to understand who executed commands, when, and what changes were made. By switching between different SSM documents, you can quickly configure your instances with different types of commands. To get started with Run Command, verify that your environment meets the prerequisites for remotely running commands on EC2 instances (`Linux`_ or `Windows`_ ). 

 



 **SSM Config**  

SSM Config is a lightweight instance configuration solution. SSM Config is currently only available for Windows instances. With SSM Config, you can specify a setup configuration for your instances. SSM Config is similar to EC2 User Data, which is another way of running one-time scripts or applying settings during instance launch. SSM Config is an extension of this capability. Using SSM documents, you can specify which actions the system should perform on your instances, including which applications to install, which AWS Directory Service directory to join, which Microsoft PowerShell modules to install, etc. If an instance is missing one or more of these configurations, the system makes those changes. By default, the system checks every five minutes to see if there is a new configuration to apply as defined in a new SSM document. If so, the system updates the instances accordingly. In this way, you can remotely maintain a consistent configuration baseline on your instances. SSM Config is available using the AWS CLI or the AWS Tools for Windows PowerShell. For more information, see `Managing Windows Instance Configuration`_ .

 

SSM Config and Run Command include the following pre-defined documents.

  Amazon Pre-defined SSM Documents       Name Description Platform      

AWS-RunShellScript

   

Run shell scripts

   

Linux

     

AWS-UpdateSSMAgent

   

Update the Amazon SSM agent

   

Linux

     

AWS-JoinDirectoryServiceDomain 

   

Join an AWS Directory 

   

Windows

     

AWS-RunPowerShellScript

   

Run PowerShell commands or scripts

   

Windows

     

AWS-UpdateEC2Config

   

Update the EC2Config service 

   

Windows

     

AWS-ConfigureWindowsUpdate

   

Configure Windows Update settings

   

Windows

     

AWS-InstallApplication

   

Install, repair, or uninstall software using an MSI package

   

Windows

     

AWS-InstallPowerShellModule

   

Install PowerShell modules 

   

Windows

     

AWS-ConfigureCloudWatch

   

Configure Amazon CloudWatch Logs to monitor applications and systems

   

Windows

      

.. warning::

   The commands or scripts specified in SSM documents run with administrative privilege on your instances because the Amazon SSM agent runs as root on Linux and the EC2Config service runs in the Local System account on Windows. If a user has permission to execute any of the pre-defined SSM documents (any document that begins with AWS-*) then that user also has administrator access to the instance. Delegate access to SSM and Run Command judiciously. This becomes extremely important if you create your own SSM documents. Amazon Web Services does not provide guidance about how to create secure SSM documents. You create SSM documents and delegate access to Run Command at your own risk. As a security best practice, we recommend that you assign access to "AWS-*" documents, especially the AWS-RunShellScript document on Linux and the AWS-RunPowerShellScript document on Windows, to trusted administrators only. You can create SSM documents for specific tasks and delegate access to non-administrators. 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  cancel-command
  create-association
  create-association-batch
  create-document
  delete-association
  delete-document
  describe-association
  describe-document
  describe-instance-information
  get-document
  list-associations
  list-command-invocations
  list-commands
  list-documents
  send-command
  update-association-status


.. _Windows: http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/remote-commands-prereq.html
.. _AWS CLI: http://docs.aws.amazon.com/cli/latest/reference/ssm/index.html
.. _Managing Windows Instance Configuration: http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-configuration-manage.html
.. _Linux: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/remote-commands-prereq.html
.. _Amazon EC2 console: http://console.aws.amazon.com/ec2/
.. _AWS Tools for Windows PowerShell: http://docs.aws.amazon.com/powershell/latest/reference/items/Amazon_Simple_Systems_Management_cmdlets.html
