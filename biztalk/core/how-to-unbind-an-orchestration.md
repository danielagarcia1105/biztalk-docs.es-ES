---
title: "Separar una orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b8adc77e5e8579339931e49abb501f9981e5fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="unbind-an-orchestration"></a>Separar una orquestación

## <a name="overview"></a>Información general
En este tema se describen cómo utilizar la consola de administración de BizTalk Server para quitar enlaces de host, puerto de envío y puerto de recepción de una orquestación.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede quitar enlaces de una orquestación mediante el procedimiento de este tema. También puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="remove-bindings-from-an-orchestration"></a>Quitar enlaces de una orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación desde el que va a quitar enlaces  
  
3.  Haga clic en **orquestaciones**, haga clic en la orquestación, haga clic en **propiedades**y, a continuación, haga clic en **enlaces** en el panel izquierdo.  
  
4.  Para quitar los enlaces de host, de la **Hosts** lista, seleccione  **\<ninguno\>**.  
  
5.  Para quitar enlaces de puertos de recepción en la lista desplegable de **puertos de recepción**, haga clic en  **\<ninguno\>**.  
  
6.  Para quitar enlaces de puertos de envío, en la lista desplegable de **grupos de puertos de envío y puertos de envío**, haga clic en  **\<ninguno\>**.  
  
7.  Cuando termine de quitar los enlaces, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md)   
 [Implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)