[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm resend-validation-email:


***********************
resend-validation-email
***********************



===========
Description
===========



Resends the email that requests domain ownership validation. The domain owner or an authorized representative must approve the ACM Certificate before it can be issued. The certificate can be approved by clicking a link in the mail to navigate to the Amazon certificate approval website and then clicking **I Approve** . However, the validation email can be blocked by spam filters. Therefore, if you do not receive the original mail, you can request that the mail be resent within 72 hours of requesting the ACM Certificate. If more than 72 hours have elapsed since your original request or since your last attempt to resend validation mail, you must request a new certificate. For more information about setting up your contact email addresses, see `Configure Email for your Domain <http://docs.aws.amazon.com/acm/latest/userguide/setup-email.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/ResendValidationEmail>`_


========
Synopsis
========

::

    resend-validation-email
  --certificate-arn <value>
  --domain <value>
  --validation-domain <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  String that contains the ARN of the requested certificate. The certificate ARN is generated and returned by the  request-certificate action as soon as the request is made. By default, using this parameter causes email to be sent to all top-level domains you specified in the certificate request.

   

  The ARN must be of the form:

   

   ``arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

  

``--domain`` (string)


  The fully qualified domain name (FQDN) of the certificate that needs to be validated.

  

``--validation-domain`` (string)


  The base validation domain that will act as the suffix of the email addresses that are used to send the emails. This must be the same as the ``Domain`` value or a superdomain of the ``Domain`` value. For example, if you requested a certificate for ``site.subdomain.example.com`` and specify a **ValidationDomain** of ``subdomain.example.com`` , ACM sends email to the domain registrant, technical contact, and administrative contact in WHOIS and the following five addresses:

   

   
  * admin@subdomain.example.com 
   
  * administrator@subdomain.example.com 
   
  * hostmaster@subdomain.example.com 
   
  * postmaster@subdomain.example.com 
   
  * webmaster@subdomain.example.com 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To resend validation email for your ACM certificate request**

The following ``resend-validation-email`` command tells the Amazon certificate authority to send validation email to the appropriate addresses::

  aws acm resend-validation-email --certificate-arn arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012 --domain www.example.com --validation-domain example.com


======
Output
======

None