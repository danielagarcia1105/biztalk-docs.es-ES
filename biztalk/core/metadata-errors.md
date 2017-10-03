---
title: Errores en los metadatos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-errors"></a>Errores de metadatos
Información para diagnosticar y resolver errores en los metadatos de WCF.  
  
## <a name="error-consuming-wcf-service-metadata"></a>Error al consumir los metadatos del Servicio WCF

||Detalles del error|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Error al consumir los metadatos del Servicio WCF|  
  
### <a name="explanation"></a>Explicación  
 Este error indica que los metadatos para el servicio no están disponibles o que no son válidos.  
  
### <a name="user-action"></a>Acción del usuario  
 Corrija los metadatos del servicio e intente consumirlo (si es propietario del Servicio WCF que está intentando consumir). Vaya al Editor de configuración de servicio (**svcConfigEditor.exe**) y realizar cambios en el archivo de configuración.  En caso contrario, póngase en contacto con el proveedor de servicios

## <a name="failed-to-get-metadata"></a>Error al obtener metadatos

||Detalles del error|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Error al obtener metadatos de "{0}.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que los metadatos no están disponibles para el servicio.  
  
## <a name="user-action"></a>Acción del usuario  
 Habilite los metadatos para el servicio y vuelva a ejecutar el Asistente para consumición (si es propietario del Servicio WCF que intenta consumir). En caso contrario, póngase en contacto con el proveedor de servicios.