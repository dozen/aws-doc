[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-microsoft-ad:


*******************
create-microsoft-ad
*******************



===========
Description
===========



Creates a Microsoft AD in the AWS cloud.

 

Before you call *create-microsoft-ad* , ensure that all of the required permissions have been explicitly granted through a policy. For details about what permissions are required to run the *create-microsoft-ad* operation, see `AWS Directory Service API Permissions\: Actions, Resources, and Conditions Reference <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/UsingWithDS_IAM_ResourcePermissions.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/CreateMicrosoftAD>`_


========
Synopsis
========

::

    create-microsoft-ad
  --name <value>
  [--short-name <value>]
  --password <value>
  [--description <value>]
  --vpc-settings <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The fully qualified domain name for the directory, such as ``corp.example.com`` . This name will resolve inside your VPC only. It does not need to be publicly resolvable.

  

``--short-name`` (string)


  The NetBIOS name for your domain. A short identifier for your domain, such as ``CORP`` . If you don't specify a NetBIOS name, it will default to the first part of your directory DNS. For example, ``CORP`` for the directory DNS ``corp.example.com`` . 

  

``--password`` (string)


  The password for the default administrative user named ``Admin`` .

  

``--description`` (string)


  A textual description for the directory. This label will appear on the AWS console ``Directory Details`` page after the directory is created.

  

``--vpc-settings`` (structure)


  Contains VPC information for the  create-directory or  create-microsoft-ad operation.

  



Shorthand Syntax::

    VpcId=string,SubnetIds=string,string




JSON Syntax::

  {
    "VpcId": "string",
    "SubnetIds": ["string", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryId -> (string)

  

  The identifier of the directory that was created.

  

  

