[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds list-ip-routes:


**************
list-ip-routes
**************



===========
Description
===========



Lists the address blocks that you have added to a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/ListIpRoutes>`_


========
Synopsis
========

::

    list-ip-routes
  --directory-id <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  Identifier (ID) of the directory for which you want to retrieve the IP addresses.

  

``--next-token`` (string)


  The *ListIpRoutes.NextToken* value from a previous call to  list-ip-routes . Pass null if this is the first call.

  

``--limit`` (integer)


  Maximum number of items to return. If this value is zero, the maximum number of items is specified by the limitations of the operation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IpRoutesInfo -> (list)

  

  A list of  IpRoute s.

  

  (structure)

    

    Information about one or more IP address blocks.

    

    DirectoryId -> (string)

      

      Identifier (ID) of the directory associated with the IP addresses.

      

      

    CidrIp -> (string)

      

      IP address block in the  IpRoute .

      

      

    IpRouteStatusMsg -> (string)

      

      The status of the IP address block.

      

      

    AddedDateTime -> (timestamp)

      

      The date and time the address block was added to the directory.

      

      

    IpRouteStatusReason -> (string)

      

      The reason for the IpRouteStatusMsg.

      

      

    Description -> (string)

      

      Description of the  IpRouteInfo .

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the *next-token* parameter in a subsequent call to  list-ip-routes to retrieve the next set of items.

  

  

