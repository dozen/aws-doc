[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch describe-expressions:


********************
describe-expressions
********************



===========
Description
===========



Gets the expressions configured for the search domain. Can be limited to specific expressions by name. By default, shows all expressions and includes any pending changes to the configuration. Set the ``Deployed`` option to ``true`` to show the active configuration and exclude pending changes. For more information, see `Configuring Expressions`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    describe-expressions
  --domain-name <value>
  [--expression-names <value>]
  [--deployed | --no-deployed]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain you want to describe.

  

``--expression-names`` (list)


  Limits the `` describe-expressions`` response to the specified expressions. If not specified, all expressions are shown.

  



Syntax::

  "string" "string" ...



``--deployed`` | ``--no-deployed`` (boolean)


  Whether to display the deployed configuration (``true`` ) or include any pending changes (``false`` ). Defaults to ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Expressions -> (list)

  

  The expressions configured for the domain.

  

  (structure)

    

    The value of an ``Expression`` and its current status.

    

    Options -> (structure)

      

      The expression that is evaluated for sorting while processing a search request.

      

      ExpressionName -> (string)

        

        Names must begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore).

        

        

      ExpressionValue -> (string)

        

        The expression to evaluate for sorting while processing a search request. The ``Expression`` syntax is based on JavaScript expressions. For more information, see `Configuring Expressions`_ in the *Amazon CloudSearch Developer Guide* .

        

        

      

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

        

        

      

    

  



.. _Configuring Expressions: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-expressions.html
