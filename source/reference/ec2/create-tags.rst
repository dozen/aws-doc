[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-tags:


***********
create-tags
***********



===========
Description
===========



Adds or overwrites one or more tags for the specified Amazon EC2 resource or resources. Each resource can have a maximum of 50 tags. Each tag consists of a key and optional value. Tag keys must be unique per resource.

 

For more information about tags, see `Tagging Your Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . For more information about creating IAM policies that control users' access to resources based on tags, see `Supported Resource-Level Permissions for Amazon EC2 API Actions <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-iam-actions-resources.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateTags>`_


========
Synopsis
========

::

    create-tags
  [--dry-run | --no-dry-run]
  --resources <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--resources`` (list)


  The IDs of one or more resources to tag. For example, ami-1a2b3c4d.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  One or more tags. The ``value`` parameter is required, but if you don't want the tag to have a value, specify the parameter with no value, and we set the value to an empty string. 

  



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

**To add a tag to a resource**

This example adds the tag ``Stack=production`` to the specified image, or overwrites an existing tag for the AMI where the tag key is ``Stack``. If the command succeeds, no output is returned.

Command::

  aws ec2 create-tags --resources ami-78a54011 --tags Key=Stack,Value=production

**To add tags to multiple resources**

This example adds (or overwrites) two tags for an AMI and an instance. One of the tags contains just a key (``webserver``), with no value (we set the value to an empty string). The other tag consists of a key (``stack``) and value (``Production``). If the command succeeds, no output is returned.

Command::

  aws ec2 create-tags --resources ami-1a2b3c4d i-1234567890abcdef0 --tags Key=webserver,Value=   Key=stack,Value=Production

**To add tags with special characters**

This example adds the tag ``[Group]=test`` for an instance. The square brackets ([ and ]) are special characters, and must be escaped. If you are using Windows, surround the value with (\"):

Command::

  aws ec2 create-tags --resources i-1234567890abcdef0 --tags Key=\"[Group]\",Value=test

If you are using Windows PowerShell, break out the characters with a backslash (\\), surround them with double quotes ("), and then surround the entire key and value structure with single quotes ('):

Command::

  aws ec2 create-tags --resources i-1234567890abcdef0 --tags 'Key=\"[Group]\",Value=test'

If you are using Linux or OS X, enclose the entire key and value structure with single quotes ('), and then enclose the element with the special character with double quotes ("):

Command::

  aws ec2 create-tags --resources i-1234567890abcdef0 --tags 'Key="[Group]",Value=test'



======
Output
======

None