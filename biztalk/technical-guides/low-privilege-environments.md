---
title: Entornos con pocos privilegios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d43f363bd96dd8e3109a8ce21b9565fb43e5f9bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298300"
---
# <a name="low-privilege-environments"></a>Entornos con pocos privilegios
Varios flujos de trabajo que se incluyen con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración requiere permisos elevados para realizar determinadas acciones. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Módulo de administración le permite realizar funciones básicas de supervisión en un entorno con pocos privilegios. Hay dos funciones administrativas: el Administrador de BizTalk Server y el operador de BizTalk Server. El Administrador de BizTalk Server tiene una función de muchos privilegios, con acceso a los datos de configuración y de seguimiento. El Administrador de BizTalk Server puede realizar todas las tareas administrativas claves tales dar de alta e iniciar los artefactos. El Operador de BizTalk Server tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones. Para obtener más información, consulte [derechos de usuario mínimos de seguridad](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).  
  
 Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración:  
  
-   Los miembros del grupo de operadores de BizTalk Server pueden realizar las siguientes acciones:  
  
    -   Supervisar BizTalk Server para errores, realizar consultas para detectar suspendido, configuración de la vista.  
  
    -   Supervisar las instalaciones de BizTalk Server y los artefactos.  
  
    -   Ver el estado del servicio y el flujo de mensajes.  
  
    -   Iniciar o detener aplicaciones y artefactos, como orquestaciones, puertos de envío o grupos de puertos que se encuentran en un estado dada de alta.  
  
    -   Habilitar o deshabilitar ubicaciones de recepción. Los cambios no se hacen efectivos hasta el próximo intervalo de actualización de la caché de 60 segundos, que es el intervalo predeterminado. El intervalo de actualización de la caché se establece en el nivel de grupo de BizTalk Server.  
  
-   Los miembros del grupo de operadores de BizTalk Server no pueden realizar las siguientes acciones:  
  
    -   Modificar la configuración de BizTalk Server.  
  
    -   Ver las propiedades de contexto del mensaje que estén clasificadas como información que se pueda identificar personalmente o los cuerpos de los mensajes.  
  
    -   Modificar el transcurso del enrutamiento de mensajes, como la eliminación de suscripciones del sistema en ejecución o la agregación de suscripciones nuevas a éste, así como la capacidad para publicar mensajes en el tiempo de ejecución de BizTalk Server.  
  
> [!NOTE]  
>  Para llevar a cabo todas las tareas de supervisión proporcionadas por el módulo de administración, como reiniciar el servicio BTSNTSvc.exe, debe ser miembro del grupo Administradores local en los servidores BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Supervisión](../technical-guides/monitoring.md)  
  
-   [Detecciones](../technical-guides/discoveries.md)