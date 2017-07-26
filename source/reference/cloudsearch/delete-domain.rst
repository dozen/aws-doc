[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch delete-domain:


*************
delete-domain
*************



===========
Description
===========



Permanently deletes a search domain and all of its data. Once a domain has been deleted, it cannot be recovered. For more information, see `Deleting a Search Domain <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/deleting-domains.html>`_ in the *Amazon CloudSearch Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/DeleteDomain>`_


========
Synopsis
========

::

    delete-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain you want to permanently delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainStatus -> (structure)

  

  The current status of the search domain.

  

  DomainId -> (string)

    

    An internally generated unique identifier for a domain.

    

    

  DomainName -> (string)

    

    A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

    

    

  ARN -> (string)

    

    The Amazon Resource Name (ARN) of the search domain. See `Identifiers for IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/index.html?Using_Identifiers.html>`_ in *Using AWS Identity and Access Management* for more information.

    

    

  Created -> (boolean)

    

    True if the search domain is created. It can take several minutes to initialize a domain when  create-domain is called. Newly created search domains are returned from  describe-domains with a false value for Created until domain creation is complete.

    

    

  Deleted -> (boolean)

    

    True if the search domain has been deleted. The system must clean up resources dedicated to the search domain when  delete-domain is called. Newly deleted search domains are returned from  describe-domains with a true value for IsDeleted for several minutes until resource cleanup is complete.

    

    

  DocService -> (structure)

    

    The service endpoint for updating documents in a search domain.

    

    Endpoint -> (string)

      

      The endpoint to which service requests can be submitted. For example, ``search-imdb-movies-oopcnjfn6ugofer3zx5iadxxca.eu-west-1.cloudsearch.amazonaws.com`` or ``doc-imdb-movies-oopcnjfn6ugofer3zx5iadxxca.eu-west-1.cloudsearch.amazonaws.com`` .

      

      

    

  SearchService -> (structure)

    

    The service endpoint for requesting search results from a search domain.

    

    Endpoint -> (string)

      

      The endpoint to which service requests can be submitted. For example, ``search-imdb-movies-oopcnjfn6ugofer3zx5iadxxca.eu-west-1.cloudsearch.amazonaws.com`` or ``doc-imdb-movies-oopcnjfn6ugofer3zx5iadxxca.eu-west-1.cloudsearch.amazonaws.com`` .

      

      

    

  RequiresIndexDocuments -> (boolean)

    

    True if  index-documents needs to be called to activate the current domain configuration.

    

    

  Processing -> (boolean)

    

    True if processing is being done to activate the current domain configuration.

    

    

  SearchInstanceType -> (string)

    

    The instance type that is being used to process search requests.

    

    

  SearchPartitionCount -> (integer)

    

    The number of partitions across which the search index is spread.

    

    

  SearchInstanceCount -> (integer)

    

    The number of search instances that are available to process search requests.

    

    

  Limits -> (structure)

    

    MaximumReplicationCount -> (integer)

      

      

    MaximumPartitionCount -> (integer)

      

      

    

  

