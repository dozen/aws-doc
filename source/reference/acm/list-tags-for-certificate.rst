[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm list-tags-for-certificate:


*************************
list-tags-for-certificate
*************************



===========
Description
===========



Lists the tags that have been applied to the ACM Certificate. Use the certificate's Amazon Resource Name (ARN) to specify the certificate. To add a tag to an ACM Certificate, use the  add-tags-to-certificate action. To delete a tag, use the  remove-tags-from-certificate action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/ListTagsForCertificate>`_


========
Synopsis
========

::

    list-tags-for-certificate
  --certificate-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  String that contains the ARN of the ACM Certificate for which you want to list the tags. This has the following form:

   

   ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the tags applied to an ACM Certificate**

The following ``list-tags-for-certificate`` command lists the tags applied to a certificate in your account::

  aws acm list-tags-for-certificate --certificate-arn arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012

The preceding command produces ouput similar to the following::

  {
    "Tags": [
        {
            "Value": "Website",
            "Key": "Purpose"
        },
        {
            "Value": "Alice",
            "Key": "Admin"
        }
    ]
  }


======
Output
======

Tags -> (list)

  

  The key-value pairs that define the applied tags.

  

  (structure)

    

    A key-value pair that identifies or specifies metadata about an ACM resource.

    

    Key -> (string)

      

      The key of the tag.

      

      

    Value -> (string)

      

      The value of the tag.

      

      

    

  

