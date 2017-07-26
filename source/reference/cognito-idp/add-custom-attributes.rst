[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp add-custom-attributes:


*********************
add-custom-attributes
*********************



===========
Description
===========



Adds additional user attributes to the user pool schema.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AddCustomAttributes>`_


========
Synopsis
========

::

    add-custom-attributes
  --user-pool-id <value>
  --custom-attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to add custom attributes.

  

``--custom-attributes`` (list)


  An array of custom attributes, such as Mutable and Name.

  



Shorthand Syntax::

    Name=string,AttributeDataType=string,DeveloperOnlyAttribute=boolean,Mutable=boolean,Required=boolean,NumberAttributeConstraints={MinValue=string,MaxValue=string},StringAttributeConstraints={MinLength=string,MaxLength=string} ...




JSON Syntax::

  [
    {
      "Name": "string",
      "AttributeDataType": "String"|"Number"|"DateTime"|"Boolean",
      "DeveloperOnlyAttribute": true|false,
      "Mutable": true|false,
      "Required": true|false,
      "NumberAttributeConstraints": {
        "MinValue": "string",
        "MaxValue": "string"
      },
      "StringAttributeConstraints": {
        "MinLength": "string",
        "MaxLength": "string"
      }
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

