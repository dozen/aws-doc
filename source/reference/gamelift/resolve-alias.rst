[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift resolve-alias:


*************
resolve-alias
*************



===========
Description
===========



Retrieves the fleet ID that a specified alias is currently pointing to.

 

Alias-related operations include:

 

 
*  create-alias   
 
*  list-aliases   
 
*  describe-alias   
 
*  update-alias   
 
*  delete-alias   
 
*  resolve-alias   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/ResolveAlias>`_


========
Synopsis
========

::

    resolve-alias
  --alias-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alias-id`` (string)


  Unique identifier for the alias you want to resolve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetId -> (string)

  

  Fleet identifier that is associated with the requested alias.

  

  

