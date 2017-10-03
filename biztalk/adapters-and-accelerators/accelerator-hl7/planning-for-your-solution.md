---
title: "Planeación de la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Greenfield project
- security, BTAHL7
- BTAHL7, security
- installing, planning
- installing, installation types
- HL7, security
- security, HL7
- Embedded installation
- Migration project
- Coexistence installation
ms.assetid: a108c6d0-dd51-4bf9-85a0-103f60fae971
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73b39dc63621583fc0ecc495d99e9307a2308db6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-your-solution"></a>Planeación de la solución
Esta sección proporciona información sobre lo debe considerar al planear la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] solución.  
  
 Puede implementar BTAHL7 de las maneras siguientes:  
  
-   **Proyecto virgen**. Este escenario es una nueva instalación de BTAHL7.  
  
-   **Proyecto de migración**. Este escenario se produce cuando la organización de atención sanitaria está retirando progresivamente el un agente de integración existente. La organización se migra a BTAHL7.  
  
-   **Coexistencia**. Este escenario implica la instalación de BTAHL7 side-by-side con otro motor de integración.  
  
-   **Embedded**. Este escenario implica la integración de BTAHL7 dentro de una aplicación de línea de negocio. Use BTAHL7 para agregar capacidades de mensajería de HL7 a esa aplicación.  
  
 Usuarios tienden a subestimar la cantidad de trabajo necesario para administrar aplicaciones con el tiempo en comparación con el trabajo necesario para crearlos en primer lugar. Esto es especialmente cierto cuando busca a gran instituciones distribuidas que necesitan para llevar a cabo una matriz de tareas de administración y procesamiento de datos compleja. Un hospital o las organizaciones de entrega de mantenimiento integrada son excelentes ejemplos de tales entidades. Estas entidades enfrentan a la necesidad de proporcionar software para admitir una gran cantidad de funciones, para habilitar la información que se pasará de aplicación a aplicación para evitar la necesidad de entrada de datos duplicados y defectuoso, para proporcionar entrenamiento para los usuarios y los mantenedores de la software y para proporcionar para la sustitución de aplicaciones obsoletas o no está actualizadas por mejorado los. Este proceso de reemplazo tiene sus propios requisitos para las pruebas y educación.  
  
 Sería imposible (muy caro) para que dichas entidades administrar todas sus funciones con una sola integran aplicaciones. En primer lugar, las instituciones no van a asociar su capital a un único proveedor y no encontrará la función all que necesitan a través de un único proveedor. En segundo lugar, las necesidades operativas simples de procesamiento institucional hacer que sea imposible instituciones para que se cumpla con una sola aplicación integrada. Por lo tanto, las instituciones será compatible con sus necesidades con varias aplicaciones. En orden para estas aplicaciones interoperar, las aplicaciones necesitan interfaces para intercambiar información. El número de aplicaciones y las interfaces implicadas suelen ser bastante grande. Dada esta arquitectura de aplicación distribuida, el motor de la interfaz es un instrumento de clave para administrar el procesamiento de datos para las entidades con el tiempo. Los problemas claves son la migración, la asignación y educación. La labor de BTAHL7 consiste en resolver estos problemas lo más fácil y eficaz como sea posible:  
  
-   **Asignación**. El trabajo más importante en la implementación de interfaz consiste en crear la asignación entre las estructuras de base de datos/aplicación y las estructuras de datos utilizadas en la interfaz. Todo lo que hace la herramienta para convertir esta sencilla y natural es bueno. Además, puesto que el documento de asignación se convertirá en una especificación de utilizada por los desarrolladores de interfaz y la aplicación, es importante ser capaz de generar fácilmente la documentación del mismo. Utilice el Explorador de configuración de BTAHL7, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] herramientas para desarrollar e implementar estas asignaciones.  
  
-   **Migración**. Debe mantener interoperabilidad entre las aplicaciones con el tiempo, como las aplicaciones cambian. Si considera que los problemas relacionados con el reemplazo de una sola aplicación, es la necesidad de actualizar las asignaciones de origen de datos a las interfaces es aplicable. Con un motor de interfaz debería haber solo una de ellas. Debe considerar que se han instalado interfaces y si los estándares de interfaz cambian con el tiempo. Verás que con el tiempo estándares de interfaz de cambiarán y tienen que migrarse a los estándares frecuentes. Se recomienda que el plan de migración tener en cuenta los cambios futuros de interfaz. Debe asignar entre los estándares y entre las distintas versiones del estándar. Además, dentro de los límites de un único estándar, especialmente una flexible como HL7 V2, tiene que tratar con (en muchas aplicaciones) varias implementaciones del mismo estándar. El motor de interfaz debe tratar esta complejidad de tal manera que es fácil de administrar.  
  
     Una tarea de migración de la clave es que la migración de un cuerpo de interfaces de un estándar a otro. Aquí está la tarea migrar todas las asignaciones que usan la versión anterior al nuevo: llevar a cabo en localización concreta de la interfaz de cuenta y las extensiones, que puede ser un proceso complicado. La herramienta debe proporcionar asistencia con esta migración.  
  
     Use la pestaña de validación de explorador de configuración de BTAHL7 para especificar el espacio de nombres de un los esquemas de tipo de mensaje adicional.  
  
-   **Educación**. Las personas implicadas con la administración y compatibles con aplicaciones cambiará con el tiempo. Además, puesto que las interfaces son esenciales para las características de interoperabilidad de la colección de aplicaciones, se procederá su documentación clave herramientas de administración de toda la empresa. Por tanto estas razones, es útil para proporcionar fácil de usar y fácil de mantener documentación de a) las especificaciones de interfaz, b) la aplicación y introversion las asignaciones y c) el razonamiento de las actividades de personalización y localización.  
  
## <a name="see-also"></a>Vea también  
[Obtenga información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)