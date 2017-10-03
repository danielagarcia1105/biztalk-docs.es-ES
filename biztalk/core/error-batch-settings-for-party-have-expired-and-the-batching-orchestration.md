---
title: "La configuración de lotes para la entidad ha caducado y se está finalizando la orquestación por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d56e06766a980c1ce293b211d2956a86c093726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a>La configuración de lotes de la entidad ha caducado y la orquestación de procesamiento por lotes está finalizando
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor de procesamiento por lotes|  
|Nombre simbólico|BatchSettingsExpired|  
|Texto del mensaje|La configuración de lotes de la entidad {0} ha caducado y la orquestación de procesamiento por lotes está finalizando. No se generarán más lotes hasta que se haya habilitado el procesamiento por lotes para esta entidad|  
  
## <a name="explanation"></a>Explicación  
 Esta advertencia indica que la instancia de orquestación por lotes se ha desactivado por haberse alcanzado el final del intervalo de activación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice al procedimiento siguiente para reiniciar el proceso por lotes:  
  
1.  Abra la consola de administración de BizTalk Server y vaya a la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.  
  
2.  Restablecer los criterios de finalización y, a continuación, reinicie la orquestación, haga clic en **iniciar**.  
  
3.  Si la fecha y hora de inicio es anterior a la hora cuando hace clic en **iniciar**, haga clic en **Sí** para actualizar la fecha y hora de inicio a la fecha y hora actual.