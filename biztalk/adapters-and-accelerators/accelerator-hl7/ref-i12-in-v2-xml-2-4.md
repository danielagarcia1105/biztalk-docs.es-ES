---
title: REF_I12 de V2. XML 2.4 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF_I12 schema
ms.assetid: 95f40b75-a176-4fc6-b9ad-65721d456ea4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a230611424efb527eec6f75f6fb7623561760e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206028"
---
# <a name="refi12-in-v2xml-24"></a>REF_I12 de V2. 2.4 DE XML
Debe cambiar manualmente el código siguiente en el esquema REF_I12 V2. 2.4 XML después de ejecutar la herramienta Update2XMLSchema:  
  
```  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
```  
  
 Debe reemplazar el código anterior con los siguientes valores, con el fin de corregir la ambigüedad deberse a varias repeticiones de la **REF** definición de elemento:  
  
```  
<xsd:element minOccurs="0" maxOccurs="2" ref="REF_I12.PATIENT_VISIT" />  
```  
  
## <a name="see-also"></a>Vea también  
 [Actualizaciones manuales necesarias](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)   
 [Utilidades](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)