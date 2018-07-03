---
title: Ejecutar operaciones compuestas en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd5bc7e1454cb00b3f163ec7201de327fccbd637
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001445"
---
# <a name="run-composite-operations-in-oracle-database"></a>Ejecutar operaciones compuestas en la base de datos de Oracle
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite a los clientes del adaptador realizar operaciones compuestas que pueden incluir cualquier número de las siguientes operaciones y en cualquier orden:  
  
- Seleccionar, insertar, actualizar y eliminar operaciones en tablas y vistas.  
  
- Procedimientos almacenados, funciones, procedimientos o funciones dentro de los paquetes que se exponen como operaciones en el adaptador.  
  
  Pueden dirigirse a las operaciones en una operación compuesta de tablas y vistas de la misma base de datos o bases de datos diferentes. Sin embargo, los datos no se comparten o reutilizar en distintas operaciones en una operación compuesta. Por ejemplo, en una operación compuesta, el conjunto de resultados de una operación Select no se puede usar como parámetro de entrada para un procedimiento almacenado.  
  
  Cada operación en una operación compuesta se realiza mediante una conexión independiente. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consume tantas conexiones de la agrupación de conexiones ODP.NET como el número de operaciones en una operación compuesta y, a continuación, libera las conexiones que se ejecutan las operaciones. Sin embargo, si una operación en la operación de composición devuelve un conjunto de resultados, la conexión se libera solo después de que se consume el mensaje.  
  
> [!IMPORTANT]
>  Si experimenta problemas de tiempo de espera mientras se ejecuta una operación compuesta podría ser porque el número de conexiones es menor que el número de operaciones en una operación compuesta que implican:  
> 
> - Procedimientos almacenados que contengan BFILE, BLOB, CLOB, NCLOB y REF CURSOR como OUT o IN OUT parámetros.  
>   -   Operación de selección.  
> 
>   Para resolver este problema, debe asegurarse de que, si hay un número de "n" de estas operaciones en una operación compuesta, el valor especificado para el **MinPoolSize** enlaza la propiedad es "n + 1" o superior. Para obtener más información sobre la **MinPoolSize** enlaza la propiedad, vea [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
 Para obtener información acerca de:  
  
- Cómo realizar operaciones compuestas en [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle mediante el uso de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
- Los esquemas para la operación compuesta de mensajes, vea [esquemas de mensaje para la operación compuesta](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)