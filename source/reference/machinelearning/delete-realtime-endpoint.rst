[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-realtime-endpoint:


************************
delete-realtime-endpoint
************************



===========
Description
===========



Deletes a real time endpoint of an ``MLModel`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteRealtimeEndpoint>`_


========
Synopsis
========

::

    delete-realtime-endpoint
  --ml-model-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ml-model-id`` (string)


  The ID assigned to the ``MLModel`` during creation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MLModelId -> (string)

  

  A user-supplied ID that uniquely identifies the ``MLModel`` . This value should be identical to the value of the ``MLModelId`` in the request.

  

  

RealtimeEndpointInfo -> (structure)

  

  The endpoint information of the ``MLModel``  

  

  PeakRequestsPerSecond -> (integer)

    

    The maximum processing rate for the real-time endpoint for ``MLModel`` , measured in incoming requests per second.

    

    

  CreatedAt -> (timestamp)

    

    The time that the request to create the real-time endpoint for the ``MLModel`` was received. The time is expressed in epoch time.

    

    

  EndpointUrl -> (string)

    

    The URI that specifies where to send real-time prediction requests for the ``MLModel`` .

     

    .. note::

      Note 

      The application must wait until the real-time endpoint is ready before using this URI.

       

    

    

  EndpointStatus -> (string)

    

    The current status of the real-time endpoint for the ``MLModel`` . This element can have one of the following values: 

     

     
    * ``NONE`` - Endpoint does not exist or was previously deleted.
     
    * ``READY`` - Endpoint is ready to be used for real-time predictions.
     
    * ``UPDATING`` - Updating/creating the endpoint. 
     

    

    

  

