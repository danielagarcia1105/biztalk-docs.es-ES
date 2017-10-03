---
title: EncryptionCert (nodo ReceiveLocation) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: EncryptionCert node [binding file]
ms.assetid: 04dc4021-8cd9-45e7-8339-8f22e29f4be6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4d0ff769c7a8ca297800f427c4ebbae48a8640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-receivelocation-node"></a>EncryptionCert (nodo ReceiveLocation)
El nodo EncryptionCert del nodo ReceiveLocation de un archivo de enlace contiene información acerca del certificado de cifrado usado con una ubicación de recepción que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-encryptioncert-node"></a>Nodos del nodo EncryptionCert  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|LongName|Attribute|xs:string|Especifica el nombre largo del certificado.|No requerido|Valor predeterminado: vacío|  
|nombreCorto|Attribute|xs:string|Especifica el nombre corto del certificado.|No requerido|Valor predeterminado: vacío|  
|UsageType|Attribute|CertUsageType (SimpleType)|Especifica el uso intencionado de este certificado.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx) enumeración.|  
|Huella digital|Attribute|xs:string|Especifica la huella digital o el Id. único del certificado.|No requerido|Valor predeterminado: vacío|