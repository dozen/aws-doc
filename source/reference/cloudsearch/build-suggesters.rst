[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch build-suggesters:


****************
build-suggesters
****************



===========
Description
===========



Indexes the search suggestions. For more information, see `Configuring Suggesters`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    build-suggesters
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FieldNames -> (list)

  

  A list of field names.

  

  (string)

    

    A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

     

    Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

     

    The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

    

    

  



.. _Configuring Suggesters: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/getting-suggestions.html#configuring-suggesters
