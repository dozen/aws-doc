[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds connect-directory:


*****************
connect-directory
*****************



===========
Description
===========



Creates an AD Connector to connect to an on-premises directory.



========
Synopsis
========

::

    connect-directory
  --name <value>
  [--short-name <value>]
  --password <value>
  [--description <value>]
  --size <value>
  --connect-settings <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The fully-qualified name of the on-premises directory, such as ``corp.example.com`` .

  

``--short-name`` (string)


  The NetBIOS name of the on-premises directory, such as ``CORP`` .

  

``--password`` (string)


  The password for the on-premises user account.

  

``--description`` (string)


  A textual description for the directory.

  

``--size`` (string)


  The size of the directory.

  

  Possible values:

  
  *   ``Small``

  
  *   ``Large``

  

  

``--connect-settings`` (structure)


  A  connect-settings object that contains additional information for the operation.

  



Shorthand Syntax::

    VpcId=string,SubnetIds=string,string,CustomerDnsIps=string,string,CustomerUserName=string




JSON Syntax::

  {
    "VpcId": "string",
    "SubnetIds": ["string", ...],
    "CustomerDnsIps": ["string", ...],
    "CustomerUserName": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DirectoryId -> (string)

  

  The identifier of the new directory.

  

  

