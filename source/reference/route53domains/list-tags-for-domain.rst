[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains list-tags-for-domain:


********************
list-tags-for-domain
********************



===========
Description
===========



This operation returns all of the tags that are associated with the specified domain.

 

All tag operations are eventually consistent; subsequent operations may not immediately represent all issued operations.



========
Synopsis
========

::

    list-tags-for-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The domain for which you want to get a list of tags.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TagList -> (list)

  

  A list of the tags that are associated with the specified domain.

   

  Type: A complex type containing a list of tags

   

  Each tag includes the following elements.

   

   
  * Key The key (name) of a tag. Type: String 
   
  * Value The value of a tag. Type: String 
   

  

  (structure)

    

    Each tag includes the following elements.

    

    Key -> (string)

      

      The key (name) of a tag.

       

      Type: String

       

      Default: None

       

      Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

       

      Constraints: Each key can be 1-128 characters long.

       

      Required: Yes

      

      

    Value -> (string)

      

      The value of a tag.

       

      Type: String

       

      Default: None

       

      Valid values: A-Z, a-z, 0-9, space, ".:/=+\-@"

       

      Constraints: Each value can be 0-256 characters long.

       

      Required: Yes

      

      

    

  

