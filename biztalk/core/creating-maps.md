---
title: Creación de mapas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e27f4fae142f4c781f95be148ec80e2dff51383
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003101"
---
# <a name="creating-maps"></a>Crear asignaciones
Se muestra la interfaz de usuario principal del asignador de BizTalk en una pestaña en el [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de edición. Esta presentación se divide en tres paneles distintos. El panel de la izquierda muestra el esquema de origen como un árbol. El panel de la derecha muestra el esquema de destino como un árbol. El panel central muestra la cuadrícula como varias páginas. Para indicar cómo desea asignar los datos del esquema de origen al de destino, dibuje líneas entre los registros y los campos que desea asignar. Estas líneas se llaman *vínculos*, y son la manera más sencilla para especificar la asignación de datos. Para obtener más información sobre cómo vincular registros y campos, consulte [vínculos en asignaciones](../core/links-in-maps.md).  
  
 Si desea implementar métodos de asignación más avanzados, puede usar los functoids. Los functoids son herramientas disponibles en las pestañas del Asignador de BizTalk en el cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Permiten crear asignaciones para llevar a cabo operaciones más complejas, como por ejemplo:  
  
- Sumar los valores de dos campos del esquema de origen y colocar el resultado en un campo del esquema de destino.  
  
- Calcular el valor medio de un campo en un registro de bucle y poner los resultados en un campo en el esquema de destino.  
  
- Escribir una secuencia de comandos personalizada para manipular datos de la instancia según convenga a las necesidades de su negocio.  
  
  Para obtener más información acerca de functoids, consulte [Functoids en asignaciones](../core/functoids-in-maps.md).  
  
  El Asignador de BizTalk admite muchos escenarios de asignaciones diferentes, desde simples relaciones primario-secundario hasta bucles complejos y detallados de registros y jerarquías. Al crear asignaciones, tenga en cuenta lo siguiente:  
  
- El Asignador de BizTalk no admite combinar y ordenar.  
  
- Si las estructuras de esquema de origen y de destino son totalmente diferentes, es posible que la transformación no se pueda llevar a cabo en una sola asignación. Tal vez deba realizar un doble proceso.  
  
- **Bucle** functoids son flexibles y eficaces, pero no podrá interrumpir la iteración cuando se detecta un cambio de valor en el esquema de origen para iniciar la siguiente iteración del bucle de destino.  
  
- Puede declarar una variable fuera del método en un **Scripting** functoid, lo que resulta en la variable esté en el ámbito de la vida de la asignación. Por lo tanto, puede usar el **Scripting** functoid para alojar valores entre las áreas de ámbito de la transformación.  
  
  Todos los datos procesados por [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución debe estar en formato XML. Antes de asignarse, todos los datos que no sean XML deben traducirse a un formato equivalente a XML. De forma similar, cuando está completado, el proceso de asignación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la salida de una operación de asignación para crear un formato de archivo que es reconocido por el socio comercial o la aplicación a la que se envían los datos.  
  
  El Asignador de BizTalk incluye un compilador. Este componente a nivel de herramientas genera la Transformación de lenguaje de hojas de estilo extensible (XSLT) necesaria para transformar o traducir mensajes de instancia de salida.  
  
  Esta sección proporciona información específica de la tarea acerca de la utilización del Asignador de BizTalk para crear la asignación entre dos esquemas. Se supone que ya tiene abierto el Asignador de BizTalk y que ha elegido sus esquemas de origen y de destino.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administración de asignaciones en proyectos](../core/managing-maps-within-projects.md)  
  
-   [Uso de vínculos para especificar asignaciones de registros y campos](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [Uso de functoids para crear asignaciones más complejas](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [Cómo crear una asignación sin asignaciones](../core/how-to-create-a-map-without-maps.md)  
  
-   [Administrar el comportamiento de asignador predeterminado mediante \<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)