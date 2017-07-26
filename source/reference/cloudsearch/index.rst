[ :ref:`aws <cli:aws>` ]

.. _cli:aws cloudsearch:


***********
cloudsearch
***********



===========
Description
===========

 

You use the Amazon CloudSearch configuration service to create, configure, and manage search domains. Configuration service requests are submitted using the AWS Query protocol. AWS Query requests are HTTP or HTTPS requests submitted via HTTP GET or POST with a query parameter named Action.

 

The endpoint for configuration service requests is region-specific: cloudsearch.*region* .amazonaws.com. For example, cloudsearch.us-east-1.amazonaws.com. For a current list of supported regions and endpoints, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#cloudsearch_region>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  build-suggesters
  create-domain
  define-analysis-scheme
  define-expression
  define-index-field
  define-suggester
  delete-analysis-scheme
  delete-domain
  delete-expression
  delete-index-field
  delete-suggester
  describe-analysis-schemes
  describe-availability-options
  describe-domains
  describe-expressions
  describe-index-fields
  describe-scaling-parameters
  describe-service-access-policies
  describe-suggesters
  index-documents
  list-domain-names
  update-availability-options
  update-scaling-parameters
  update-service-access-policies
