---
title: Cómo ajustar el intervalo de actualización de caché de configuración | Microsoft Docs
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
ms.openlocfilehash: a861b6a4b4bc3f60dc2d3a50cb1c27d47e07b46a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985661"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>Cómo ajustar el intervalo de actualización de caché de configuración
El intervalo de actualización de caché de configuración define el período de tiempo en la que BizTalk Server actualiza la configuración de los puntos de conexión. Cuando se inicia el servidor BizTalk Server, todos los elementos de administración de BizTalk Server, como las bases de datos, las propiedades del servidor, adaptadores y las conexiones a la base de datos de seguimiento, cuadro de mensajes se almacenan en la caché de configuración. Se actualizan todos los elementos de la memoria caché por el intervalo de actualización de configuración. De forma predeterminada, esto es cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor. Esto significa que si cambia las propiedades generales de un grupo de BizTalk, como el host SMTP, los cambios se recogen en 60 segundos. No se reflejan los cambios del sistema realizados fuera de la instancia de la consola de administración de BizTalk Server abierta hasta que la actualice.  
  
 El intervalo de actualización de caché de configuración forma parte de las propiedades del grupo de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>Para ajustar el intervalo de actualización de caché  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **configuración**.  
  
3. En el **panel de configuración de BizTalk** cuadro de diálogo, seleccione el **General** ficha. Para el **intervalo de actualización de configuración** propiedad, escriba o seleccione el tiempo (en segundos) que todos los elementos de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] caché de administración debe esperar entre actualizaciones de la memoria caché de configuración y, a continuación, haga clic en **Aceptar** .  
  
   > [!NOTE]  
   >  Entre los elementos que participan en la actualización se incluyen las bases de datos de cuadro de mensajes, las propiedades del servidor, los adaptadores y las conexiones a la base de datos de seguimiento.  
  
   > [!NOTE]  
   >  De forma predeterminada, todos los objetos de la caché de configuración se actualizan cada 60 segundos, excepto para las conexiones de base de datos de servidor y las propiedades del servidor.