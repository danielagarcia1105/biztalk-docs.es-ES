---
title: Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving in Visual Studio
- metadata
ms.assetid: d903b408-1144-4625-909d-710826e37769
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdf1d1943c471591e35f1efb6ca6e08f36948fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214332"
---
# <a name="get-metadata-for-oracle-database-operations-in-visual-studio"></a>Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede utilizar para ayudarle a desarrollar soluciones mediante el adaptador.  
  
-   El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] están disponibles en proyectos de BizTalk Server. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)  
  
-   La [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
 Todos estos tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:  
  
-   Proporcionar una interfaz de Microsoft Windows a través del cual se puede examinar y buscar para las operaciones que desea utilizar en la solución.  
  
-   Al recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.  
  
-   Convertir que los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y lo agrega al proyecto.  
  
 Esta sección proporciona instrucciones sobre cómo usar [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Conectarse a la base de datos de Oracle en Visual Studio mediante el servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md) 
  
-   [Examinar, buscar y obtener los metadatos de las operaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)