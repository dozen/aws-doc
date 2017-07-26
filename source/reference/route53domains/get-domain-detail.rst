[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-domain-detail:


*****************
get-domain-detail
*****************



===========
Description
===========



This operation returns detailed information about a specified domain that is associated with the current AWS account. Contact information for the domain is also returned as part of the output.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/GetDomainDetail>`_


========
Synopsis
========

::

    get-domain-detail
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain that you want to get detailed information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainName -> (string)

  

  The name of a domain.

  

  

Nameservers -> (list)

  

  The name of the domain.

  

  (structure)

    

    Nameserver includes the following elements.

    

    Name -> (string)

      

      The fully qualified host name of the name server.

       

      Constraint: Maximum 255 characters

      

      

    GlueIps -> (list)

      

      Glue IP address of a name server entry. Glue IP addresses are required only when the name of the name server is a subdomain of the domain. For example, if your domain is example.com and the name server for the domain is ns.example.com, you need to specify the IP address for ns.example.com.

       

      Constraints: The list can contain only one IPv4 and one IPv6 address.

      

      (string)

        

        

      

    

  

AutoRenew -> (boolean)

  

  Specifies whether the domain registration is set to renew automatically.

  

  

AdminContact -> (structure)

  

  Provides details about the domain administrative contact.

  

  FirstName -> (string)

    

    First name of contact.

    

    

  LastName -> (string)

    

    Last name of contact.

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

    

    

  City -> (string)

    

    The city of the contact's address.

    

    

  State -> (string)

    

    The state or province of the contact's city.

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  Email -> (string)

    

    Email address of the contact.

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

        

        

      

    

  

RegistrantContact -> (structure)

  

  Provides details about the domain registrant.

  

  FirstName -> (string)

    

    First name of contact.

    

    

  LastName -> (string)

    

    Last name of contact.

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

    

    

  City -> (string)

    

    The city of the contact's address.

    

    

  State -> (string)

    

    The state or province of the contact's city.

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  Email -> (string)

    

    Email address of the contact.

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

        

        

      

    

  

TechContact -> (structure)

  

  Provides details about the domain technical contact.

  

  FirstName -> (string)

    

    First name of contact.

    

    

  LastName -> (string)

    

    Last name of contact.

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

    

    

  City -> (string)

    

    The city of the contact's address.

    

    

  State -> (string)

    

    The state or province of the contact's city.

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  Email -> (string)

    

    Email address of the contact.

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

        

        

      

    

  

AdminPrivacy -> (boolean)

  

  Specifies whether contact information for the admin contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

  

RegistrantPrivacy -> (boolean)

  

  Specifies whether contact information for the registrant contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

  

TechPrivacy -> (boolean)

  

  Specifies whether contact information for the tech contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

  

  

RegistrarName -> (string)

  

  Name of the registrar of the domain as identified in the registry. Amazon Route 53 domains are registered by registrar Gandi. The value is ``"GANDI SAS"`` . 

  

  

WhoIsServer -> (string)

  

  The fully qualified name of the WHOIS server that can answer the WHOIS query for the domain.

  

  

RegistrarUrl -> (string)

  

  Web address of the registrar.

  

  

AbuseContactEmail -> (string)

  

  Email address to contact to report incorrect contact information for a domain, to report that the domain is being used to send spam, to report that someone is cybersquatting on a domain name, or report some other type of abuse.

  

  

AbuseContactPhone -> (string)

  

  Phone number for reporting abuse.

  

  

RegistryDomainId -> (string)

  

  Reserved for future use.

  

  

CreationDate -> (timestamp)

  

  The date when the domain was created as found in the response to a WHOIS query. The date format is Unix time.

  

  

UpdatedDate -> (timestamp)

  

  The last updated date of the domain as found in the response to a WHOIS query. The date format is Unix time.

  

  

ExpirationDate -> (timestamp)

  

  The date when the registration for the domain is set to expire. The date format is Unix time.

  

  

Reseller -> (string)

  

  Reseller of the domain. Domains registered or transferred using Amazon Route 53 domains will have ``"Amazon"`` as the reseller. 

  

  

DnsSec -> (string)

  

  Reserved for future use.

  

  

StatusList -> (list)

  

  An array of domain name status codes, also known as Extensible Provisioning Protocol (EPP) status codes.

   

  ICANN, the organization that maintains a central database of domain names, has developed a set of domain name status codes that tell you the status of a variety of operations on a domain name, for example, registering a domain name, transferring a domain name to another registrar, renewing the registration for a domain name, and so on. All registrars use this same set of status codes.

   

  For a current list of domain name status codes and an explanation of what each code means, go to the `ICANN website <https://www.icann.org/>`_ and search for ``epp status codes`` . (Search on the ICANN website; web searches sometimes return an old version of the document.)

  

  (string)

    

    

  

