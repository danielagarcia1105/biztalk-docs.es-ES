---
title: "Puertos de envío y grupos de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, states
- send port groups
- send port groups, states
- send ports, about send ports
- send ports
- send port groups, about send port groups
- states, send ports
ms.assetid: 274bdd27-9098-46a2-8762-8b57bbfc95b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57e56d05cf3b1a98bba83d0df92d52f09c6eda5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-ports-and-send-port-groups"></a>Puertos de envío y grupos de puertos de envío
A *puerto de envío* es la ubicación a la que Microsoft BizTalk Server envía mensajes o desde la que BizTalk Server recibe mensajes. Asimismo proporciona la tecnología que utiliza BizTalk Server para implementar la acción de comunicación. El nombre del puerto identifica la ubicación de forma exclusiva.  
  
 Cada vez que se envía un mensaje a un puerto de envío, se crea una nueva instancia de un servicio de puerto de envío. Esto se denomina instancia de servicio o instancia de puerto de envío.  
  
> [!NOTE]
>  solo puede haber una instancia de un puerto de envío con entrega por orden.  
  
 A *grupo de puertos de envío* es una colección con nombre de puertos de envío que BizTalk Server puede usar para enviar el mismo mensaje a varios destinos con una sola configuración.  
  
 BizTalk Server puede enrutar mensajes directamente desde ubicaciones de recepción a un puerto de envío o grupo de puertos de envío. BizTalk Server envía los mensajes enrutados a un grupo de puertos de envío a todos los puertos de envío de ese grupo.  
  
 Los puertos de envío que pertenecen a un grupo de puertos de envío procesan los mensajes de dos formas:  
  
-   Como miembro del grupo de puertos de envío  
  
-   Como si BizTalk Server enrutara los mensajes al puerto de envío directamente  
  
## <a name="send-port-and-send-port-group-states"></a>Estados de puertos de envío y de grupos de puertos de envío  
 La consola de administración de BizTalk se muestran los puertos de envío y grupos de puertos de envío en uno de los siguientes estados:  
  
-   **Enlazado**. Usando la consola de administración de BizTalk Server, un administrador enlaza el puerto de envío o el grupo de puertos de envío con una orquestación. Antes de que BizTalk Server enrute mensajes a este puerto de envío o grupo de puertos de envío, el administrador dar de alta e iniciar el puerto de envío o grupo de puertos de envío enlazados.  
  
-   **Iniciar**. La suscripción para este puerto de envío o grupo de puertos de envío existe y está activa. Cuando el puerto de envío o grupo de puertos de envío está en estado iniciado, BizTalk Server entrega mensajes al puerto de envío o grupo de puertos de envío, y estos los procesan. Para poder iniciar un puerto de envío o grupo de puertos de envío, un administrador debe utilizar la consola de administración de BizTalk para dar de alta al puerto de envío o grupo de puertos de envío enlazados.  
  
-   **Detenido**. El puerto de envío o grupo de puertos de envío no se está ejecutando. Si inició el puerto de envío o grupo de puertos de envío y luego lo detuvo, el procesamiento continúa en la cola de trabajo. BizTalk Server envía todos los mensajes nuevos enrutados a un puerto de envío o grupo de puertos de envío detenido a la cola de suspensión del host donde se está ejecutando el controlador de envío.  
  
 En la tabla siguiente se muestran las acciones disponibles en cada estado y el resultado de cada una.  
  
||Enlazado|Detenido|Iniciado|  
|------|-----------|-------------|-------------|  
|**Dar de alta**|Detenido|No disponible|No disponible|  
|**Iniciar**|Iniciado|Iniciado|No disponible|  
|**Detener**|No disponible|No disponible|Detenido|  
|**Dar de baja**|No disponible|Enlazado|Enlazado|  
  
 El estado combinado de un puerto de envío y del grupo de puertos de envío al que pertenece determina si el puerto de envío o grupo de puertos de envío procesa o no un mensaje.  
  
 En la tabla siguiente se describen todas las combinaciones posibles de estados para puertos de envío y grupos de puertos de envío.  
  
|Mensaje enviado|Estado del grupo de puertos de envío|Estado del puerto de envío|Resultado|  
|------------------|------------------------------|------------------------|-------------|  
|Directamente al puerto de envío|Cualquier estado|Iniciado|El mensaje se procesa|  
|Directamente al puerto de envío|Cualquier estado|Detenido|El mensaje se suspende|  
|Al puerto de envío mediante un grupo de puertos de envío|Iniciado|Iniciado|El mensaje se procesa|  
|Al puerto de envío mediante un grupo de puertos de envío|Cualquier estado|Detenido|El mensaje se suspende|  
|Al puerto de envío mediante un grupo de puertos de envío|Detenido|Cualquier estado|El mensaje se suspende|  
  
## <a name="see-also"></a>Vea también  
 [Artefactos](../core/artifacts.md)