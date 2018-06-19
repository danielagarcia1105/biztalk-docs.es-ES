---
title: Para habilitar los informes de estado, ejecutar &#39; Configuración de BizTalk Server &#39; y configurar la característica de informes de estado de EDI y AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334e77ed58d460aea3ca37f73c1165d62da0f10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268916"
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a>Para habilitar los informes de estado, ejecutar &#39; Configuración de BizTalk Server &#39; y configurar la característica de informes de estado de EDI y AS2
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|0|  
|Texto del mensaje|Para habilitar los informes de estado, ejecute 'Configuración de BizTalk Server' y configure la característica de informes de estado de EDI/AS2.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que no funciona la generación de informes de estado de EDI/AS2 porque no se ha configurado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
1.  Ejecute el Asistente para configuración de BizTalk Server. Haga clic en el nodo Tiempo de ejecución de EDI y AS2 de BizTalk y active la propiedad "Habilitar informes de estado de tiempo de ejecución de EDI y AS2 de BizTalk para este grupo de BizTalk". Debe configurar BAM para configurar los informes de estado de EDI/AS2.  
  
2.  En la consola de administración de BizTalk Server, habilite los informes de estado de EDI para la entidad al hacer clic en la propiedad "Activar informes de EDI" de la página General del cuadro de diálogo Propiedades de EDI. Habilite los informes de estado de AS2 para la entidad al hacer clic en la propiedad "Activar informes de AS2" de la página General del cuadro de diálogo Propiedades de AS2. Debe reiniciar el servicio de BizTalk después de habilitar los informes de estado de EDI o AS2.