[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront delete-streaming-distribution:


*****************************
delete-streaming-distribution
*****************************



===========
Description
===========



Delete a streaming distribution. To delete an RTMP distribution using the CloudFront API, perform the following steps.

 

 **To delete an RTMP distribution using the CloudFront API** :

 

 
* Disable the RTMP distribution. 
 
* Submit a ``GET Streaming Distribution Config`` request to get the current configuration and the ``Etag`` header for the distribution.  
 
* Update the XML document that was returned in the response to your ``GET Streaming Distribution Config`` request to change the value of ``Enabled`` to ``false`` . 
 
* Submit a ``PUT Streaming Distribution Config`` request to update the configuration for your distribution. In the request body, include the XML document that you updated in Step 3. Then set the value of the HTTP ``If-Match`` header to the value of the ``ETag`` header that CloudFront returned when you submitted the ``GET Streaming Distribution Config`` request in Step 2. 
 
* Review the response to the ``PUT Streaming Distribution Config`` request to confirm that the distribution was successfully disabled. 
 
* Submit a ``GET Streaming Distribution Config`` request to confirm that your changes have propagated. When propagation is complete, the value of ``Status`` is ``Deployed`` . 
 
* Submit a ``DELETE Streaming Distribution`` request. Set the value of the HTTP ``If-Match`` header to the value of the ``ETag`` header that CloudFront returned when you submitted the ``GET Streaming Distribution Config`` request in Step 2. 
 
* Review the response to your ``DELETE Streaming Distribution`` request to confirm that the distribution was successfully deleted. 
 

 

For information about deleting a distribution using the CloudFront console, see `Deleting a Distribution <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowToDeleteDistribution.html>`_ in the *Amazon CloudFront Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/DeleteStreamingDistribution>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    delete-streaming-distribution
  --id <value>
  [--if-match <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The distribution ID. 

  

``--if-match`` (string)


  The value of the ``ETag`` header that you received when you disabled the streaming distribution. For example: ``E2QWRUHAPOMQZL`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None