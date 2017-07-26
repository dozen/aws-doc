[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs create-tags:


***********
create-tags
***********



===========
Description
===========



Creates or overwrites tags associated with a file system. Each tag is a key-value pair. If a tag key specified in the request already exists on the file system, this operation overwrites its value with the value provided in the request. If you add the ``Name`` tag to your file system, Amazon EFS returns it in the response to the  describe-file-systems operation. 

 

This operation requires permission for the ``elasticfilesystem:CreateTags`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/CreateTags>`_


========
Synopsis
========

::

    create-tags
  --file-system-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-system-id`` (string)


  ID of the file system whose tags you want to modify (String). This operation modifies the tags only, not the file system.

  

``--tags`` (list)


  Array of ``Tag`` objects to add. Each ``Tag`` object is a key-value pair. 

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None