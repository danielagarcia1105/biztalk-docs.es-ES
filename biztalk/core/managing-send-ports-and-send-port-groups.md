---
title: "Administrar puertos de envío y grupos de puertos de envío | Documentos de Microsoft"
description: "Vínculos para crear, configurar, dar de alta, dar de baja e iniciar y detener puertos de envío de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928160ed5b67602c8fc8d9d646459bf2425d7a01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-send-ports-and-send-port-groups"></a>Administrar puertos de envío y grupos de puertos de envío

## <a name="overview"></a>Información general
En esta sección se proporcionan instrucciones acerca del uso de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para crear, configurar y administrar puertos de envío y grupos de puertos de envío en una aplicación de BizTalk. Un puerto de envío especifica la ubicación a la que se envían los mensajes y, de forma opcional, confirma su recepción. Siempre que se envía un mensaje a un puerto de envío, se crea una nueva instancia del servicio de puerto de envío, que se denomina un *instancia del servicio*.  
  
 Un grupo de puertos de envío es una agrupación lógica de puertos de envío. Cuando un mensaje se envía a un grupo de puertos de envío, se dirige a todos los puertos de envío asociados.  Para obtener información general sobre los puertos de envío y grupos de puertos de envío, consulte [puertos de envío y grupos de puertos de envío](../core/send-ports-and-send-port-groups.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
> [!NOTE]
>  Al desarrollar una aplicación de BizTalk, el programador puede utilizar herramientas de diseño de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], por ejemplo, el Diseñador de orquestaciones, para crear y configurar puertos de envío y grupos de puertos de envío. Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)  
  
-   [Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)  
  
-   [Dar de alta un puerto de envío o grupo de puertos de envío](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [Dar de baja un puerto de envío o grupo de puertos de envío](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [Iniciar un puerto de envío o un grupo de puertos de envío](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [Detener un puerto de envío o un grupo de puertos de envío](../core/how-to-stop-a-send-port-or-send-port-group.md)