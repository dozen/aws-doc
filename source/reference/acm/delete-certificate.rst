[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm delete-certificate:


******************
delete-certificate
******************



===========
Description
===========



Deletes an ACM Certificate and its associated private key. If this action succeeds, the certificate no longer appears in the list of ACM Certificates that can be displayed by calling the  list-certificates action or be retrieved by calling the  get-certificate action. The certificate will not be available for use by other AWS services.

 

.. note::

   

  You cannot delete an ACM Certificate that is being used by another AWS service. To delete a certificate that is in use, the certificate association must first be removed.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/DeleteCertificate>`_


========
Synopsis
========

::

    delete-certificate
  --certificate-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  String that contains the ARN of the ACM Certificate to be deleted. This must be of the form:

   

   ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an ACM certificate from your account**

The following ``delete-certificate`` command deletes the certificate with the specified ARN::

  aws acm delete-certificate --certificate-arn arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012

======
Output
======

None