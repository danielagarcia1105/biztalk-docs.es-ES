---
title: "Tiempo no válido en directo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2ddb6de-8c3b-4dee-a984-980e1caea95e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9171fd311a07317c0480e6e4d1ef35742e0e8bcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-time-to-live-timeout"></a>Tiempo de vida no válido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Tiempo de vida no válido. Intervalo válido: 0 a 23 horas, 0 a 59 minutos y 0 a 59 segundos|  
  
## <a name="explanation"></a>Explicación  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el intervalo de tiempo de espera.  
  
#### <a name="to-configure-the-timeout-range"></a>Para configurar el intervalo de tiempo de espera  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** lista, seleccione **WCF-NetMsmq**.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **propiedades de transporte de WCF-NetMsmq** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. En el **configuración de la cola** sección, asegúrese del **tiempo en vivo (SS) del mensaje** intervalo es válido. Los valores aceptados son de 0 a 23 horas, de 0 a 59 minutos y de 0 a 59 segundos.