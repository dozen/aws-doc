[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-cache-security-group:


***************************
delete-cache-security-group
***************************



===========
Description
===========



Deletes a cache security group.

 

.. note::

   

  You cannot delete a cache security group if it is associated with any cache clusters.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DeleteCacheSecurityGroup>`_


========
Synopsis
========

::

    delete-cache-security-group
  --cache-security-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-security-group-name`` (string)


  The name of the cache security group to delete.

   

  .. note::

     

    You cannot delete the default security group.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None