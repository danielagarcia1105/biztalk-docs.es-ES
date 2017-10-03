---
title: Usar el TPE | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0fa826ce68042336c2b6e4fb006ecb278a3f981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-tpe"></a>Usar el TPE
El Editor de perfiles de seguimiento (TPE) se utiliza para asignar orquestaciones y propiedades a definiciones de actividad de BAM.  
  
 Los usuarios del TPE crean una asignación, o perfil de seguimiento, entre elementos de una actividad de BAM, como hitos y datos contextuales (a veces llamada "lista de visibilidad") y los orígenes de la solución de BizTalk de estos elementos.  
  
 **Crear un perfil de seguimiento**  
  
 Por ejemplo, considere una actividad de BAM que incluya un hito denominado “Pedido de compra  recibido”. El programador sabe, por haber creado procesos en otras herramientas de programación de BizTalk Server, que el proceso real incluye un puerto de mensajería a través del cual fluyen los pedidos para iniciar el procesamiento. El programador determina que el hito de actividad, llamado “Pedido de compra recibido”, se asocia más correctamente a una propiedad de mensajería de BizTalk llamada “PortEndTime” en el puerto de la solución. El programador realiza ésta y otras asignaciones para completar el perfil de seguimiento cargando la actividad, seleccionando los orígenes de eventos y arrastrando los elementos apropiados desde el origen del evento hasta los nodos correspondientes de la definición del árbol de actividades.  
  
 **Requisitos previos para crear un perfil**  
  
 Existen dos requisitos previos para la creación de un perfil de seguimiento:  
  
1.  Como parte de un modelo de observación general, el analista de negocios crea una actividad de BAM, que posteriormente implementará el administrador del sistema.  
  
2.  Una solución de BizTalk (incluidas las orquestaciones, los esquemas, la asignación y las canalizaciones) se habrá creado correctamente en el entorno de destino.  
  
 Estos requisitos previos son necesarios ya que, tras la instalación, el TPE no se rellena con ningún dato que deba recuperarse de las bases de datos.  
  
 **Crear un perfil para soluciones de BAM personalizadas**  
  
 Los perfiles de seguimiento únicamente son relevantes en los tiempos de ejecución que tienen un interceptor. En el caso de las soluciones de BAM que constan de código personalizado que usa las API de BAM, no hay ningún interceptor de tiempo de ejecución de BAM asociado y el envío de datos a BAM solo puede realizarse de una de las dos maneras siguientes:  
  
-   Directamente a través de las API de BAM: el uso de las API permite a los programadores enviar de forma explícita datos de eventos a la infraestructura de BAM. Para obtener más información sobre el uso de las API de BAM, consulte [implementar actividades de BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md).  
  
-   Indirectamente a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] propiedades. en el caso de que el código personalizado se ejecute dentro de algún contexto de tiempo de ejecución que no tenga una tecnología de interceptación asociada (por ejemplo, una canalización personalizada o formas Expresión o Acción al invocar un ensamblado personalizado), puede usar las API de BAM como se indica arriba o utilizar técnicas de promoción de datos. Cuando las propiedades se promocionan, el TPE puede tener acceso a ellas y se puede crear en el TPE una asociación entre esos datos de eventos y un elemento de actividad de BAM mediante la propiedad de contexto correcta. Para obtener más información acerca de la promoción de propiedades, vea [promocionar propiedades](../core/promoting-properties.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)  
  
-   [Cómo quitar perfiles de seguimiento huérfanos](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [Usar varias continuaciones](../core/using-multiple-continuations.md)