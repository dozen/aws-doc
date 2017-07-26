[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-domain-name:


******************
update-domain-name
******************



===========
Description
===========



Changes information about the  DomainName resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateDomainName>`_


========
Synopsis
========

::

    update-domain-name
  --domain-name <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the  DomainName resource to be changed.

  

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
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

**To change the certificate name for a custom domain name**

Command::

  aws apigateway update-domain-name --domain-name api.domain.tld --patch-operations op='replace',path='/certificateName',value='newDomainCertName'

Output::

  {
      "domainName": "api.domain.tld", 
      "distributionDomainName": "d123456789012.cloudfront.net", 
      "certificateName": "newDomainCertName", 
      "certificateUploadDate": 1462565487
  }



======
Output
======

domainName -> (string)

  

  The name of the  DomainName resource.

  

  

certificateName -> (string)

  

  The name of the certificate.

  

  

certificateArn -> (string)

  

  The reference to an AWS-managed certificate. AWS Certificate Manager is the only supported source.

  

  

certificateUploadDate -> (timestamp)

  

  The timestamp when the certificate was uploaded.

  

  

distributionDomainName -> (string)

  

  The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation <http://aws.amazon.com/documentation/cloudfront/>`_ .

  

  

