[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch delete-index-field:


******************
delete-index-field
******************



===========
Description
===========



Removes an `` IndexField`` from the search domain. For more information, see `Configuring Index Fields`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    delete-index-field
  --domain-name <value>
  --index-field-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--index-field-name`` (string)


  The name of the index field your want to remove from the domain's indexing options.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IndexField -> (structure)

  

  The status of the index field being deleted.

  

  Options -> (structure)

    

    Configuration information for a field in the index, including its name, type, and options. The supported options depend on the `` IndexFieldType`` .

    

    IndexFieldName -> (string)

      

      A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

       

      Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

       

      The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

      

      

    IndexFieldType -> (string)

      

      The type of field. The valid options for a field depend on the field type. For more information about the supported field types, see `Configuring Index Fields`_ in the *Amazon CloudSearch Developer Guide* .

      

      

    IntOptions -> (structure)

      

      Options for a 64-bit signed integer field. Present if ``IndexFieldType`` specifies the field is of type ``int`` . All options are enabled by default.

      

      DefaultValue -> (long)

        A value to use for the field if the field isn't specified for a document. This can be important if you are using the field in an expression and that field is not present in every document.

        

      SourceField -> (string)

        

        The name of the source field to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      

    DoubleOptions -> (structure)

      

      Options for a double-precision 64-bit floating point field. Present if ``IndexFieldType`` specifies the field is of type ``double`` . All options are enabled by default.

      

      DefaultValue -> (double)

        

        A value to use for the field if the field isn't specified for a document. This can be important if you are using the field in an expression and that field is not present in every document.

        

        

      SourceField -> (string)

        

        The name of the source field to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      

    LiteralOptions -> (structure)

      

      Options for literal field. Present if ``IndexFieldType`` specifies the field is of type ``literal`` . All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceField -> (string)

        

        A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

         

        Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

         

        The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      

    TextOptions -> (structure)

      

      Options for text field. Present if ``IndexFieldType`` specifies the field is of type ``text`` . A ``text`` field is always searchable. All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceField -> (string)

        

        A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

         

        Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

         

        The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      HighlightEnabled -> (boolean)

        

        Whether highlights can be returned for the field.

        

        

      AnalysisScheme -> (string)

        

        The name of an analysis scheme for a ``text`` field.

        

        

      

    DateOptions -> (structure)

      

      Options for a date field. Dates and times are specified in UTC (Coordinated Universal Time) according to IETF RFC3339: yyyy-mm-ddT00:00:00Z. Present if ``IndexFieldType`` specifies the field is of type ``date`` . All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceField -> (string)

        

        A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

         

        Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

         

        The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      

    LatLonOptions -> (structure)

      

      Options for a latlon field. A latlon field contains a location stored as a latitude and longitude value pair. Present if ``IndexFieldType`` specifies the field is of type ``latlon`` . All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceField -> (string)

        

        A string that represents the name of an index field. CloudSearch supports regular index fields as well as dynamic fields. A dynamic field's name defines a pattern that begins or ends with a wildcard. Any document fields that don't map to a regular index field but do match a dynamic field's pattern are configured with the dynamic field's indexing options. 

         

        Regular field names begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore). Dynamic field names must begin or end with a wildcard (*). The wildcard can also be the only character in a dynamic field name. Multiple wildcards, and wildcards embedded within a string are not supported. 

         

        The name ``score`` is reserved and cannot be used as a field name. To reference a document's ID, you can use the name ``_id`` . 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      SortEnabled -> (boolean)

        

        Whether the field can be used to sort the search results.

        

        

      

    IntArrayOptions -> (structure)

      

      Options for a field that contains an array of 64-bit signed integers. Present if ``IndexFieldType`` specifies the field is of type ``int-array`` . All options are enabled by default.

      

      DefaultValue -> (long)

        A value to use for the field if the field isn't specified for a document.

        

      SourceFields -> (string)

        

        A list of source fields to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      

    DoubleArrayOptions -> (structure)

      

      Options for a field that contains an array of double-precision 64-bit floating point values. Present if ``IndexFieldType`` specifies the field is of type ``double-array`` . All options are enabled by default.

      

      DefaultValue -> (double)

        A value to use for the field if the field isn't specified for a document.

        

      SourceFields -> (string)

        

        A list of source fields to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      

    LiteralArrayOptions -> (structure)

      

      Options for a field that contains an array of literal strings. Present if ``IndexFieldType`` specifies the field is of type ``literal-array`` . All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceFields -> (string)

        

        A list of source fields to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      

    TextArrayOptions -> (structure)

      

      Options for a field that contains an array of text strings. Present if ``IndexFieldType`` specifies the field is of type ``text-array`` . A ``text-array`` field is always searchable. All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceFields -> (string)

        

        A list of source fields to map to the field. 

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      HighlightEnabled -> (boolean)

        

        Whether highlights can be returned for the field.

        

        

      AnalysisScheme -> (string)

        

        The name of an analysis scheme for a ``text-array`` field.

        

        

      

    DateArrayOptions -> (structure)

      

      Options for a field that contains an array of dates. Present if ``IndexFieldType`` specifies the field is of type ``date-array`` . All options are enabled by default.

      

      DefaultValue -> (string)

        A value to use for the field if the field isn't specified for a document.

        

      SourceFields -> (string)

        

        A list of source fields to map to the field. 

        

        

      FacetEnabled -> (boolean)

        

        Whether facet information can be returned for the field.

        

        

      SearchEnabled -> (boolean)

        

        Whether the contents of the field are searchable.

        

        

      ReturnEnabled -> (boolean)

        

        Whether the contents of the field can be returned in the search results.

        

        

      

    

  Status -> (structure)

    

    The status of domain configuration option.

    

    CreationDate -> (timestamp)

      

      A timestamp for when this option was created.

      

      

    UpdateDate -> (timestamp)

      

      A timestamp for when this option was last updated.

      

      

    UpdateVersion -> (integer)

      

      A unique integer that indicates when this option was last updated.

      

      

    State -> (string)

      

      The state of processing a change to an option. Possible values:

       

       
      * ``RequiresIndexDocuments`` : the option's latest value will not be deployed until  index-documents has been called and indexing is complete.
       
      * ``Processing`` : the option's latest value is in the process of being activated. 
       
      * ``Active`` : the option's latest value is completely deployed.
       
      * ``FailedToValidate`` : the option value is not compatible with the domain's data and cannot be used to index the data. You must either modify the option value or update or remove the incompatible documents.
       

      

      

    PendingDeletion -> (boolean)

      

      Indicates that the option will be deleted once processing is complete.

      

      

    

  



.. _Configuring Index Fields: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-index-fields.html
