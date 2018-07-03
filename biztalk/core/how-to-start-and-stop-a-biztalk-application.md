---
title: Cómo iniciar y detener una aplicación de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting
- starting, applications
- managing [applications], starting
- managing [applications], stopping
- applications, starting
- stopping, applications
- applications, stopping
- stopping
ms.assetid: f9f83e99-a1e2-4dfd-b3be-60d3ec2cbcc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979de8e8614d05ba97223e43c90ed0ec83cefc4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968733"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a>Cómo iniciar y detener una aplicación de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server para iniciar y detener una aplicación de BizTalk.  
  
 Antes de que puede iniciar una aplicación, los enlaces deben configurarse para todas las orquestaciones que contenga, como se describe en [cómo configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md).  
  
 Al iniciar una aplicación, puede seleccionar una o varias de las siguientes opciones:  
  
-   Dar de alta e iniciar todas las orquestaciones  
  
-   Dar de alta e iniciar todos los puertos de envío  
  
-   Dar de alta e iniciar todos los grupos de puertos de envío  
  
-   Habilitar todas las ubicaciones de recepción  
  
-   Iniciar todas las instancias de host asociadas  
  
-   Reanudar instancias suspendidas  
  
-   Implementar todas las directivas.  
  
> [!NOTE]
>  Solo las directivas publicadas en la aplicación se implementan de forma automática. Si una directiva no está publicada, no se implementará.  
  
 Al detener una aplicación, puede seleccionar una de las siguientes opciones:  
  
-   **Parcial Stop: permitir que continúen las instancias en ejecución.** esta opción deshabilita todas las ubicaciones de recepción en la aplicación, pero deja los demás artefactos con el estado anterior. Esto permite a las instancias en ejecución completar el procesamiento de los mensajes que hay actualmente en el sistema. Si usa esta opción, tenga en cuenta que es posible que las transacciones de mensajes que requieren varias entradas no puedan completarse.  
  
-   **Parcial Stop: suspender las instancias en ejecución.** esta opción deshabilita todas las ubicaciones de recepción y detiene todas las orquestaciones y puertos de envío en la aplicación. No da de baja ningún artefacto ni anula su implementación. Use esta opción si desea pausar temporalmente la aplicación.  
  
-   **Detención completa: finalizar instancias.** esta opción deshabilita todas las ubicaciones de recepción, detiene y da de baja todas las orquestaciones y puertos de envío, y anula la implementación de todas las directivas en la aplicación. Use esta opción si desea anular por completo la implementación de una aplicación. Tenga en cuenta que no se completará el procesamiento de los mensajes en curso de cualquier instancia en ejecución. Para obtener más información, consulte [anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Los operadores de BizTalk pueden realizar una detención parcial, pero no una completa. Además, pueden iniciar una aplicación si todos los artefactos están dados de alta. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-start-or-stop-a-biztalk-application"></a>Para iniciar o detener una aplicación de BizTalk  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, expanda **aplicaciones**.  
  
3. Haga clic en la aplicación de BizTalk que desea iniciar o detener y, a continuación, haga clic en **iniciar** o **detener**.  
  
4. Seleccione el inicio o detención opciones que desee y haga clic en **iniciar** o **detener**.  
  
## <a name="see-also"></a>Vea también  
 [Implementación y administración de aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)   
 [Actualización de aplicaciones de BizTalk](../core/updating-biztalk-applications.md)