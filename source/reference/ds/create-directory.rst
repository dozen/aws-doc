[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-directory:


****************
create-directory
****************



===========
Description
===========



Creates a Simple AD directory.



========
Synopsis
========

::

    create-directory
  --name <value>
  [--short-name <value>]
  --password <value>
  [--description <value>]
  --size <value>
  [--vpc-settings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The fully qualified name for the directory, such as ``corp.example.com`` .

  

``--short-name`` (string)


  The short name of the directory, such as ``CORP`` .

  

``--password`` (string)


  The password for the directory administrator. The directory creation process creates a directory administrator account with the username ``Administrator`` and this password.

  

``--description`` (string)


  A textual description for the directory.

  

``--size`` (string)


  The size of the directory.

  

  Possible values:

  
  *   ``Small``

  
  *   ``Large``

  

  

``--vpc-settings`` (structure)


  A  vpc-settings object that contains additional information for the operation.

  



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

  

  

