---
title: Obtener metadatos para operaciones de base de datos de Oracle en Visual Studio | Microsoft Docs
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
ms.openlocfilehash: 1f1afec8c125d2350d7fa7706b523931a3c6bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003453"
---
# <a name="get-metadata-for-oracle-database-operations-in-visual-studio"></a>Obtener metadatos para operaciones de base de datos de Oracle en Visual Studio
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede usar para desarrollar soluciones mediante el adaptador.  
  
- El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] están disponibles en proyectos de BizTalk Server. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de BizTalk con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)  
  
- El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
  Estos tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:  
  
- Proporcionar una interfaz de Microsoft Windows a través del cual puede examinar y buscar para las operaciones que desea usar en la solución.  
  
- Recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.  
  
- Convertir los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y agregarlo al proyecto.  
  
  Esta sección proporciona instrucciones sobre cómo usar [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Conectarse a la base de datos de Oracle en Visual Studio mediante Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md) 
  
-   [Examinar, buscar y obtener metadatos para operaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)