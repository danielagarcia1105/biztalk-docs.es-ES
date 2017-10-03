---
title: "Configurar enlaces para una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb695f9636327107887397372d5fc2dda74e4eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a>Cómo configurar enlaces para una orquestación

## <a name="overview"></a>Información general
Este tema explica cómo usar la consola de administración de BizTalk Server para configurar enlaces para una orquestación. Esto conlleva enlazar los puertos lógicos definidos para la orquestación a los puertos físicos en el entorno de ensayo o de producción, así como enlazar la orquestación a un host. Si ya se ha enlazado la orquestación, es posible cambiar los enlaces mediante este procedimiento.  
  
 Después de configurar los enlaces, se puede dar de alta la orquestación e iniciarla para que comience a procesar mensajes. Para obtener instrucciones acerca de cómo realizar estas tareas, consulte [cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) y [cómo iniciar una orquestación](../core/how-to-start-an-orchestration.md).  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede configurar enlaces para una orquestación para probar su funcionalidad durante el proceso de desarrollo mediante el procedimiento de este tema. También puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="configure-bindings-for-an-orchestration"></a>Configurar enlaces para una orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que va a configurar los enlaces  
  
3.  Haga clic en **orquestaciones**, haga clic en la orquestación para la que desea configurar los enlaces y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **enlaces** ficha y desde el **Host** lista, seleccione el host en el que se va a dar de alta una orquestación.  
  
5.  En la lista desplegable se enumeran en la **puertos de recepción** columna, junto a cada puerto lógico de entrada, seleccione el puerto de recepción al que desea enlazar el puerto lógico.  
  
6.  En la lista desplegable de la **grupos de puertos de envío y puertos de envío** columna, junto a cada puerto lógico de entrada, seleccione el puerto de envío a la que desea enlazar el puerto lógico y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Cómo separar una orquestación](../core/how-to-unbind-an-orchestration.md)   
 [Implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)