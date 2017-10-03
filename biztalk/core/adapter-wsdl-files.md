---
title: Archivos WSDL del adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d4b35c0-1e4b-4106-8921-29d14f976d65
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c600729411066637e021a118b88ec97ffd3b25fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-wsdl-files"></a><span data-ttu-id="fef73-102">Archivos WSDL del adaptador</span><span class="sxs-lookup"><span data-stu-id="fef73-102">Adapter WSDL Files</span></span>
<span data-ttu-id="fef73-103">En el Asistente para agregar metadatos de adaptador está seleccionado y de entrada en el archivo de lenguaje de descripción de servicios Web (WSDL) la **seleccionar servicios para importar** página.</span><span class="sxs-lookup"><span data-stu-id="fef73-103">In the Add Adapter Metadata Wizard the Web Services Description Language (WSDL) file is selected and input on the **Select Services to Import** page.</span></span> <span data-ttu-id="fef73-104">El asistente lee los archivos WSDL expuestos por el servicio y seleccionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fef73-104">The wizard reads the WSDL files exposed by the service and selected by the user.</span></span> <span data-ttu-id="fef73-105">Después crea y agrega un archivo XSD y una orquestación en el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fef73-105">It then creates and adds an XSD file and an orchestration in the BizTalk project.</span></span>  
  
 <span data-ttu-id="fef73-106">En el adaptador de archivo de ejemplo, el archivo Service1.wsdl contiene las definiciones XSD que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fef73-106">In the sample file adapter, the Service1.wsdl file contains the XSD definitions that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adds to the project.</span></span> <span data-ttu-id="fef73-107">Puede optar por modificar el archivo Service1.wsdl o crear su propio archivo WSDL que contenga las definiciones XSD que va a agregar al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fef73-107">You may choose to modify the Service1.wsdl file or create your own WSDL file that contains the XSD definitions to add to your BizTalk project.</span></span>  
  
 <span data-ttu-id="fef73-108">El código siguiente procede del archivo Service1.wsdl:</span><span class="sxs-lookup"><span data-stu-id="fef73-108">The following code is from the Service1.wsdl file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://tempuri.org/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://tempuri.org/" xmlns="http://schemas.xmlsoap.org/wsdl/">  
  <types>  
    <s:schema elementFormDefault="qualified" targetNamespace="http://tempuri.org/">  
      <s:element name="GetTaxID">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetTaxIDResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetTaxIDResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetPayStub">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetPayStubResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetPayStubResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetTaxInfo">  
        <s:complexType />  
      </s:element>  
  
```