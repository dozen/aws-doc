[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm remove-tags-from-certificate:


****************************
remove-tags-from-certificate
****************************



===========
Description
===========



Remove one or more tags from an ACM Certificate. A tag consists of a key-value pair. If you do not specify the value portion of the tag when calling this function, the tag will be removed regardless of value. If you specify a value, the tag is removed only if it is associated with the specified value.

 

To add tags to a certificate, use the  add-tags-to-certificate action. To view all of the tags that have been applied to a specific ACM Certificate, use the  list-tags-for-certificate action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/RemoveTagsFromCertificate>`_


========
Synopsis
========

::

    remove-tags-from-certificate
  --certificate-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  String that contains the ARN of the ACM Certificate with one or more tags that you want to remove. This must be of the form:

   

   ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

``--tags`` (list)


  The key-value pair that defines the tag to remove.

  



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

**To remove a tag from an ACM Certificate**

The following ``remove-tags-from-certificate`` command removes two tags from the specified certificate. Use a space to separate multiple tags::

  aws acm remove-tags-from-certificate --certificate-arn arn:aws:acm:us-east-1:1234567890122:certificate/12345678-1234-1234-1234-123456789012 --tags Key=Admin,Value=Alice Key=Purpose,Value=Website




======
Output
======

None