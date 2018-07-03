---
title: Servidor Web en el puerto de host no encontrado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987149"
---
# <a name="web-server-on-host-port-not-found"></a>No se encontró el servidor web en el puerto de host
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                    Servidor Web en el host "{0}" puerto {1} no encontrado                     |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio World Wide Web (WWW) no se ejecuta.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para iniciar el servicio World Wide Web.  
  
#### <a name="to-start-the-world-wide-web-service"></a>Para iniciar el servicio World Wide Web  
  
1.  Haga clic en **iniciar**, haga clic en **Panel de Control**, haga doble clic en **herramientas administrativas**y haga doble clic en **servicios.**  
  
2.  En la columna nombre, busque **publicación World Wide Web**. Asegúrese de que el estado es **iniciado**.  
  
3.  Vuelva a la **herramientas administrativas** ventana. Haga doble clic en **Internet Information Services**.  
  
4.  Expanda el área de la carpeta y localice el sitio web.  
  
5.  Asegúrese de que el estado es **iniciado**.