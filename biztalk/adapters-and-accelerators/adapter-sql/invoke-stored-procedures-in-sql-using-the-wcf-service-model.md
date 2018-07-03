---
title: Invocar procedimientos almacenados en SQL mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ce43db33101dfc3849743e8480e66a8fd76f53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023298"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>Invocar procedimientos almacenados en SQL mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta los procedimientos almacenados como operaciones que los clientes del adaptador pueden invocar en el cliente WCF para invocar el procedimiento almacenado. Según cómo el procedimiento almacenado devuelve el conjunto de resultados, el adaptador clasifica todos los procedimientos almacenados como:  
  
- **Procedimientos**. Invocar procedimientos almacenados desde el **procedimientos** nodo devuelve una matriz de conjunto de datos.  
  
- **Fuertemente tipado procedimientos**. Invocar procedimientos almacenados desde el **Strongly-Typed procedimientos** nodo devuelve un conjunto de resultados fuertemente tipado.  
  
  Tenga en cuenta que será el mismo conjunto de procedimientos almacenados en la base de datos que conectado aparece bajo el **procedimientos** y **Strongly-Typed procedimientos** nodo. Según el tipo de conjunto de resultados que desee, debe invocar el procedimiento almacenado desde el nodo correspondiente. Para obtener más información acerca de cómo los [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite procedimientos almacenados, vea [ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).  
  
  Esta sección proporciona instrucciones sobre cómo invocar procedimientos almacenados desde el **procedimientos** y **Strongly-Typed procedimientos** nodo mediante un cliente WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Involk débilmente tipada los procedimientos almacenados de SQL mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [Invocación del procedimiento almacenado fuertemente tipado en SQL mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)