[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-microsoft-ad:


*******************
create-microsoft-ad
*******************



===========
Description
===========

Creates a Microsoft AD in the AWS cloud.

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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DirectoryId -> (string)

  The identifier of the directory that was created.

  

