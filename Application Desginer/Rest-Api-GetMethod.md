### GET method

Use the GET method to retrieve business object resources and object structure resources.

### Syntax

***GET uri?parameter=value?parameter=value&...***

***uri*** is a URI. The length of the URI path cannot exceed any system specified limit.

***parameter*** is a query parameter.

***value*** is the value of the query parameter.

### Example: Retrieving a business object resource
The following method retrieves a business object resource:
***GET /maxrest/rest/mbo/asset/123***

The following XML is returned:
<?xml version="1.0" encoding="UTF-8" ?> 
  <ASSET xmlns="http://www.ibm.com/maximo"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <ASSETNUM>11200</ASSETNUM> 
    <SERIALNUM>3481-52</SERIALNUM> 
    <ASSETTAG>3751</ASSETTAG> 
    <LOCATION>BR200</LOCATION> 
    <DESCRIPTION>HVAC System- 50 Ton Cool Cap/ 450000 Btu Heat Cap</DESCRIPTION> 
    <ASSETUID>123</ASSETUID> 
    .
    .
  </ASSET>
  
The resource response is shown in XML. The default format setting can be configured in the ***mxe.rest.mbo.defaultformat*** system property.


### Example: Retrieving an object structure resource
The following method retrieves an object structure resource:
***GET /maxrest/rest/mbo/mxasset/123***

The following XML is returned:

<?xml version="1.0" encoding="UTF-8" ?> 
  <QueryMXASSETResponse xmlns="http://www.ibm.com/maximo" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    creationDateTime="2011-04-07T11:43:59-04:00" 
    transLanguage="EN" baseLanguage="EN" messageID="1302195161355515345" 
    maximoVersion="7 5 20110405-0030 V7500-718" rsStart="0" rsTotal="1" 
    rsCount="1"> 
    <MXASSETSet> 
      <ASSET> 
        <ASSETNUM>11200</ASSETNUM> 
        <SERIALNUM>3481-52</SERIALNUM> 
        <ASSETTAG>3751</ASSETTAG> 
        <LOCATION>BR200</LOCATION> 
        <DESCRIPTION>HVAC System- 50 Ton Cool Cap/ 450000 Btu Heat Cap</DESCRIPTION>
        <ASSETUID>123</ASSETUID> 
        .
        .
        <ASSETMETER> 
          <ACTIVE>1</ACTIVE> 
          <ASSETMETERID>63</ASSETMETERID> 
          <LASTREADING>0</LASTREADING> 
          <METERNAME>PRESSURE</METERNAME> 
          .
          .
        </ASSETMETER> 
        <ASSETSPEC> 
          <ASSETATTRID>SPEED</ASSETATTRID> 
          <ASSETSPECID>2138</ASSETSPECID> 
          .
          .
        </ASSETSPEC> 
        <ASSETSPEC> 
          <ASSETATTRID>SHAFTDIA</ASSETATTRID> 
          <ASSETSPECID>2139</ASSETSPECID> 
          .
          .
        </ASSETSPEC> 
      </ASSET> 
    </MXASSETSet> 
  </QueryMXASSETResponse>

The object structure resource data includes asset, asset meter, and asset specification data based on the configuration of the objects within the MXASSET object structure. Any fields that are configured to be included or excluded are implemented in the data.

The URI path can contain the ID of the resource as a way to select a specific resource. In the preceding example, the ID is 123. The ID value is a unique ID for the object that is registered in the MAXATTRIBUTE table. If no ID is provided, the response includes all occurrences of the resource, depending on the security restrictions on the user. The ID is the only business object field that can be part of the URI path for selection criteria. All other fields can be used as a query parameter in the URI for selection filtering.


### Example: Selecting related child resources
The following method requests a PO resource for a business object resource:

***GET /maxrest/rest/mbo/po/13***

The following XML is returned:
<?xml version="1.0" encoding="UTF-8" ?> 
  <PO xmlns="http://www.ibm.com/maximo" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <PONUM>1005</PONUM> 
    <DESCRIPTION>Electrical Supplies</DESCRIPTION>
    .
    .
  </PO>

### Example: Selecting related PO lines of a PO
The following method requests all of the PO lines that are related to the PO that is selected in the previous example:
***GET /maxrest/rest/mbo/po/13/poline***

The following XML is returned:
<?xml version="1.0" encoding="UTF-8" ?> 
  <POLINEMboSet rsStart="0" rsTotal="2" rsCount="2" 
    xmlns="http://www.ibm.com/maximo" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <POLINE xmlns="http://www.ibm.com/maximo" 
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <PONUM>1005</PONUM> 
      <ITEMNUM>11241</ITEMNUM> 
      <STORELOC>CENTRAL</STORELOC> 
      <ORDERQTY>3.0</ORDERQTY> 
      <POLINENUM>1</POLINENUM> 
      <POLINEID>10051</POLINEID> 
      .
      .
    </POLINE>
    <POLINE xmlns="http://www.ibm.com/maximo" 
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <PONUM>1005</PONUM> 
      <ITEMNUM>29331</ITEMNUM> 
      <STORELOC>PKG</STORELOC> 
      <ORDERQTY>2.0</ORDERQTY> 
      <POLINENUM>2</POLINENUM> 
      <POLINEID>10052</POLINEID> 
      .
      .
    </POLINE>
  </POLINEMboSet>

If you select POLINE, the relationship name that is specified in the URI (POLINE) identifies the path from the business object (PO) to a related business object (POLINE). In this example, the business object and the relationship have the same name. An object can have many relationships between two objects that can result in different data being selected for the related object. Relationships are defined in the MAXRELATIONSHIP table.

To retrieve only the line of a specific POLINE business object, include the ID of the POLINE business object in the URI:
***GET /maxrest/rest/mbo/po13/poline/10052***

In this example, poline represents the relationship name and 10052 is the ID of the POLINE business object that the relationship retrieves. You can use the same approach to specify the path from POLINE to ITEM or POCOST:

***GET /maxrest/rest/mbo/po/13/poline/10052/item***
***GET /maxrest/rest/mbo/po/13/poline/10052/pocost***

When you use the object structure resource, child objects cannot have relationships. The object structure supports a graph of related business objects. The relationships are part of the object structure definition.

You can traverse related business objects to move from one resource to another if a valid relationship exists between the source and target object.
