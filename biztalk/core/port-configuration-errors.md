---
title: Errores de configuración de puerto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f0e51c06fab9dadb60fc43a003108e50bbb0fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264196"
---
# <a name="port-configuration-errors"></a>Errores de configuración de puerto
Información para diagnosticar y resolver errores de configuración de puerto de WCF.  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a>No se puede combinar la operación debido a un conflicto de patrón de comunicación
  
||Detalles|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede combinar la operación "{0}". Conflicto de patrón de comunicación.  Todas las operaciones deben ser unidireccionales o de solicitud-respuesta.|  
  
### <a name="explanation"></a>Explicación  
 Este error indica que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta combinar puertos con tipos de puertos que tienen patrones de comunicación diferentes.  
  
### <a name="user-action"></a>Acción del usuario  
 Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen la misma dirección de comunicación, unidireccional o de solicitud-respuesta.  
  
 Para obtener más información sobre la configuración del puerto, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a>No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta 
  
||Detalles|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta. Corrija el tipo de puerto de servicio descripción "{0}" "{{1}" y vuelva a ejecutar el Asistente|  
  
### <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se intenta consumir tiene operaciones que son unidireccionales y bidireccionales (solicitud-respuesta).  
  
### <a name="user-action"></a>Acción del usuario  
 Corrija el servicio con las operaciones adecuadas (unidireccionales o de solicitud-respuesta, pero no ambas) e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir). En caso contrario, póngase en contacto con el proveedor de servicios.
