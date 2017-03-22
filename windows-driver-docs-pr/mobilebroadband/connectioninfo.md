---
title: ConnectionInfo
description: ConnectionInfo
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bbdba286-4d28-46b6-bafa-83cbddd883ae
---

# ConnectionInfo


The ConnectionInfo element specifies a list of connections for the specified operator.

## <span id="Usage"></span><span id="usage"></span><span id="USAGE"></span>Usage


``` syntax
<ConnectionInfoList AccessString=”xs:string” Username=”xs:string” Password=”xs:string” FriendlyName=”xs:string” Purchase=”xs:Boolean” Internet=”xs:Boolean” AutoConnectOrder=”xs:positiveinteger” Compression=”xs:token” AutoProtocol=”xs:token”>
</ConnectionInfoList>
```

## <span id="Attributes"></span><span id="attributes"></span><span id="ATTRIBUTES"></span>Attributes


<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccessString</p></td>
<td><p>xs:string</p></td>
<td><p>No</p></td>
<td><p>The name and country/region of the operator.</p>
<p>Example: Contoso (Argentina)</p></td>
</tr>
<tr class="even">
<td><p>Username</p></td>
<td><p>xs:string</p></td>
<td><p>No</p></td>
<td><p>The username is used to connect to the Internet.</p></td>
</tr>
<tr class="odd">
<td><p>Password</p></td>
<td><p>xs:string</p></td>
<td><p>No</p></td>
<td><p>The password used to connect to the Internet.</p></td>
</tr>
<tr class="even">
<td><p>FriendlyName</p></td>
<td><p>xs:string</p></td>
<td><p>No</p></td>
<td><p>The value shown in Windows Connection Manager in the APN drop-down box.</p></td>
</tr>
<tr class="odd">
<td><p>Purchase</p></td>
<td><p>xs:boolean</p></td>
<td><p>Yes</p></td>
<td><p>Denotes whether the access string should be used for purchase or Internet.</p></td>
</tr>
<tr class="even">
<td><p>Internet</p></td>
<td><p>xs:boolean</p></td>
<td><p>Yes</p></td>
<td><p>Denotes whether the access string should be used for purchase or Internet.</p></td>
</tr>
<tr class="odd">
<td><p>AutoConnectOrder</p></td>
<td><p>xs:positiveinteger</p></td>
<td><p>No</p></td>
<td><p>Determines the order in which Windows tries to connect to each of the APNs in the [ConnectionInfoList](connectioninfolist.md) element.</p></td>
</tr>
<tr class="even">
<td><p>Compression</p></td>
<td><p>xs:token</p></td>
<td><p>No</p></td>
<td><p>Specifies if compression will be used at the data link for header and data transfer.</p>
<p>Values: ENABLE or DISABLE</p></td>
</tr>
<tr class="odd">
<td><p>AuthProtocol</p></td>
<td><p>xs:token</p></td>
<td><p>No</p></td>
<td><p>Specifies the authentication protocol used for activating a PDP context.</p>
<p>Values: NONE, PAP, CHAP, or MsCHAPv2</p></td>
</tr>
</tbody>
</table>

 

## <span id="Child_elements"></span><span id="child_elements"></span><span id="CHILD_ELEMENTS"></span>Child elements


There are no child elements.

## <span id="Parent_elements"></span><span id="parent_elements"></span><span id="PARENT_ELEMENTS"></span>Parent elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[ConnectionInfoList](connectioninfolist.md)</p></td>
<td><p>Specifies the details for an operator in the APN database.</p></td>
</tr>
</tbody>
</table>

 

## <span id="XSD"></span><span id="xsd"></span>XSD


``` syntax
<xs:element ref="ConnectionInfo" maxOccurs="unbounded"/>

<xs:element name="ConnectionInfo">
  <xs:complexType>
    <xs:attribute name="AccessString" use="optional">
      <!--The AccessString element identifies the APN or dial string to be used to establish a data connection -->
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="0"/>
          <xs:maxLength value="100"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="Username" use="optional">
      <!--The UserName element specifies the user name for logon -->
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="0"/>
          <xs:maxLength value="255"/>
          <xs:whiteSpace value="collapse"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="Password" use="optional">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="0"/>
          <xs:maxLength value="255"/>
          <xs:whiteSpace value="collapse"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="FriendlyName" use="optional">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:minLength value="0"/>
          <xs:maxLength value="255"/>
          <xs:whiteSpace value="collapse"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="Purchase" type="xs:boolean" use="required"/>
    <xs:attribute name="Internet" type="xs:boolean" use="required"/>
    <xs:attribute name="AutoConnectOrder" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="Compression" use="optional">
      <xs:simpleType>
        <xs:restriction base="xs:token">
          <xs:enumeration value="DISABLE"/>
          <xs:enumeration value="ENABLE"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
    <xs:attribute name="AuthProtocol" use="optional">
      <xs:simpleType>
        <xs:restriction base="xs:token">
          <xs:enumeration value="NONE"/>
          <xs:enumeration value="PAP"/>
          <xs:enumeration value="CHAP"/>
          <xs:enumeration value="MsCHAPv2"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
</xs:element>
```

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The ConnectionInfo element is required.

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_mb\p_mb%5D:%20ConnectionInfo%20%20RELEASE:%20%281/18/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



