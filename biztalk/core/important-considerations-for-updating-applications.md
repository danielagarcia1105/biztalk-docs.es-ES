---
title: Consideraciones importantes para actualizar aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24528dcce390376b7ac2e47199aa5ae06d412a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257748"
---
# <a name="important-considerations-for-updating-applications"></a>Consideraciones importantes para actualizar aplicaciones
A continuación se indican problemas importantes que deben considerarse antes de actualizar una aplicación, especialmente si la misma se ejecuta en un entorno de producción.  
  
## <a name="general-considerations"></a>Consideraciones generales  
  
-   Las entidades y reglas están visibles en un ámbito de grupo, por lo que agregar entidades y reglas adicionales puede afectar a otras aplicaciones.  
  
-   Para anular la implementación de un artefacto del que depende otro, primero se debe anular la implementación del artefacto dependiente.  
  
    > [!NOTE]
    >  La consola de administración de BizTalk Server mostrará una advertencia e impedirá anular la implementación de artefactos si se intenta realizar en un orden incorrecto.  
  
-   Si se actualiza un ensamblado de BizTalk en una aplicación existente, debe reiniciar instancias de host para que los cambios surtan efecto. Al reiniciar una instancia de host detiene todas las demás aplicaciones que se ejecutan en la instancia de host.  
  
-   Si se usa Visual Studio para implementar una aplicación en un entorno de producción (no se recomienda en absoluto) y la opción Reiniciar instancias de host está establecida como True en las propiedades del proyecto, se reiniciarán todas las instancias de host al implementar la aplicación, incluidas las que no estén asociadas a esa aplicación. Esto detendrá todas las demás aplicaciones que estén en ejecución en cualquier instancia de host del equipo local.  
  
-   Si desea actualizar un ensamblado de BizTalk Server (que contiene una orquestación, un esquema o una asignación) que se implementa como una aplicación de BizTalk, puede realizar cualquiera de las acciones siguientes:  
  
    -   Efectúe una implementación en paralelo. Puede modificar de forma apropiada el ensamblado más reciente, generalmente incrementando la versión. Esto hace que ambos ensamblados tengan un nombre completo de ensamblado distinto. Para obtener más información, consulte [cómo implementar una nueva versión de una aplicación en ejecución Side-by-side con una versión existente](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).  
  
    -   Sustituya el ensamblado de BizTalk Server existente por un nuevo ensamblado. Debe detener todas las instancias de host que tengan la posibilidad de cargar el ensamblado obsoleto, sustituir el ensamblado obsoleto en la GAC y reiniciar las instancias de host.  
  
-   Si se implementa una aplicación completamente nueva para reemplazar una existente, se debe corregir cualquier referencia existente entre otras aplicaciones y la aplicación que se está reemplazando.  
  
## <a name="considerations-for-updating-schemas"></a>Consideraciones para actualizar esquemas  
  
-   Si agrega un ensamblado a una aplicación que incluye un nuevo esquema con el mismo tipo de mensaje como un esquema existente en el grupo de BizTalk, se usará el esquema con el mayor número de versión cuando la resolución de esquemas se produce en las canalizaciones. Además, si un tipo de mensaje hace referencia a más de un tipo. NET, esta ambigüedad puede provocar errores de ejecución de canalización. Esto se debe a que la búsqueda de esquemas usa el tipo de mensaje, el espacio de nombres de destino y el nombre de raíz de la instancia. Esta situación puede ocurrir con las canalizaciones de aplicaciones que usen un esquema con el mismo tipo de mensaje que el nuevo esquema. Para obtener más información acerca de la resolución de esquemas, vea [resolución de esquemas en componentes de canalización](../core/schema-resolution-in-pipeline-components.md).  
  
-   Al actualizar un esquema, también se deben actualizar las asignaciones que hacen referencia al mismo (o crear nuevas asignaciones) y cualquier otra orquestación basada en él.  
  
-   Si se incrementa la versión de un esquema, se debe actualizar la referencia al esquema para cualquier instancia y componente de canalización que lo use.  
  
-   Al anular la implementación de un esquema, se activa la versión anterior del esquema, si está disponible.  
  
## <a name="considerations-for-updating-policies"></a>Consideraciones para actualizar directivas  
  
-   El tiempo de ejecución de BizTalk Server usa la versión más alta de una directiva con estado implementado.  
  
## <a name="see-also"></a>Vea también  
 [Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md)