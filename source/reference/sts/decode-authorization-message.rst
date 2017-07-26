[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts decode-authorization-message:


****************************
decode-authorization-message
****************************



===========
Description
===========



Decodes additional information about the authorization status of a request from an encoded message returned in response to an AWS request.

 

For example, if a user is not authorized to perform an action that he or she has requested, the request returns a ``Client.UnauthorizedOperation`` response (an HTTP 403 response). Some AWS actions additionally return an encoded message that can provide details about this authorization failure. 

 

.. note::

   

  Only certain AWS actions return an encoded authorization message. The documentation for an individual action indicates whether that action returns an encoded message in addition to returning an HTTP code.

   

 

The message is encoded because the details of the authorization status can constitute privileged information that the user who requested the action should not see. To decode an authorization status message, a user must be granted permissions via an IAM policy to request the ``decode-authorization-message`` (``sts:DecodeAuthorizationMessage`` ) action. 

 

The decoded message includes the following type of information:

 

 
* Whether the request was denied due to an explicit deny or due to the absence of an explicit allow. For more information, see `Determining Whether a Request is Allowed or Denied <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html#policy-eval-denyallow>`_ in the *IAM User Guide* .  
 
* The principal who made the request. 
 
* The requested action. 
 
* The requested resource. 
 
* The values of condition keys in the context of the user's request. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sts-2011-06-15/DecodeAuthorizationMessage>`_


========
Synopsis
========

::

    decode-authorization-message
  --encoded-message <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--encoded-message`` (string)


  The encoded message that was returned with the response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DecodedMessage -> (string)

  

  An XML document that contains the decoded message.

  

  

