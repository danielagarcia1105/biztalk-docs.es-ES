---
title: Servidor Web en el puerto de host no se encuentra | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dce09ce00a169ad14bbc8ae2ab28fe70c039c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="web-server-on-host-port-not-found"></a>No se encontró el servidor web en el puerto de host
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Servidor Web en {1} de puerto de host "{0}" no encontrado|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio World Wide Web (WWW) no se ejecuta.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para iniciar el servicio World Wide Web.  
  
#### <a name="to-start-the-world-wide-web-service"></a>Para iniciar el servicio World Wide Web  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**, haga doble clic en **herramientas administrativas**y haga doble clic en **servicios.**  
  
2.  En la columna nombre, busque **publicación World Wide Web**. Asegúrese de que el estado es **iniciado**.  
  
3.  Vuelva a la **herramientas administrativas** ventana. Haga doble clic en **servicios de Internet Information Server**.  
  
4.  Expanda el área de la carpeta y localice el sitio web.  
  
5.  Asegúrese de que el estado es **iniciado**.