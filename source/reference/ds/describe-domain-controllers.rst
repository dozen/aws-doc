[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-domain-controllers:


***************************
describe-domain-controllers
***************************



===========
Description
===========



Provides information about any domain controllers in your directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeDomainControllers>`_


========
Synopsis
========

::

    describe-domain-controllers
  --directory-id <value>
  [--domain-controller-ids <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  Identifier of the directory for which to retrieve the domain controller information.

  

``--domain-controller-ids`` (list)


  A list of identifiers for the domain controllers whose information will be provided.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The *DescribeDomainControllers.NextToken* value from a previous call to  describe-domain-controllers . Pass null if this is the first call. 

  

``--limit`` (integer)


  The maximum number of items to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainControllers -> (list)

  

  List of the  DomainController objects that were retrieved.

  

  (structure)

    

    Contains information about the domain controllers for a specified directory.

    

    DirectoryId -> (string)

      

      Identifier of the directory where the domain controller resides.

      

      

    DomainControllerId -> (string)

      

      Identifies a specific domain controller in the directory.

      

      

    DnsIpAddr -> (string)

      

      The IP address of the domain controller.

      

      

    VpcId -> (string)

      

      The identifier of the VPC that contains the domain controller.

      

      

    SubnetId -> (string)

      

      Identifier of the subnet in the VPC that contains the domain controller.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone where the domain controller is located.

      

      

    Status -> (string)

      

      The status of the domain controller.

      

      

    StatusReason -> (string)

      

      A description of the domain controller state.

      

      

    LaunchTime -> (timestamp)

      

      Specifies when the domain controller was created.

      

      

    StatusLastUpdatedDateTime -> (timestamp)

      

      The date and time that the status was last updated.

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``next-token`` parameter in a subsequent call to  describe-domain-controllers retrieve the next set of items.

  

  

