---
title: Planificación de la solución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20e41137d8e300453d3dc4eba7fee6e9dd6ecc0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977277"
---
# <a name="planning-for-your-solution"></a>Planificación de la solución
Esta sección proporciona información sobre lo debe considerar al planear su Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] solución.  
  
 Puede implementar BTAHL7 de las maneras siguientes:  
  
- **Proyecto virgen**. Este escenario es una nueva instalación de BTAHL7.  
  
- **Proyecto de migración**. Este escenario se produce cuando un agente de integración existente se retirará la organización de atención médica. La organización se migra a BTAHL7.  
  
- **Coexistencia**. Este escenario implica una instalación de BTAHL7 side-by-side con otro motor de integración.  
  
- **Embedded**. Este escenario implica la integración de BTAHL7 dentro de una aplicación de línea de negocio. Use BTAHL7 para agregar capacidades de mensajería de HL7 a esa aplicación.  
  
  Las personas tienden a subestimar la cantidad de esfuerzo necesario para administrar aplicaciones con el tiempo en comparación con el trabajo necesario para crearlos en primer lugar. Esto es especialmente cierto cuando busca a gran instituciones distribuidas que necesitan para llevar a cabo una matriz de tareas de administración y procesamiento de datos compleja. Un hospitales o las organizaciones de entrega de mantenimiento integrados son excelentes ejemplos de tales entidades. Dichas entidades enfrentan a la necesidad de proporcionar software para admitir una gran variedad de funciones, para habilitar la información que se pasará de aplicación a aplicación para evitar la necesidad de entrada de datos duplicados y defectuoso, para proporcionar entrenamiento para los usuarios y los mantenedores de la software y proporcionar la sustitución de aplicaciones obsoletas o anticuadas mejorado por aquellos. Este proceso de reemplazo tiene sus propios requisitos para las pruebas y educación.  
  
  Sería imposible (prohibitivamente caro) para que tales entidades administrar todas sus funciones con una sola integrado de aplicación. En primer lugar, las instituciones no van a agrupar sus fortunas a un único proveedor y no encontrará toda la función que necesitan a través de un único proveedor. En segundo lugar, las necesidades operativas simple de procesamiento institucional imposibilitan para las entidades que se debe cumplir con una sola aplicación integrada. Por lo tanto, las instituciones será compatible con sus necesidades con varias aplicaciones. En orden para estas aplicaciones interoperar, las aplicaciones necesitan interfaces para intercambiar información. El número de aplicaciones y las interfaces implicadas a menudo es bastante grande. Dada esta arquitectura de aplicaciones distribuidas, el motor de la interfaz es un instrumento clave para administrar el procesamiento de datos para las instituciones con el tiempo. Los problemas clave son la migración, la asignación y educación. El trabajo de BTAHL7 consiste en hacer resolver estos problemas más fácil y eficaz como sea posible:  
  
- **Asignación**. El trabajo más importante en la implementación de la interfaz es crear la asignación entre las estructuras de aplicación/base de datos y las estructuras de datos utilizadas en la interfaz. Todo lo que hace la herramienta para facilitar esta sencilla y natural es bueno. Además, puesto que el documento de asignación se convertirá en una especificación de los desarrolladores de interfaz y la aplicación, es importante ser capaz de generar fácilmente la documentación del mismo. Utilice el Explorador de configuración de BTAHL7, Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y herramientas de BizTalk Server para desarrollar e implementar estas asignaciones.  
  
- **Migración**. Debe mantener la interoperabilidad de aplicaciones con el tiempo a medida que cambian las aplicaciones. Si considera que los problemas relacionados con el reemplazo de una sola aplicación, es la necesidad de actualizar las asignaciones de origen de datos a las interfaces aplicable. Con un motor de la interfaz debe haber sólo uno de éstos. Debe considerar donde se han instalado las interfaces y si cambian los estándares de interfaz con el tiempo. Encontrará que con el tiempo los estándares de interfaz cambiarán y tienen que migrarse a los estándares muy extendidos. Se recomienda que el plan de migración se tienen en cuenta los cambios futuros de interfaz. Deberá asignar entre los estándares y entre las distintas versiones del estándar. Además, dentro de los confines de un único estándar, especialmente uno flexible como HL7 V2, tiene que tratar con (a través de muchas aplicaciones) en varias implementaciones del mismo estándar. El motor de la interfaz debe ocuparse de esta complejidad de tal manera que es fácil de administrar.  
  
   Una tarea de migración de clave es el de migrar un cuerpo de las interfaces de un estándar a otro. Aquí es migrar todas las asignaciones que utilizan una versión anterior a la nueva la tarea, se tarda en localización concreta de la interfaz de cuenta y las extensiones, que puede ser un proceso complicado. La herramienta debe proporcionar asistencia con esta migración.  
  
   Utilice la pestaña de explorador validación de la configuración de BTAHL7 para especificar el espacio de nombres de un todos los esquemas de tipo de mensaje adicionales.  
  
- **Educación**. Las personas implicadas con la administración y compatibilidad de las aplicaciones seguirán evolucionando. Además, puesto que las interfaces son fundamentales para las características de interoperabilidad de la colección de aplicaciones, se procederá su documentación clave herramientas de administración de toda la empresa. Por tanto estas razones, es útil para proporcionar la fácil de usar y fácil de mantener la documentación de (a) las especificaciones de la interfaz, (b) la aplicación y introversion las asignaciones y c) la lógica de actividades de personalización y localización.  
  
## <a name="see-also"></a>Vea también  
[Información sobre el acelerador de HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)