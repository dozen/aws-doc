[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch describe-service-access-policies:


********************************
describe-service-access-policies
********************************



===========
Description
===========



Gets information about the access policies that control access to the domain's document and search endpoints. By default, shows the configuration with any pending changes. Set the ``Deployed`` option to ``true`` to show the active configuration and exclude pending changes. For more information, see `Configuring Access for a Search Domain`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    describe-service-access-policies
  --domain-name <value>
  [--deployed | --no-deployed]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain you want to describe.

  

``--deployed`` | ``--no-deployed`` (boolean)


  Whether to display the deployed configuration (``true`` ) or include any pending changes (``false`` ). Defaults to ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AccessPolicies -> (structure)

  

  The access rules configured for the domain specified in the request.

  

  Options -> (string)

    

    Access rules for a domain's document or search service endpoints. For more information, see `Configuring Access for a Search Domain`_ in the *Amazon CloudSearch Developer Guide* . The maximum size of a policy document is 100 KB.

    

    

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

      

      

    

  



.. _Configuring Access for a Search Domain: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-access.html
