[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs create-tags:


***********
create-tags
***********



===========
Description
===========



Creates or overwrites tags associated with a file system. Each tag is a key-value pair. If a tag key specified in the request already exists on the file system, this operation overwrites its value with the value provided in the request. If you add the "Name" tag to your file system, Amazon EFS returns it in the response to the  describe-file-systems API. 

 

This operation requires permission for the ``elasticfilesystem:CreateTags`` action.



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    create-tags
  --file-system-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--file-system-id`` (string)


  String. The ID of the file system whose tags you want to modify. This operation modifies only the tags and not the file system.

  

``--tags`` (list)


  An array of ``Tag`` objects to add. Each ``Tag`` object is a key-value pair. 

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None