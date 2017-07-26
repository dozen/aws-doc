[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains update-tags-for-domain:


**********************
update-tags-for-domain
**********************



===========
Description
===========



This operation adds or updates tags for a specified domain.

 

All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/UpdateTagsForDomain>`_


========
Synopsis
========

::

    update-tags-for-domain
  --domain-name <value>
  [--tags-to-update <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to add or update tags.

  

``--tags-to-update`` (list)


  A list of the tag keys and values that you want to add or update. If you specify a key that already exists, the corresponding value will be replaced.

  



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

