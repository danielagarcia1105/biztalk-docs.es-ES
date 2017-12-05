---
title: "Resolución ESB y marco de proveedores de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c82c2247-1f0a-48bd-98c2-9c816f4d68d7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c23fa8aca6def654b594d8b4fccf5d584e12fed4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>Resolución ESB y marco de proveedores de adaptador
La resolución y el marco de proveedores de adaptador proporciona una arquitectura acoplable completa para resolver dinámicamente información de punto de conexión y los tipos de asignación de BizTalk Server. Utiliza los componentes extensibles, que permiten a los desarrolladores cambiar el comportamiento para satisfacer sus propias necesidades y ampliar el mecanismo para admitir la solución alternativa y los métodos de enrutamiento.  
  
 La resolución y el marco de proveedores de adaptador proporciona compatibilidad con Universal Description, Discovery y Integration (UDDI), motor de reglas de negocios (BRE) y XML Path Language (XPath). También expone interfaces de desarrollador (**IResolveProvider** y **IAdapterProvider**) para permitir la creación de componentes personalizados de resolución y el adaptador. Éstos son los tres componentes principales de la resolución y el marco de proveedores de adaptador:  
  
-   **Resoluciones.** Se definen mediante un esquema, la cadena de conexión y a través de la implementación de la **IResolveProvider** interfaz en un ensamblado de .NET Framework. Estos se cargan en memoria caché en tiempo de ejecución y admiten una variedad de tipos de resolución y cadenas de conexión.  
  
-   **Proveedores de adaptador.** Se definen a través de la implementación de la **IAdapterProvider** interfaz dentro de un ensamblado de .NET Framework. Estos se registran por su tipo de transporte de BizTalk Server, que establece la información de punto de conexión proporcionada por una resolución en el adaptador de BizTalk Server adecuado.  
  
-   **Componentes de canalización itinerarios.** Estas instrucciones de resolución de las cadenas de conexión o de los encabezados SOAP de itinerario de ESB de analizar y proporcionan funciones de ejecución de resolución o transformación usa la resolución y el marco de proveedores de adaptador de punto de conexión. Los componentes dinámicamente pueden establecer propiedades de punto de conexión de BizTalk Server o ejecutar una transformación de asignación de BizTalk Server en función de instrucciones de resolución de la cadena de conexión o de los encabezados SOAP de itinerario ESB. Estos componentes son responsables de administrar, actualizar y conservar el itinerario en los límites del servicios y de proceso. El componente de desensamblador opcional proporciona funciones de análisis de BizTalk Server nativo del mensaje e implementa el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] característica de enrutamiento para varios puntos de conexión sin la necesidad de un servicio de orquestación.  
  
 Para obtener más información acerca de la resolución dinámica y enrutamiento dinámico, consulte [utilizando resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md) y [usando la transformación dinámica](../esb-toolkit/using-dynamic-transformation.md). Para obtener información acerca de la resolución y el marco de proveedores de adaptador, vea [modificar y extender el Kit de herramientas de ESB de BizTalk](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).