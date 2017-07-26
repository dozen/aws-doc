[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm request-certificate:


*******************
request-certificate
*******************



===========
Description
===========



Requests an ACM Certificate for use with other AWS services. To request an ACM Certificate, you must specify the fully qualified domain name (FQDN) for your site. You can also specify additional FQDNs if users can reach your site by using other names. For each domain name you specify, email is sent to the domain owner to request approval to issue the certificate. After receiving approval from the domain owner, the ACM Certificate is issued. For more information, see the `AWS Certificate Manager User Guide <http://docs.aws.amazon.com/acm/latest/userguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/RequestCertificate>`_


========
Synopsis
========

::

    request-certificate
  --domain-name <value>
  [--subject-alternative-names <value>]
  [--idempotency-token <value>]
  [--domain-validation-options <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  Fully qualified domain name (FQDN), such as www.example.com, of the site that you want to secure with an ACM Certificate. Use an asterisk (*) to create a wildcard certificate that protects several sites in the same domain. For example, *.example.com protects www.example.com, site.example.com, and images.example.com. 

   

  The maximum length of a DNS name is 253 octets. The name is made up of multiple labels separated by periods. No label can be longer than 63 octets. Consider the following examples: 

   

   ``(63 octets).(63 octets).(63 octets).(61 octets)`` is legal because the total length is 253 octets (63+1+63+1+63+1+61) and no label exceeds 63 octets. 

   

   ``(64 octets).(63 octets).(63 octets).(61 octets)`` is not legal because the total length exceeds 253 octets (64+1+63+1+63+1+61) and the first label exceeds 63 octets. 

   

   ``(63 octets).(63 octets).(63 octets).(62 octets)`` is not legal because the total length of the DNS name (63+1+63+1+63+1+62) exceeds 253 octets. 

  

``--subject-alternative-names`` (list)


  Additional FQDNs to be included in the Subject Alternative Name extension of the ACM Certificate. For example, add the name www.example.net to a certificate for which the ``DomainName`` field is www.example.com if users can reach your site by using either name. The maximum number of domain names that you can add to an ACM Certificate is 100. However, the initial limit is 10 domain names. If you need more than 10 names, you must request a limit increase. For more information, see `Limits <http://docs.aws.amazon.com/acm/latest/userguide/acm-limits.html>`_ .

  



Syntax::

  "string" "string" ...



``--idempotency-token`` (string)


  Customer chosen string that can be used to distinguish between calls to ``request-certificate`` . Idempotency tokens time out after one hour. Therefore, if you call ``request-certificate`` multiple times with the same idempotency token within one hour, ACM recognizes that you are requesting only one certificate and will issue only one. If you change the idempotency token for each call, ACM recognizes that you are requesting multiple certificates.

  

``--domain-validation-options`` (list)


  The domain name that you want ACM to use to send you emails to validate your ownership of the domain.

  



Shorthand Syntax::

    DomainName=string,ValidationDomain=string ...




JSON Syntax::

  [
    {
      "DomainName": "string",
      "ValidationDomain": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To request a new ACM certificate**

The following ``request-certificate`` command requests a new certificate for the www.example.com domain::

  aws acm request-certificate --domain-name www.example.com

You can enter an idempotency token to distinguish between calls to ``request-certificate``::

  aws acm request-certificate --domain-name www.example.com --idempotency-token 91adc45q

You can enter an alternative name that can be used to reach your website::

  aws acm request-certificate --domain-name www.example.com --idempotency-token 91adc45q --subject-alternative-names www.example.net

You can also enter multiple alternative names::

  aws acm request-certificate --domain-name a.example.com --subject-alternative-names b.example.com c.example.com d.example.com *.e.example.com *.f.example.com

You can also enter domain validation options to specify the domain to which validation email will be sent::

  aws acm request-certificate --domain-name example.com --subject-alternative-names www.example.com --domain-validation-options DomainName=www.example.com,ValidationDomain=example.com


======
Output
======

CertificateArn -> (string)

  

  String that contains the ARN of the issued certificate. This must be of the form:

   

   ``arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

  

  

