[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-resource-permissions:


*****************************
describe-resource-permissions
*****************************



===========
Description
===========



Describes the permissions of a specified resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeResourcePermissions>`_


========
Synopsis
========

::

    describe-resource-permissions
  [--authentication-token <value>]
  --resource-id <value>
  [--limit <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--resource-id`` (string)


  The ID of the resource.

  

``--limit`` (integer)


  The maximum number of items to return with this call.

  

``--marker`` (string)


  The marker for the next set of results. (You received this marker from a previous call)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Principals -> (list)

  

  The principals.

  

  (structure)

    

    Describes a resource.

    

    Id -> (string)

      

      The ID of the resource.

      

      

    Type -> (string)

      

      The type of resource.

      

      

    Roles -> (list)

      

      The permission information for the resource.

      

      (structure)

        

        Describes the permissions.

        

        Role -> (string)

          

          The role of the user.

          

          

        Type -> (string)

          

          The type of permissions.

          

          

        

      

    

  

Marker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

