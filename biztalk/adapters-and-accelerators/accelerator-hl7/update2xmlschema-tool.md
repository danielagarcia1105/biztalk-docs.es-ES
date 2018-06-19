---
title: Herramienta de Update2XMLSchema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0f5a33b8951d1f02cf0504ba833b35adf275834
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961114"
---
# <a name="update2xmlschema-tool"></a>Herramienta Update2XMLSchema
La herramienta Update2XMLSchema le permite modificar los esquemas XML de HL7 2. para trabajar con el Editor de BizTalk. Esto es necesario porque algunos esquemas XML de 2. HL7 no funcionan correctamente en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin ninguna modificación. Después de modificar los esquemas, la herramienta coloca en la carpeta esquemas donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] está instalado, por ejemplo,  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7\Templates\Schemas.  
  
 Debe actualizar manualmente algunos campos de los esquemas que son el resultado de ejecutar la herramienta Update2XMLSchema. Vea [requiere actualizaciones manuales](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) para obtener una lista de los esquemas.  
  
## <a name="syntax"></a>Sintaxis  
 Esta herramienta se encuentra en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7\SDK\2XML utilidades. Ejecute esta herramienta en el símbolo del sistema con el comando siguiente:  
  
```  
Update2XMLSchema /s /v  
```  
  
 En la tabla siguiente se enumera los parámetros para usar con este comando.  
  
|Parámetro|Nombre|Valor|  
|---------------|----------|-----------|  
|*S*|Source|Ruta de acceso completa de los esquemas de HL7 originales|  
|*V*|Versión|La versión de los esquemas XML de 2.: 2.3.1, 2.4 o 2.5|  
  
## <a name="example"></a>Ejemplo  
  
-   Si desea modificar esquemas XML versión 2.3.1 2. que encuentra en el directorio c:\231XML\v231\xsd, escribiría el comando siguiente en el símbolo del sistema:  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Actualizaciones manuales obligatorias](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)