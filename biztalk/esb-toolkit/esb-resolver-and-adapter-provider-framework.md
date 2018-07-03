---
title: Marco de proveedores de adaptador y la resolución ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c82c2247-1f0a-48bd-98c2-9c816f4d68d7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 900897c4b740f39dbec2f5f513b5e814d1589bf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987029"
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>Marco de proveedores de adaptador y la resolución ESB
El marco de proveedores de adaptador y la resolución proporciona una arquitectura conectable completa para resolver dinámicamente la información de punto de conexión y los tipos de mapa de BizTalk Server. Usa los componentes extensibles, lo que permite a los desarrolladores cambiar el comportamiento para adaptarlo a sus propios requisitos y ampliar el mecanismo para admitir la solución alternativa y los métodos de enrutamiento.  
  
 La resolución y el marco de proveedores de adaptador proporciona compatibilidad con Universal Description, Discovery y Integration (UDDI), motor de reglas de negocios (BRE) y XML Path Language (XPath). También expone las interfaces de desarrollador (**IResolveProvider** y **IAdapterProvider**) para permitir la creación de componentes de resolución y adaptadores personalizados. Los siguientes son los tres componentes principales de la resolución y el marco de proveedores de adaptador:  
  
- **Resoluciones.** Se definen mediante un esquema, la cadena de conexión y a través de la implementación de la **IResolveProvider** interfaz en un ensamblado de .NET Framework. Estos se cargan y almacenan en caché en tiempo de ejecución y admiten una variedad de tipos de resolución y cadenas de conexión.  
  
- **Proveedores de adaptador.** Se definen mediante la implementación de la **IAdapterProvider** interfaz dentro de un ensamblado de .NET Framework. Estos se registran por su tipo de transporte de BizTalk Server, que establece la información de punto de conexión proporcionada por una resolución en el adaptador de BizTalk Server apropiado.  
  
- **Componentes de canalización de itinerarios.** Estas instrucciones de resolución de las cadenas de conexión o de los encabezados SOAP de itinerarios de ESB de analizar y proporcionan funciones de ejecución de resolución o transformación mediante el marco de proveedores de adaptador y resolución de punto de conexión. Pueden establecer propiedades de punto de conexión de BizTalk Server o ejecutar una transformación mapa de BizTalk Server según las instrucciones de resolución de la cadena de conexión o de los encabezados SOAP de itinerarios de ESB dinámicamente los componentes. Estos componentes son responsables de administrar, actualizar y conservar el itinerario a través de límites de procesos y de servicios. El componente de desensamblador opcional proporciona análisis de BizTalk Server nativo del mensaje y la implementa el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] característica de enrutamiento a varios puntos de conexión sin necesidad de un servicio de orquestación.  
  
  Para obtener más información acerca de resolución dinámica y el enrutamiento dinámico, consulte [enrutamiento y uso de resolución dinámica](../esb-toolkit/using-dynamic-resolution-and-routing.md) y [utilizando la transformación dinámica](../esb-toolkit/using-dynamic-transformation.md). Para obtener información acerca de la resolución y el marco de proveedores de adaptador, vea [modificación y extensión del Kit de herramientas de BizTalk ESB](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).