[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds connect-directory:


*****************
connect-directory
*****************



===========
Description
===========



Creates an AD Connector to connect to an on-premises directory.

 

Before you call *connect-directory* , ensure that all of the required permissions have been explicitly granted through a policy. For details about what permissions are required to run the *connect-directory* operation, see `AWS Directory Service API Permissions\: Actions, Resources, and Conditions Reference <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/UsingWithDS_IAM_ResourcePermissions.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/ConnectDirectory>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryId -> (string)

  

  The identifier of the new directory.

  

  

