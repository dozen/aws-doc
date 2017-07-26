[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the specified set of tags from the specified set of resources. This call is designed to follow a ``describe-tags`` request.

 

For more information about tags, see `Tagging Your Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteTags>`_


========
Synopsis
========

::

    delete-tags
  [--dry-run | --no-dry-run]
  --resources <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--resources`` (list)


  The ID of the resource. For example, ami-1a2b3c4d. You can specify more than one resource ID.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  One or more tags to delete. If you omit the ``value`` parameter, we delete the tag regardless of its value. If you specify this parameter with an empty string as the value, we delete the key only if its value is an empty string.

  



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



========
Examples
========

**To delete a tag from a resource**

This example deletes the tag ``Stack=Test`` from the specified image. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-tags --resources ami-78a54011 --tags Key=Stack,Value=Test


It's optional to specify the value for any tag with a value. If you specify a value for the key, the tag is deleted only if the tag's value matches the one you specified. If you specify the empty string as the value, the tag is deleted only if the tag's value is the empty string. The following example specifies the empty string as the value for the tag to delete.

Command::

  aws ec2 delete-tags --resources i-1234567890abcdef0 --tags Key=Name,Value=
 
This example deletes the tag with the ``purpose`` key from the specified instance, regardless of the tag's value.

Command::

  aws ec2 delete-tags --resources i-1234567890abcdef0 --tags Key=purpose
  
**To delete a tag from multiple resources**
  
This example deletes the ``Purpose=Test`` tag from a specified instance and AMI. The tag's value can be omitted from the command. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-tags --resources i-1234567890abcdef0 ami-78a54011 --tags Key=Purpose


======
Output
======

None