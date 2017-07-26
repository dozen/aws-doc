[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional delete-web-acl:


**************
delete-web-acl
**************



===========
Description
===========



Permanently deletes a  WebACL . You can't delete a ``WebACL`` if it still contains any ``Rules`` .

 

To delete a ``WebACL`` , perform the following steps:

 

 
* Update the ``WebACL`` to remove ``Rules`` , if any. For more information, see  update-web-acl . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-web-acl`` request. 
 
* Submit a ``delete-web-acl`` request. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/DeleteWebACL>`_


========
Synopsis
========

::

    delete-web-acl
  --web-acl-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  The ``WebACLId`` of the  WebACL that you want to delete. ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``delete-web-acl`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

