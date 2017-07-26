[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-trusts:


***************
describe-trusts
***************



===========
Description
===========



Obtains information about the trust relationships for this account.

 

If no input parameters are provided, such as directory-id or TrustIds, this request describes all the trust relationships belonging to the account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeTrusts>`_


========
Synopsis
========

::

    describe-trusts
  [--directory-id <value>]
  [--trust-ids <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The Directory ID of the AWS directory that is a part of the requested trust relationship.

  

``--trust-ids`` (list)


  A list of identifiers of the trust relationships for which to obtain the information. If this member is null, all trust relationships that belong to the current account are returned.

   

  An empty list results in an ``InvalidParameterException`` being thrown.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The *DescribeTrustsResult.NextToken* value from a previous call to  describe-trusts . Pass null if this is the first call.

  

``--limit`` (integer)


  The maximum number of objects to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Trusts -> (list)

  

  The list of Trust objects that were retrieved.

   

  It is possible that this list contains less than the number of items specified in the *limit* member of the request. This occurs if there are less than the requested number of items left to retrieve, or if the limitations of the operation have been exceeded.

  

  (structure)

    

    Describes a trust relationship between an Microsoft AD in the AWS cloud and an external domain.

    

    DirectoryId -> (string)

      

      The Directory ID of the AWS directory involved in the trust relationship.

      

      

    TrustId -> (string)

      

      The unique ID of the trust relationship.

      

      

    RemoteDomainName -> (string)

      

      The Fully Qualified Domain Name (FQDN) of the external domain involved in the trust relationship.

      

      

    TrustType -> (string)

      

      The trust relationship type.

      

      

    TrustDirection -> (string)

      

      The trust relationship direction.

      

      

    TrustState -> (string)

      

      The trust relationship state.

      

      

    CreatedDateTime -> (timestamp)

      

      The date and time that the trust relationship was created.

      

      

    LastUpdatedDateTime -> (timestamp)

      

      The date and time that the trust relationship was last updated.

      

      

    StateLastUpdatedDateTime -> (timestamp)

      

      The date and time that the TrustState was last updated.

      

      

    TrustStateReason -> (string)

      

      The reason for the TrustState.

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the *next-token* parameter in a subsequent call to  describe-trusts to retrieve the next set of items.

  

  

