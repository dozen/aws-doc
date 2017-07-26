[ :ref:`aws <cli:aws>` ]

.. _cli:aws cloudsearchdomain:


*****************
cloudsearchdomain
*****************



===========
Description
===========



You use the AmazonCloudSearch2013 API to upload documents to a search domain and search those documents. 

 

The endpoints for submitting ``upload-documents`` , ``search`` , and ``suggest`` requests are domain-specific. To get the endpoints for your domain, use the Amazon CloudSearch configuration service ``DescribeDomains`` action. The domain endpoints are also displayed on the domain dashboard in the Amazon CloudSearch console. You submit suggest requests to the search endpoint. 

 

For more information, see the `Amazon CloudSearch Developer Guide <http://docs.aws.amazon.com/cloudsearch/latest/developerguide>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  search
  suggest
  upload-documents
