[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes the tags associated with the specified Direct Connect resources.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  --resource-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arns`` (list)


  The Amazon Resource Names (ARNs) of the Direct Connect resources.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe tags for your AWS Direct Connect resources**

The following command describes the tags for the connection ``dxcon-abcabc12``.

Command::

  aws directconnect describe-tags --resource-arns arn:aws:directconnect:us-east-1:123456789012:dxcon/dxcon-abcabc12

Output::

  {
    "resourceTags": [
        {
            "resourceArn": "arn:aws:directconnect:us-east-1:123456789012:dxcon/dxcon-abcabc12", 
            "tags": [
                {
                    "value": "VAConnection", 
                    "key": "Name"
                }
            ]
        }
    ]
  }

======
Output
======

resourceTags -> (list)

  

  Information about the tags.

  

  (structure)

    

    The tags associated with a Direct Connect resource.

    

    resourceArn -> (string)

      

      The Amazon Resource Name (ARN) of the Direct Connect resource.

      

      

    tags -> (list)

      

      The tags.

      

      (structure)

        

        Information about a tag.

        

        key -> (string)

          

          The key of the tag.

          

          

        value -> (string)

          

          The value of the tag.

          

          

        

      

    

  

