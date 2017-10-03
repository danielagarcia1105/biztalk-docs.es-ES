---
title: Invocar los procedimientos almacenados de SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2d707c37ba92fb6f1d1608ae43d02d1e964cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>Invocar los procedimientos almacenados de SQL mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta los procedimientos almacenados como operaciones que los clientes de adaptador pueden invocar en el cliente WCF para invocar el procedimiento almacenado. En función de cómo el procedimiento almacenado devuelve el conjunto de resultados, el adaptador clasifica todos los procedimientos almacenados como:  
  
-   **Procedimientos**. Invocar procedimientos almacenados desde el **procedimientos** nodo devuelve una matriz de conjunto de datos.  
  
-   **Inflexible procedimientos**. Invocar procedimientos almacenados desde el **Strongly-Typed procedimientos** nodo devuelve un conjunto de resultados fuertemente tipada.  
  
 Tenga en cuenta que será el mismo conjunto de procedimientos almacenados en la base de datos conectado a aparece tanto en el **procedimientos** y **Strongly-Typed procedimientos** nodo. Según el tipo de conjunto de resultados que desee, debe invocar el procedimiento almacenado desde el nodo relevante. Para obtener más información acerca de cómo los [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite procedimientos almacenados, vea [ejecutar los procedimientos almacenados de SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).  
  
 Esta sección proporciona instrucciones sobre cómo invocar procedimientos almacenados desde el **procedimientos** y **Strongly-Typed procedimientos** nodo mediante el uso de un cliente de WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Involk débilmente tipada los procedimientos almacenados de SQL mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [Invocar fuertemente tipada de procedimiento almacenado en SQL mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)