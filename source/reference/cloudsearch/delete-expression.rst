[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch delete-expression:


*****************
delete-expression
*****************



===========
Description
===========



Removes an `` Expression`` from the search domain. For more information, see `Configuring Expressions <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-expressions.html>`_ in the *Amazon CloudSearch Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/DeleteExpression>`_


========
Synopsis
========

::

    delete-expression
  --domain-name <value>
  --expression-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--expression-name`` (string)


  The name of the `` Expression`` to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Expression -> (structure)

  

  The status of the expression being deleted.

  

  Options -> (structure)

    

    The expression that is evaluated for sorting while processing a search request.

    

    ExpressionName -> (string)

      

      Names must begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore).

      

      

    ExpressionValue -> (string)

      

      The expression to evaluate for sorting while processing a search request. The ``Expression`` syntax is based on JavaScript expressions. For more information, see `Configuring Expressions <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-expressions.html>`_ in the *Amazon CloudSearch Developer Guide* .

      

      

    

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

      

      

    

  

