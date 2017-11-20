---
title: DFT_P11 de V2. XML 2.4 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DFT_P11 schema
ms.assetid: 3887a8bb-94df-4a3b-b828-f46013d1abb8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8142e3b878fbffa782e467d64906076b06320318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dftp11-in-v2xml-24"></a><span data-ttu-id="b3788-102">DFT_P11 de V2. 2.4 DE XML</span><span class="sxs-lookup"><span data-stu-id="b3788-102">DFT_P11 in V2.XML 2.4</span></span>
<span data-ttu-id="b3788-103">Debe cambiar manualmente el código siguiente en el esquema DFT_P11 V2. 2.4 XML después de ejecutar la herramienta Update2XMLSchema:</span><span class="sxs-lookup"><span data-stu-id="b3788-103">You must manually change the following code in the DFT_P11 schema in V2.XML 2.4 after running the Update2XMLSchema tool:</span></span>  
  
```  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
<xsd:element ref="PV1" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="PV2" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
```  
  
 <span data-ttu-id="b3788-104">Debe reemplazar el código anterior con los siguientes valores, con el fin de corregir la ambigüedad deberse a varias repeticiones de la **ROL** definición de elemento:</span><span class="sxs-lookup"><span data-stu-id="b3788-104">You must replace the above code with the following, in order to fix the ambiguity caused by multiple occurrences of the **ROL** element definition:</span></span>  
  
```  
<xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
  <xsd:choice minOccurs="0" maxOccurs="1">  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV1" />  
      <xsd:element minOccurs="0" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
  </xsd:choice>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3788-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3788-105">See Also</span></span>  
 <span data-ttu-id="b3788-106">[Actualizaciones manuales necesarias](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span><span class="sxs-lookup"><span data-stu-id="b3788-106">[Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span></span>  
 [<span data-ttu-id="b3788-107">Utilidades</span><span class="sxs-lookup"><span data-stu-id="b3788-107">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)