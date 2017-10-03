---
title: "Se encontró ninguna transformación coincidente para DocType en puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc45ac0edf425bc19ab526fac6b2690f3a6b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>No se ha encontrado ninguna transformación coincidente para DocType en Puerto de envío
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|NoMatchingTransformFoundForSendPortAndDocType|  
|Texto del mensaje|Ninguna transformación coincidente que encuentra para DocType {0} en {1} del puerto de envío. Incoherente con la información de ExplorerOM|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que no se encontró ninguna transformación coincidente para un DocType y Puerto de envío.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente:  
  
1.  Abra la consola de administración de BizTalk, localice el transporte y haga clic con el botón secundario en el nombre del transporte.  
  
2.  Haga clic en **Propiedades**.  
  
3.  En la lista Tipo de puerto, seleccione el puerto correcto. Haga clic en **configurar**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de envío de [nombre de puerto], haga clic en **asignaciones de salida** en el panel izquierdo.  
  
5.  Compruebe que aquí aparece la asignación y que corresponde con el tipo de documento correcto.