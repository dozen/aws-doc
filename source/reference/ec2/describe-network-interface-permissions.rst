[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-network-interface-permissions:


**************************************
describe-network-interface-permissions
**************************************



===========
Description
===========



Describes the permissions for your network interfaces. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeNetworkInterfacePermissions>`_


========
Synopsis
========

::

    describe-network-interface-permissions
  [--network-interface-permission-ids <value>]
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--network-interface-permission-ids`` (list)


  One or more network interface permission IDs.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``network-interface-permission.network-interface-permission-id`` - The ID of the permission. 
   
  * ``network-interface-permission.network-interface-id`` - The ID of the network interface. 
   
  * ``network-interface-permission.aws-account-id`` - The AWS account ID. 
   
  * ``network-interface-permission.aws-service`` - The AWS service. 
   
  * ``network-interface-permission.permission`` - The type of permission (``INSTANCE-ATTACH`` | ``EIP-ASSOCIATE`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--next-token`` (string)


  The token to request the next page of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. To retrieve the remaining results, make another call with the returned ``NextToken`` value. If this parameter is not specified, up to 50 results are returned by default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NetworkInterfacePermissions -> (list)

  

  The network interface permissions.

  

  (structure)

    

    Describes a permission for a network interface.

    

    NetworkInterfacePermissionId -> (string)

      

      The ID of the network interface permission.

      

      

    NetworkInterfaceId -> (string)

      

      The ID of the network interface.

      

      

    AwsAccountId -> (string)

      

      The AWS account ID.

      

      

    AwsService -> (string)

      

      The AWS service.

      

      

    Permission -> (string)

      

      The type of permission.

      

      

    PermissionState -> (structure)

      

      Information about the state of the permission.

      

      State -> (string)

        

        The state of the permission.

        

        

      StatusMessage -> (string)

        

        A status message, if applicable.

        

        

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results.

  

  

