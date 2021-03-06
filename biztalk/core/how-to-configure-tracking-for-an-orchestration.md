---
title: Cómo configurar el seguimiento de una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, tracking
- orchestrations, HAT
- managing [orchestrations], tracking
- configuring [HAT tracking], orchestrations
- tracking, orchestrations
- HAT, orchestrations
ms.assetid: 8f5ed525-11f8-4bef-95c4-cfe9c971b663
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c64d7521bf6d65458f66bb0ef06d08421edf1b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013197"
---
# <a name="how-to-configure-tracking-for-an-orchestration"></a>Cómo configurar el seguimiento para una orquestación
Este tema explica cómo usar la consola de administración de BizTalk Server para configurar el seguimiento para una orquestación.  
  
 Para obtener más información sobre la creación y uso de consultas, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md). Para obtener más información acerca de las características de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Ver mensaje realiza el seguimiento y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-an-orchestration"></a>Para configurar el seguimiento para una orquestación  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que desea configurar el seguimiento.  
  
3. Haga clic en **orquestaciones**, haga clic en la orquestación que desea configurar el seguimiento y, a continuación, haga clic en **propiedades**.  
  
4. Haga clic en el **seguimiento** , seleccione las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Opción|Descripción|  
   |------------|-----------------|  
   |**Seguimiento de eventos - inicio de la orquestación y de finalización**|Activar esta casilla de verificación para realizar un seguimiento de la instancia de orquestación antes y después del procesamiento del proceso empresarial completo. La orquestación del seguimiento permite ver las instancias en las vistas de los resultados de la consulta de seguimiento.|  
   |**Seguimiento de eventos - envío y recepción de mensajes**|Active esta casilla de verificación para realizar un seguimiento de los eventos de envío y recepción de mensajes. Esta casilla solo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
   |**Seguimiento de eventos - forma Inicio y finalización**|Active esta casilla de verificación si necesita depurar instancias de orquestación en el Depurador de orquestaciones. Al activar esta casilla, se llena la lista de eventos del Depurador de orquestaciones. Esta casilla solo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
   |**Seguimiento de partes de mensaje – antes del procesamiento de orquestación**|Active esta casilla de verificación para guardar y realizar un seguimiento del contenido real de los mensajes antes de que los procese la instancia de orquestación. Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  
   |**Realizar un seguimiento de cuerpos de mensaje - después del procesamiento de orquestación**|Active esta casilla de verificación para guardar y realizar un seguimiento del contenido real de los mensajes después de que los procese la instancia de orquestación. Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  
   |**Seguimiento de propiedades de mensaje - mensajes entrantes**|Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje entrante.|  
   |**Seguimiento de propiedades de mensaje - mensajes salientes**|Activar esta casilla para realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)