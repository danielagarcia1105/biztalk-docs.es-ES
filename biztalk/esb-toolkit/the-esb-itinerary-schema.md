---
title: El esquema de itinerarios de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 168e7b98-6282-494e-bde8-3171e0be7d59
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66bcbe6780105a97e58df393d0e060688048a02b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295228"
---
# <a name="the-esb-itinerary-schema"></a>El esquema de itinerarios de ESB
El esquema de ESB itinerario denominado Itinerary.xsd define un itinerario como un conjunto de instrucciones, que suele denominadas servicios itinerarios de procesamiento. Un servicio itinerario puede contener uno o más servicios itinerarios y las cadenas de conexión de resolución correspondiente, tal y como se muestra en la siguiente definición de esquema.  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary" targetNamespace="http://schemas.microsoft.biztalk.practices.esb.com/itinerary" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <xs:annotation>  
    <xs:appinfo>  
      <b:schemaInfo root_reference="Itinerary" xmlns:b="http://schemas.microsoft.con/BizTalk/2003" />  
    </xs:appinfo>  
  </xs:annotation>  
  <xs:element name="Itinerary">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="BizTalkSegment">  
          <xs:complexType>  
            <xs:attribute name="interchangeId" type="xs:string" />  
            <xs:attribute name="epmRRCorrelationToken" type="xs:string" />  
            <xs:attribute name="receiveInstanceId" type="xs:string" />  
            <xs:attribute name="messageId" type="xs:string" />  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="ServiceInstance">  
          <xs:complexType>  
            <xs:attribute name="uuid" type="xs:string" />  
            <xs:attribute name="name" type="xs:string" />  
            <xs:attribute name="type" type="xs:string" />  
            <xs:attribute name="state" type="xs:string" />  
            <xs:attribute name="position" type="xs:int" />  
            <xs:attribute name="isRequestResponse" type="xs:boolean" />  
            <xs:attribute name="stage" type="Stages" />  
          </xs:complexType>  
        </xs:element>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Services">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Services">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" maxOccurs="1" name="PropertyBag" nillable="true">  
                      <xs:complexType>  
                        <xs:sequence minOccurs="0" maxOccurs="1">  
                          <xs:element minOccurs="0" maxOccurs="unbounded" name="Property">  
                            <xs:complexType>  
                              <xs:attribute name="name" type="xs:string" use="required" />  
                              <xs:attribute name="value" type="xs:string" use="required" />  
                            </xs:complexType>  
                          </xs:element>  
                        </xs:sequence>  
                      </xs:complexType>  
                    </xs:element>  
                  </xs:sequence>  
                  <xs:attribute name="uuid" type="xs:string" />  
                  <xs:attribute name="beginTime" type="xs:string" />  
                  <xs:attribute name="completeTime" type="xs:string" />  
                  <xs:attribute name="name" type="xs:string" />  
                  <xs:attribute name="type" type="xs:string" />  
                  <xs:attribute name="state" type="xs:string" />  
                  <xs:attribute name="resolve" type="xs:boolean" />  
                  <xs:attribute name="isRequestResponse" type="xs:boolean" />  
                  <xs:attribute name="position" type="xs:int" />  
                  <xs:attribute name="serviceInstanceId" type="xs:string" />  
                  <xs:attribute name="isTrackingEnabled">  
                    <xs:simpleType>  
                      <xs:restriction base="xs:boolean" />  
                    </xs:simpleType>  
                  </xs:attribute>  
                  <xs:attribute name="stage" type="Stages" />  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="ResolverGroups">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element maxOccurs="unbounded" name="Resolvers">  
                <xs:complexType>  
                  <xs:simpleContent>  
                    <xs:extension base="xs:string">  
                      <xs:attribute name="serviceId" type="xs:string" />  
                    </xs:extension>  
                  </xs:simpleContent>  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
      <xs:attribute name="uuid" type="xs:string" />  
      <xs:attribute name="beginTime" type="xs:string" />  
      <xs:attribute name="completeTime" type="xs:string" />  
      <xs:attribute name="state" type="xs:string" />  
      <xs:attribute name="isRequestResponse" type="xs:boolean" />  
      <xs:attribute name="servicecount" type="xs:int" use="required" />  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="Stages">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="notSpecified" />  
      <xs:enumeration value="receiveInbound" />  
      <xs:enumeration value="receiveTransmit" />  
      <xs:enumeration value="sendTransmit" />  
      <xs:enumeration value="sendInbound" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
 El **ServiceInstance** elemento corresponde al servicio itinerario actual y contiene las propiedades como **nombre**, **tipo**, **estado**, y **posición** que el servicio se promociona en el contexto del mensaje. El esquema llamado sistema-Properties.xsd en el **Microsoft.Practices.ESB.ItinerarySchemas** ensamblado define estas propiedades.  
  
 El **servicios** elemento representa un conjunto de servicios itinerarios, con cada servicio se define por su estado, empezar a tiempo, la hora de finalización, tipo (**orquestación** o **mensajería**) y, opcionalmente, fase (**receiveInbound**, **receiveTransmit**, **sendTransmit**, **sendInbound**).  
  
 El **ResolverGroups** elemento contiene varias **resoluciones** elementos, cada uno de los cuales define uno o más cadenas de conexión de resolución que hace referencia a un itinerario a través de la **serviceid**  atributo.  
  
 La siguiente muestra un ejemplo de un encabezado SOAP itinerario enviado antes de que lo procese el componente de canalización de itinerario ESB.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Itinerary xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" uuid="" beginTime="" completeTime="" state="Pending" isRequestResponse="false" xmlns="http://schemas.microsoft.biztalk.practices.esb.com/itinerary">  
  
  <ServiceInstance uuid="" name="Microsoft.Practices.ESB.Services.Transform" type="Messaging" state="Pending" position="0" isRequestResponse="false" xmlns="" />  
  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="Microsoft.Practices.ESB.Services.Transform" type="Messaging" state="Pending" isRequestResponse="false" position="0" serviceInstanceId="" />  
  </Services>  
  
  <Services xmlns="">  
    <Service uuid="" beginTime="" completeTime="" name="DynamicResolutionSolicitResp" type="Messaging" state="Pending" isRequestResponse="true" position="1" serviceInstanceId="" />  
  </Services>  
  
  <ResolverGroups xmlns="">  
    <Resolvers serviceId="DynamicResolutionSolicitResp1"><![CDATA[BRE:\\policy=GetCanadaEndPoint;version=;useMsg=;]]></Resolvers>  
  
    <Resolvers serviceId="Microsoft.Practices.ESB.Services.Transform0"><![CDATA[BRE:\\policy=CanadaSubmitOrderMaps;version=;useMsg=;]]></Resolvers>  
  </ResolverGroups>  
  
</Itinerary>  
```