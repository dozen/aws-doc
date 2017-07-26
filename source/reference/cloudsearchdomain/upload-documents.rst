[ :ref:`aws <cli:aws>` . :ref:`cloudsearchdomain <cli:aws cloudsearchdomain>` ]

.. _cli:aws cloudsearchdomain upload-documents:


****************
upload-documents
****************



===========
Description
===========



Posts a batch of documents to a search domain for indexing. A document batch is a collection of add and delete operations that represent the documents you want to add, update, or delete from your domain. Batches can be described in either JSON or XML. Each item that you want Amazon CloudSearch to return as a search result (such as a product) is represented as a document. Every document has a unique ID and one or more fields that contain the data that you want to search and return in results. Individual documents cannot contain more than 1 MB of data. The entire batch cannot exceed 5 MB. To get the best possible upload performance, group add and delete operations in batches that are close the 5 MB limit. Submitting a large volume of single-document batches can overload a domain's document service. 

 

The endpoint for submitting ``upload-documents`` requests is domain-specific. To get the document endpoint for your domain, use the Amazon CloudSearch configuration service ``DescribeDomains`` action. A domain's endpoints are also displayed on the domain dashboard in the Amazon CloudSearch console. 

 

For more information about formatting your data for Amazon CloudSearch, see `Preparing Your Data`_ in the *Amazon CloudSearch Developer Guide* . For more information about uploading data for indexing, see `Uploading Data`_ in the *Amazon CloudSearch Developer Guide* . 



========
Synopsis
========

::

    upload-documents
  --documents <value>
  --content-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--documents`` (blob)


  A batch of documents formatted in JSON or HTML.

  

``--content-type`` (string)


  The format of the batch you are uploading. Amazon CloudSearch supports two document batch formats:

   

   
  * application/json
   
  * application/xml
   

  

  Possible values:

  
  *   ``application/json``

  
  *   ``application/xml``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

status -> (string)

  

  The status of an ``UploadDocumentsRequest`` .

  

  

adds -> (long)

  

  The number of documents that were added to the search domain.

  

  

deletes -> (long)

  

  The number of documents that were deleted from the search domain.

  

  

warnings -> (list)

  

  Any warnings returned by the document service about the documents being uploaded.

  

  (structure)

    

    A warning returned by the document service when an issue is discovered while processing an upload request.

    

    message -> (string)

      

      The description for a warning returned by the document service.

      

      

    

  



.. _Uploading Data: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/uploading-data.html
.. _Preparing Your Data: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/preparing-data.html
