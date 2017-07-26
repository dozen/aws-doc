[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-schema:


*************
create-schema
*************



===========
Description
===========



Creates a new schema in a development state. A schema can exist in three phases:

 

 
* *Development:* This is a mutable phase of the schema. All new schemas are in the development phase. Once the schema is finalized, it can be published. 
 
* *Published:* Published schemas are immutable and have a version associated with them. 
 
* *Applied:* Applied schemas are mutable in a way that allows you to add new schema facets. You can also add new, nonrequired attributes to existing schema facets. You can apply only published schemas to directories.  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateSchema>`_


========
Synopsis
========

::

    create-schema
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name that is associated with the schema. This is unique to each account and in each region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SchemaArn -> (string)

  

  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

  

