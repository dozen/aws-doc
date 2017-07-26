[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch update-availability-options:


***************************
update-availability-options
***************************



===========
Description
===========



Configures the availability options for a domain. Enabling the Multi-AZ option expands an Amazon CloudSearch domain to an additional Availability Zone in the same Region to increase fault tolerance in the event of a service disruption. Changes to the Multi-AZ option can take about half an hour to become active. For more information, see `Configuring Availability Options <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-availability-options.html>`_ in the *Amazon CloudSearch Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/UpdateAvailabilityOptions>`_


========
Synopsis
========

::

    update-availability-options
  --domain-name <value>
  --multi-az | --no-multi-az
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  You expand an existing search domain to a second Availability Zone by setting the Multi-AZ option to true. Similarly, you can turn off the Multi-AZ option to downgrade the domain to a single Availability Zone by setting the Multi-AZ option to ``false`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AvailabilityOptions -> (structure)

  

  The newly-configured availability options. Indicates whether Multi-AZ is enabled for the domain. 

  

  Options -> (boolean)

    

    The availability options configured for the domain.

    

    

  Status -> (structure)

    

    The status of domain configuration option.

    

    CreationDate -> (timestamp)

      

      A timestamp for when this option was created.

      

      

    UpdateDate -> (timestamp)

      

      A timestamp for when this option was last updated.

      

      

    UpdateVersion -> (integer)

      

      A unique integer that indicates when this option was last updated.

      

      

    State -> (string)

      

      The state of processing a change to an option. Possible values:

       

       
      * ``RequiresIndexDocuments`` : the option's latest value will not be deployed until  index-documents has been called and indexing is complete.
       
      * ``Processing`` : the option's latest value is in the process of being activated. 
       
      * ``Active`` : the option's latest value is completely deployed.
       
      * ``FailedToValidate`` : the option value is not compatible with the domain's data and cannot be used to index the data. You must either modify the option value or update or remove the incompatible documents.
       

      

      

    PendingDeletion -> (boolean)

      

      Indicates that the option will be deleted once processing is complete.

      

      

    

  

