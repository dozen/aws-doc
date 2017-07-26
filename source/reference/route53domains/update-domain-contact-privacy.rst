[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains update-domain-contact-privacy:


*****************************
update-domain-contact-privacy
*****************************



===========
Description
===========



This operation updates the specified domain contact's privacy setting. When the privacy option is enabled, personal information such as postal or email address is hidden from the results of a public WHOIS query. The privacy services are provided by the AWS registrar, Gandi. For more information, see the `Gandi privacy features <http://www.gandi.net/domain/whois/?currency=USD&amp;lang=en>`_ .

 

This operation only affects the privacy of the specified contact type (registrant, administrator, or tech). Successful acceptance returns an operation ID that you can use with  get-operation-detail to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/UpdateDomainContactPrivacy>`_


========
Synopsis
========

::

    update-domain-contact-privacy
  --domain-name <value>
  [--admin-privacy | --no-admin-privacy]
  [--registrant-privacy | --no-registrant-privacy]
  [--tech-privacy | --no-tech-privacy]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain that you want to update the privacy setting for.

  

``--admin-privacy`` | ``--no-admin-privacy`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

``--registrant-privacy`` | ``--no-registrant-privacy`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

``--tech-privacy`` | ``--no-tech-privacy`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OperationId -> (string)

  

  Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

  

  

