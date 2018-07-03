---
title: Herramienta Update2XMLSchema | Microsoft Docs
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
ms.openlocfilehash: 108bc63536e84dd18cd738fbc6ec10d1e07c404b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978141"
---
# <a name="update2xmlschema-tool"></a>Herramienta Update2XMLSchema
La herramienta Update2XMLSchema permite modificar esquemas de HL7 2.XML para trabajar con el Editor de BizTalk. Esto es necesario porque algunos esquemas de HL7 2.XML no funcionan correctamente en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin ninguna modificación. Después de modificar los esquemas, la herramienta coloca en la carpeta esquemas donde [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] está instalado, por ejemplo,  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\Templates\Schemas.  
  
 Deberá actualizar manualmente algunos campos de los esquemas de ese resultado de ejecutar la herramienta Update2XMLSchema. Consulte [requiere actualizaciones manuales](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) para obtener una lista de esos esquemas.  
  
## <a name="syntax"></a>Sintaxis  
 Esta herramienta se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\2XML utilidades. Ejecute esta herramienta en el símbolo del sistema con el siguiente comando:  
  
```  
Update2XMLSchema /s /v  
```  
  
 En la tabla siguiente se enumera los parámetros para usar con este comando.  
  
|Parámetro|Nombre|Valor|  
|---------------|----------|-----------|  
|*S*|Source|Ruta de acceso completa de los esquemas de HL7 originales|  
|*V*|Versión|La versión de los esquemas 2.XML: 2.3.1, 2.4 o 2.5|  
  
## <a name="example"></a>Ejemplo  
  
-   Si desea modificar la versión 2.3.1 esquemas 2.XML ubicados en el directorio c:\231XML\v231\xsd, escribiría el comando siguiente en el símbolo del sistema:  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Actualizaciones manuales obligatorias](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)