---
title: Cómo ajustar el intervalo de actualización de caché de configuración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9459fadd65af220982ab31ae0e464cb7f1986e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297884"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>Cómo ajustar el intervalo de actualización de caché de configuración
El intervalo de actualización de caché de configuración define el período de tiempo en el que BizTalk Server actualiza la configuración de los puntos de conexión. Cuando se inicia el servidor BizTalk Server, todos los elementos de administración de BizTalk Server, como bases de datos de cuadro de mensajes, propiedades del servidor, adaptadores y conexiones a la base de datos de seguimiento se almacenan en la caché de configuración. Se actualizan todos los elementos de la memoria caché por el intervalo de actualización de configuración. De forma predeterminada, esto es cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor. Esto significa que si cambia las propiedades generales de un grupo de BizTalk, como el host de SMTP, los cambios se recogen en 60 segundos. No se reflejan los cambios realizados fuera de la instancia abierta actualmente de la consola de administración de BizTalk Server en el sistema hasta que los actualice.  
  
 El intervalo de actualización de caché de configuración es parte de las propiedades del grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>Para ajustar el intervalo de actualización de caché  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
3.  En el **panel de configuración de BizTalk** cuadro de diálogo, seleccione la **General** ficha. Para el **intervalo de actualización de configuración** propiedad, escriba o seleccione el tiempo (en segundos) que todos los elementos de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] caché de administración debe esperar entre actualizaciones de la caché de configuración y, a continuación, haga clic en **Aceptar** .  
  
    > [!NOTE]  
    >  Entre los elementos que participan en la actualización se incluyen las bases de datos de cuadro de mensajes, las propiedades del servidor, los adaptadores y las conexiones a la base de datos de seguimiento.  
  
    > [!NOTE]  
    >  De forma predeterminada, todos los objetos en la caché de configuración se actualizarán cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor.