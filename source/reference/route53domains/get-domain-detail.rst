[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-domain-detail:


*****************
get-domain-detail
*****************



===========
Description
===========



This operation returns detailed information about the domain. The domain's contact information is also returned as part of the output.



========
Synopsis
========

::

    get-domain-detail
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

   

  Required: Yes

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DomainName -> (string)

  

  The name of a domain.

   

  Type: String

  

  

Nameservers -> (list)

  

  The name of the domain.

   

  Type: String

  

  (structure)

    

    Nameserver includes the following elements.

    

    Name -> (string)

      

      The fully qualified host name of the name server.

       

      Type: String

       

      Constraint: Maximum 255 characterss

       

      Parent: ``Nameservers`` 

      

      

    GlueIps -> (list)

      

      Glue IP address of a name server entry. Glue IP addresses are required only when the name of the name server is a subdomain of the domain. For example, if your domain is example.com and the name server for the domain is ns.example.com, you need to specify the IP address for ns.example.com.

       

      Type: List of IP addresses.

       

      Constraints: The list can contain only one IPv4 and one IPv6 address.

       

      Parent: ``Nameservers`` 

      

      (string)

        

        

      

    

  

AutoRenew -> (boolean)

  

  Specifies whether the domain registration is set to renew automatically.

   

  Type: Boolean

  

  

AdminContact -> (structure)

  

  Provides details about the domain administrative contact. 

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

  

  FirstName -> (string)

    

    First name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  LastName -> (string)

    

    Last name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  City -> (string)

    

    The city of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  State -> (string)

    

    The state or province of the contact's city.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  Email -> (string)

    

    Email address of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 254 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

     

    Type: Complex

     

    Default: None

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Children: ``Name`` , ``Value`` 

     

    Required: No

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

         

        Type: String

         

        Default: None

         

        Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 2048 characters.

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      

    

  

RegistrantContact -> (structure)

  

  Provides details about the domain registrant. 

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

  

  FirstName -> (string)

    

    First name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  LastName -> (string)

    

    Last name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  City -> (string)

    

    The city of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  State -> (string)

    

    The state or province of the contact's city.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  Email -> (string)

    

    Email address of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 254 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

     

    Type: Complex

     

    Default: None

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Children: ``Name`` , ``Value`` 

     

    Required: No

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

         

        Type: String

         

        Default: None

         

        Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 2048 characters.

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      

    

  

TechContact -> (structure)

  

  Provides details about the domain technical contact.

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

  

  FirstName -> (string)

    

    First name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  LastName -> (string)

    

    Last name of contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ContactType -> (string)

    

    Indicates whether the contact is a person, company, association, or public organization. If you choose an option other than ``PERSON`` , you must enter an organization name, and you can't enable privacy protection for the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Valid values: ``PERSON`` | ``COMPANY`` | ``ASSOCIATION`` | ``PUBLIC_BODY`` 

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  OrganizationName -> (string)

    

    Name of the organization for contact types other than ``PERSON`` .

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters. Contact type must not be ``PERSON`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  AddressLine1 -> (string)

    

    First line of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  AddressLine2 -> (string)

    

    Second line of contact's address, if any.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  City -> (string)

    

    The city of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  State -> (string)

    

    The state or province of the contact's city.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  CountryCode -> (string)

    

    Code for the country of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  ZipCode -> (string)

    

    The zip or postal code of the contact's address.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 255 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  PhoneNumber -> (string)

    

    The phone number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: Yes

    

    

  Email -> (string)

    

    Email address of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Maximum 254 characters.

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact``  

     

    Required: Yes

    

    

  Fax -> (string)

    

    Fax number of the contact.

     

    Type: String

     

    Default: None

     

    Constraints: Phone number must be specified in the format "+[country dialing code].[number including any area code]". For example, a US phone number might appear as ``"+1.1234567890"`` .

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Required: No

    

    

  ExtraParams -> (list)

    

    A list of name-value pairs for parameters required by certain top-level domains.

     

    Type: Complex

     

    Default: None

     

    Parents: ``RegistrantContact`` , ``AdminContact`` , ``TechContact`` 

     

    Children: ``Name`` , ``Value`` 

     

    Required: No

    

    (structure)

      

      ExtraParam includes the following elements.

      

      Name -> (string)

        

        Name of the additional parameter required by the top-level domain.

         

        Type: String

         

        Default: None

         

        Valid values: ``DUNS_NUMBER`` | ``BRAND_NUMBER`` | ``BIRTH_DEPARTMENT`` | ``BIRTH_DATE_IN_YYYY_MM_DD`` | ``BIRTH_COUNTRY`` | ``BIRTH_CITY`` | ``DOCUMENT_NUMBER`` | ``AU_ID_NUMBER`` | ``AU_ID_TYPE`` | ``CA_LEGAL_TYPE`` | ``ES_IDENTIFICATION`` | ``ES_IDENTIFICATION_TYPE`` | ``ES_LEGAL_FORM`` | ``FI_BUSINESS_NUMBER`` | ``FI_ID_NUMBER`` | ``IT_PIN`` | ``RU_PASSPORT_DATA`` | ``SE_ID_NUMBER`` | ``SG_ID_NUMBER`` | ``VAT_NUMBER`` 

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      Value -> (string)

        

        Values corresponding to the additional parameter names required by some top-level domains.

         

        Type: String

         

        Default: None

         

        Constraints: Maximum 2048 characters.

         

        Parent: ``ExtraParams`` 

         

        Required: Yes

        

        

      

    

  

AdminPrivacy -> (boolean)

  

  Specifies whether contact information for the admin contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: Boolean

  

  

RegistrantPrivacy -> (boolean)

  

  Specifies whether contact information for the registrant contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: Boolean

  

  

TechPrivacy -> (boolean)

  

  Specifies whether contact information for the tech contact is concealed from WHOIS queries. If the value is ``true`` , WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: Boolean

  

  

RegistrarName -> (string)

  

  Name of the registrar of the domain as identified in the registry. Amazon Route 53 domains are registered by registrar Gandi. The value is ``"GANDI SAS"`` . 

   

  Type: String

  

  

WhoIsServer -> (string)

  

  The fully qualified name of the WHOIS server that can answer the WHOIS query for the domain.

   

  Type: String

  

  

RegistrarUrl -> (string)

  

  Web address of the registrar.

   

  Type: String

  

  

AbuseContactEmail -> (string)

  

  Email address to contact to report incorrect contact information for a domain, to report that the domain is being used to send spam, to report that someone is cybersquatting on a domain name, or report some other type of abuse. 

   

  Type: String

  

  

AbuseContactPhone -> (string)

  

  Phone number for reporting abuse. 

   

  Type: String

  

  

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

   

  Type: String

  

  

DnsSec -> (string)

  

  Reserved for future use.

  

  

StatusList -> (list)

  

  An array of domain name status codes, also known as Extensible Provisioning Protocol (EPP) status codes.

   

  ICANN, the organization that maintains a central database of domain names, has developed a set of domain name status codes that tell you the status of a variety of operations on a domain name, for example, registering a domain name, transferring a domain name to another registrar, renewing the registration for a domain name, and so on. All registrars use this same set of status codes.

   

  For a current list of domain name status codes and an explanation of what each code means, go to the `ICANN website`_ and search for ``epp status codes`` . (Search on the ICANN website; web searches sometimes return an old version of the document.)

   

  Type: Array of String

  

  (string)

    

    

  



.. _ICANN website: https://www.icann.org/
