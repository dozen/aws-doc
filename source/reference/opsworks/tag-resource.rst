[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks tag-resource:


************
tag-resource
************



===========
Description
===========



Apply cost-allocation tags to a specified stack or layer in AWS OpsWorks Stacks. For more information about how tagging works, see `tags <http://docs.aws.amazon.com/opsworks/latest/userguide/tagging.html>`_ in the AWS OpsWorks User Guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/TagResource>`_


========
Synopsis
========

::

    tag-resource
  --resource-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The stack or layer's Amazon Resource Number (ARN).

  

``--tags`` (map)


  A map that contains tag keys and tag values that are attached to a stack or layer.

   

   
  * The key cannot be empty. 
   
  * The key can be a maximum of 127 characters, and can contain only Unicode letters, numbers, or separators, or the following special characters: ``+ - = . _ : /``   
   
  * The value can be a maximum 255 characters, and contain only Unicode letters, numbers, or separators, or the following special characters: ``+ - = . _ : /``   
   
  * Leading and trailing white spaces are trimmed from both the key and value. 
   
  * A maximum of 40 tags is allowed for any resource. 
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None