[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains delete-tags-for-domain:


**********************
delete-tags-for-domain
**********************



===========
Description
===========



This operation deletes the specified tags for a domain.

 

All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.



========
Synopsis
========

::

    delete-tags-for-domain
  --domain-name <value>
  --tags-to-delete <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to delete one or more tags.

   

  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Hyphens are allowed only when theyaposre surrounded by letters, numbers, or other hyphens. You canapost specify a hyphen at the beginning or end of a label. To specify an Internationalized Domain Name, you must convert the name to Punycode.

   

  Required: Yes

  

``--tags-to-delete`` (list)


  A list of tag keys to delete.

   

  Type: A list that contains the keys of the tags that you want to delete.

   

  Default: None

   

  Required: No

  '



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

