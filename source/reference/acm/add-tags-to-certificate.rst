[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm add-tags-to-certificate:


***********************
add-tags-to-certificate
***********************



===========
Description
===========



Adds one or more tags to an ACM Certificate. Tags are labels that you can use to identify and organize your AWS resources. Each tag consists of a ``key`` and an optional ``value`` . You specify the certificate on input by its Amazon Resource Name (ARN). You specify the tag by using a key-value pair.

 

You can apply a tag to just one certificate if you want to identify a specific characteristic of that certificate, or you can apply the same tag to multiple certificates if you want to filter for a common relationship among those certificates. Similarly, you can apply the same tag to multiple resources if you want to specify a relationship among those resources. For example, you can add the same tag to an ACM Certificate and an Elastic Load Balancing load balancer to indicate that they are both used by the same website. For more information, see `Tagging ACM Certificates <http://docs.aws.amazon.com/acm/latest/userguide/tags.html>`_ .

 

To remove one or more tags, use the  remove-tags-from-certificate action. To view all of the tags that have been applied to the certificate, use the  list-tags-for-certificate action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/AddTagsToCertificate>`_


========
Synopsis
========

::

    add-tags-to-certificate
  --certificate-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  String that contains the ARN of the ACM Certificate to which the tag is to be applied. This must be of the form:

   

   ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

``--tags`` (list)


  The key-value pair that defines the tag. The tag value is optional.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
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

**To add tags to an existing ACM Certificate**

The following ``add-tags-to-certificate`` command adds two tags to the specified certificate. Use a space to separate multiple tags::

  aws acm add-tags-to-certificate --certificate-arn arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012 --tags Key=Admin,Value=Alice Key=Purpose,Value=Website




======
Output
======

None