---
title: Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7ac720-e573-4564-8d15-8212a815f1f7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec993dd308abf0f364eb73f6f35d48d618d6807e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter"></a>Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede utilizar para ayudarle a desarrollar soluciones con el adaptador: el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Los clientes de adaptador deben usar estos componentes para conectarse a SQL Server y, a continuación, generar metadatos para las operaciones que deseen realizar.  
  
 Todos estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:  
  
-   Proporcionar una interfaz de Microsoft Windows a través del cual se puede examinar y buscar para las operaciones que desea utilizar en la solución.  
  
-   Al recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.  
  
-   Convertir que los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y lo agrega al proyecto.  
  
 Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
