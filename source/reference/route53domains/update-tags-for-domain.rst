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



========
Synopsis
========

::

    update-tags-for-domain
  --domain-name <value>
  [--tags-to-update <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to add or update tags.

   

  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Hyphens are allowed only when theyaposre surrounded by letters, numbers, or other hyphens. You canapost specify a hyphen at the beginning or end of a label. To specify an Internationalized Domain Name, you must convert the name to Punycode.

   

  Required: Yes

  

``--tags-to-update`` (list)


  A list of the tag keys and values that you want to add or update. If you specify a key that already exists, the corresponding value will be replaced.

   

  Type: A complex type containing a list of tags

   

  Default: None

   

  Required: No

  ' 

  Each tag includes the following elements:

   

   
  * Key The key (name) of a tag. Type: String Default: None Valid values: Unicode characters including alphanumeric, space, and ".:/=+\-@" Constraints: Each key can be 1-128 characters long. Required: Yes 
   
  * Value The value of a tag. Type: String Default: None Valid values: Unicode characters including alphanumeric, space, and ".:/=+\-@" Constraints: Each value can be 0-256 characters long. Required: Yes 
   

  



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

