[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses describe-receipt-rule-set:


*************************
describe-receipt-rule-set
*************************



===========
Description
===========



Returns the details of the specified receipt rule set.

 

For information about managing receipt rule sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rule-sets.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/DescribeReceiptRuleSet>`_


========
Synopsis
========

::

    describe-receipt-rule-set
  --rule-set-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-set-name`` (string)


  The name of the receipt rule set to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Metadata -> (structure)

  

  The metadata for the receipt rule set, which consists of the rule set name and the timestamp of when the rule set was created.

  

  Name -> (string)

    

    The name of the receipt rule set. The name must:

     

     
    * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
     
    * Start and end with a letter or number. 
     
    * Contain less than 64 characters. 
     

    

    

  CreatedTimestamp -> (timestamp)

    

    The date and time the receipt rule set was created.

    

    

  

Rules -> (list)

  

  A list of the receipt rules that belong to the specified receipt rule set.

  

  (structure)

    

    Receipt rules enable you to specify which actions Amazon SES should take when it receives mail on behalf of one or more email addresses or domains that you own.

     

    Each receipt rule defines a set of email addresses or domains to which it applies. If the email addresses or domains match at least one recipient address of the message, Amazon SES executes all of the receipt rule's actions on the message.

     

    For information about setting up receipt rules, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-receipt-rules.html>`_ .

    

    Name -> (string)

      

      The name of the receipt rule. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
       
      * Start and end with a letter or number. 
       
      * Contain less than 64 characters. 
       

      

      

    Enabled -> (boolean)

      

      If ``true`` , the receipt rule is active. The default value is ``false`` .

      

      

    TlsPolicy -> (string)

      

      Specifies whether Amazon SES should require that incoming email is delivered over a connection encrypted with Transport Layer Security (TLS). If this parameter is set to ``Require`` , Amazon SES will bounce emails that are not received over TLS. The default is ``Optional`` .

      

      

    Recipients -> (list)

      

      The recipient domains and email addresses to which the receipt rule applies. If this field is not specified, this rule will match all recipients under all verified domains.

      

      (string)

        

        

      

    Actions -> (list)

      

      An ordered list of actions to perform on messages that match at least one of the recipient email addresses or domains specified in the receipt rule.

      

      (structure)

        

        An action that Amazon SES can take when it receives an email on behalf of one or more email addresses or domains that you own. An instance of this data type can represent only one action.

         

        For information about setting up receipt rules, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-receipt-rules.html>`_ .

        

        S3Action -> (structure)

          

          Saves the received message to an Amazon Simple Storage Service (Amazon S3) bucket and, optionally, publishes a notification to Amazon SNS.

          

          TopicArn -> (string)

            

            The ARN of the Amazon SNS topic to notify when the message is saved to the Amazon S3 bucket. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          BucketName -> (string)

            

            The name of the Amazon S3 bucket to which to save the received email.

            

            

          ObjectKeyPrefix -> (string)

            

            The key prefix of the Amazon S3 bucket. The key prefix is similar to a directory name that enables you to store similar data under the same directory in a bucket.

            

            

          KmsKeyArn -> (string)

            

            The customer master key that Amazon SES should use to encrypt your emails before saving them to the Amazon S3 bucket. You can use the default master key or a custom master key you created in AWS KMS as follows:

             

             
            * To use the default master key, provide an ARN in the form of ``arn:aws:kms:REGION:ACCOUNT-ID-WITHOUT-HYPHENS:alias/aws/ses`` . For example, if your AWS account ID is 123456789012 and you want to use the default master key in the US West (Oregon) region, the ARN of the default master key would be ``arn:aws:kms:us-west-2:123456789012:alias/aws/ses`` . If you use the default master key, you don't need to perform any extra steps to give Amazon SES permission to use the key. 
             
            * To use a custom master key you created in AWS KMS, provide the ARN of the master key and ensure that you add a statement to your key's policy to give Amazon SES permission to use it. For more information about giving permissions, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-permissions.html>`_ . 
             

             

            For more information about key policies, see the `AWS KMS Developer Guide <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html>`_ . If you do not specify a master key, Amazon SES will not encrypt your emails.

             

            .. warning::

               

              Your mail is encrypted by Amazon SES using the Amazon S3 encryption client before the mail is submitted to Amazon S3 for storage. It is not encrypted using Amazon S3 server-side encryption. This means that you must use the Amazon S3 encryption client to decrypt the email after retrieving it from Amazon S3, as the service has no access to use your AWS KMS keys for decryption. This encryption client is currently available with the `AWS Java SDK <http://aws.amazon.com/sdk-for-java/>`_ and `AWS Ruby SDK <http://aws.amazon.com/sdk-for-ruby/>`_ only. For more information about client-side encryption using AWS KMS master keys, see the `Amazon S3 Developer Guide <http://alpha-docs-aws.amazon.com/AmazonS3/latest/dev/UsingClientSideEncryption.html>`_ .

               

            

            

          

        BounceAction -> (structure)

          

          Rejects the received email by returning a bounce response to the sender and, optionally, publishes a notification to Amazon Simple Notification Service (Amazon SNS).

          

          TopicArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the bounce action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          SmtpReplyCode -> (string)

            

            The SMTP reply code, as defined by `RFC 5321 <https://tools.ietf.org/html/rfc5321>`_ .

            

            

          StatusCode -> (string)

            

            The SMTP enhanced status code, as defined by `RFC 3463 <https://tools.ietf.org/html/rfc3463>`_ .

            

            

          Message -> (string)

            

            Human-readable text to include in the bounce message.

            

            

          Sender -> (string)

            

            The email address of the sender of the bounced email. This is the address from which the bounce message will be sent.

            

            

          

        WorkmailAction -> (structure)

          

          Calls Amazon WorkMail and, optionally, publishes a notification to Amazon SNS.

          

          TopicArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the WorkMail action is called. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          OrganizationArn -> (string)

            

            The ARN of the Amazon WorkMail organization. An example of an Amazon WorkMail organization ARN is ``arn:aws:workmail:us-west-2:123456789012:organization/m-68755160c4cb4e29a2b2f8fb58f359d7`` . For information about Amazon WorkMail organizations, see the `Amazon WorkMail Administrator Guide <http://docs.aws.amazon.com/workmail/latest/adminguide/organizations_overview.html>`_ .

            

            

          

        LambdaAction -> (structure)

          

          Calls an AWS Lambda function, and optionally, publishes a notification to Amazon SNS.

          

          TopicArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the Lambda action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          FunctionArn -> (string)

            

            The Amazon Resource Name (ARN) of the AWS Lambda function. An example of an AWS Lambda function ARN is ``arn:aws:lambda:us-west-2:account-id:function:MyFunction`` . For more information about AWS Lambda, see the `AWS Lambda Developer Guide <http://docs.aws.amazon.com/lambda/latest/dg/welcome.html>`_ .

            

            

          InvocationType -> (string)

            

            The invocation type of the AWS Lambda function. An invocation type of ``RequestResponse`` means that the execution of the function will immediately result in a response, and a value of ``Event`` means that the function will be invoked asynchronously. The default value is ``Event`` . For information about AWS Lambda invocation types, see the `AWS Lambda Developer Guide <http://docs.aws.amazon.com/lambda/latest/dg/API_Invoke.html>`_ .

             

            .. warning::

               

              There is a 30-second timeout on ``RequestResponse`` invocations. You should use ``Event`` invocation in most cases. Use ``RequestResponse`` only when you want to make a mail flow decision, such as whether to stop the receipt rule or the receipt rule set.

               

            

            

          

        StopAction -> (structure)

          

          Terminates the evaluation of the receipt rule set and optionally publishes a notification to Amazon SNS.

          

          Scope -> (string)

            

            The scope to which the Stop action applies. That is, what is being stopped.

            

            

          TopicArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon SNS topic to notify when the stop action is taken. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          

        AddHeaderAction -> (structure)

          

          Adds a header to the received email.

          

          HeaderName -> (string)

            

            The name of the header to add. Must be between 1 and 50 characters, inclusive, and consist of alphanumeric (a-z, A-Z, 0-9) characters and dashes only.

            

            

          HeaderValue -> (string)

            

            Must be less than 2048 characters, and must not contain newline characters ("\r" or "\n").

            

            

          

        SNSAction -> (structure)

          

          Publishes the email content within a notification to Amazon SNS.

          

          TopicArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon SNS topic to notify. An example of an Amazon SNS topic ARN is ``arn:aws:sns:us-west-2:123456789012:MyTopic`` . For more information about Amazon SNS topics, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html>`_ .

            

            

          Encoding -> (string)

            

            The encoding to use for the email within the Amazon SNS notification. UTF-8 is easier to use, but may not preserve all special characters when a message was encoded with a different encoding format. Base64 preserves all special characters. The default value is UTF-8.

            

            

          

        

      

    ScanEnabled -> (boolean)

      

      If ``true`` , then messages to which this receipt rule applies are scanned for spam and viruses. The default value is ``false`` .

      

      

    

  

