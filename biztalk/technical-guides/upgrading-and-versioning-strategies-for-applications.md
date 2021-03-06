---
title: Actualización y las estrategias de versión de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf239b00d45d62a0ee3587baaea40482bfe50667
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015355"
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a>Actualizar y las estrategias de control de versiones de aplicaciones
Control de versiones de aplicación de BizTalk puede ser un problema cuando necesite ejecutar dos versiones de una solución de BizTalk en paralelo, o si no puede utilizar el tiempo de inactividad de aplicación de BizTalk para implementar una nueva versión. Si no es necesario ejecutar dos versiones de la solución al mismo tiempo (por ejemplo, donde no haya ningún orquestaciones de larga duración) y las ventanas de mantenimiento de servicio están disponibles, es absolutamente aceptable para anular la implementación de la versión anterior e implementar la nueva versión como una estrategia de control de versiones (sin control de versiones de ensamblado). Ésta es una estrategia de control de versiones posibles, aunque todavía sigue siendo recomendable incrementar el número de versión de archivo (para que sepa qué versión se implementa en los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
## <a name="when-to-use-versioning"></a>Cuándo se debe utilizar el control de versiones  
 Si necesita admitir orquestaciones de larga ejecución, o debe realizar las implementaciones de aplicaciones de BizTalk sin tiempo de inactividad de aplicación de BizTalk, debe implementar y practicar un sólido,-to-end [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] estrategia de control de versiones para el escenarios de versión diferentes. Esto incluye las versiones de ensamblado de .NET y las versiones de todos los artefactos de BizTalk, que incluye los esquemas, mapas, canalizaciones, los componentes de canalización, orquestaciones, adaptadores personalizados, clases personalizadas llamado en orquestaciones y mapas, reglas de negocios y BAM.  
  
 Versión del esquema es único en el que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] canalizaciones determinan el tipo de mensaje de un mensaje basándose en el nodo raíz más de espacio de nombres de destino definido en el esquema de nombre. Para obtener más información, consulte [resolución de esquemas en componentes de canalización](../core/schema-resolution-in-pipeline-components.md). Si necesita para la versión de los esquemas, un indicador de versión debe formar parte del espacio de nombres de destino. Si cambia la versión de esquema tiene un efecto dominó a lo largo de la solución y, por tanto, debe planearse de antemano. Al crear mensajes de orquestación, busque **BizTalk Server: 8 sugerencias y trucos para mejorar la programación de BizTalk** (sugerencia 1: siempre utilice tipos de mensaje de varias partes). Uso de este método proporciona mayor flexibilidad cuando los esquemas de control de versiones.  
  
## <a name="using-factoring-for-assembly-versioning"></a>Uso de factorización para las versiones de ensamblado  
 Si necesita admitir orquestaciones de larga ejecución, las implementaciones en paralelo o las actualizaciones de sin tiempo de inactividad, debe implementar una estrategia de empaquetado y control de versiones de ensamblado. Para llevar a cabo las versiones de ensamblado de artefactos de BizTalk, los ensamblados de la solución de BizTalk deben tenerse en cuenta (empaquetar) como para permitir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] control de versiones.  Hay tres tipos de factorización:  
  
-   **No hay factorización**  
  
     Todos los artefactos de BizTalk están en un ensamblado. Esto es más fácil de comprender e implementar, pero proporciona la menor cantidad de flexibilidad.  
  
-   **Factorización completa**  
  
     Cada artefacto de BizTalk está en su propio ensamblado. Esto ofrece la máxima flexibilidad, pero es la más compleja para implementar y comprender.  
  
-   **Factorización óptimo**  
  
     En alguna parte entre "ningún factorización" y "factorización completa" basándose en un análisis exhaustivo de las aplicaciones de BizTalk. Además de las versiones, esto permite implementar fácilmente el diseño de Host de BizTalk. Esto se logra mediante la búsqueda de relaciones entre artefactos de BizTalk. Artefactos que están siempre con control de versiones entre sí por lo general se pueden colocar en el mismo ensamblado. Si es necesaria crear versiones independientes de los artefactos, debe colocar en distintos ensamblados. Este es el nivel de factorización que desea conseguir.  
  
## <a name="additional-resources"></a>Recursos adicionales  
  
 Definir y practicar una estrategia de control de versiones sólido para asegurarse de que proporciona las estrategias de implementación de side-by-side es posible que tenga. Recursos para estrategias de actualización y la versión de la aplicación de BizTalk Server son los siguientes:  
  
-   [Actualización de una aplicación](../technical-guides/updating-an-application.md)  
  
-   [Actualización de aplicaciones de BizTalk](../core/updating-biztalk-applications.md)
  
-   [Control de versiones de proyectos de BizTalk Server](../core/biztalk-server-project-versioning.md)  
  
-   [Descripción de implementación de aplicación de BizTalk Server](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)
