---
title: Separar una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5673101934c4ba35deb4d63839c23e3d9cda7e4b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992629"
---
# <a name="unbind-an-orchestration"></a>Separar una orquestación

## <a name="overview"></a>Información general
En este tema se describen cómo utilizar la consola de administración de BizTalk Server para quitar enlaces de host, puerto de envío y puerto de recepción de una orquestación.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede quitar enlaces de una orquestación mediante el procedimiento de este tema. También puede utilizar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="remove-bindings-from-an-orchestration"></a>Quitar enlaces de una orquestación  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación desde el que desea quitar enlaces  
  
3. Haga clic en **orquestaciones**, haga clic en la orquestación, haga clic en **propiedades**y, a continuación, haga clic en **enlaces** en el panel izquierdo.  
  
4. Para quitar los enlaces de host de la **Hosts** lista, seleccione  **\<ninguno\>**.  
  
5. Para quitar enlaces de puerto de recepción en la lista desplegable **puertos de recepción**, haga clic en  **\<ninguno\>**.  
  
6. Para quitar los enlaces de puerto de envío, en la lista desplegable **grupos de puertos de envío y puertos de envío**, haga clic en  **\<ninguno\>**.  
  
7. Cuando termine de quitar los enlaces, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)   
 [Cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md)   
 [Implementación y administración de aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)