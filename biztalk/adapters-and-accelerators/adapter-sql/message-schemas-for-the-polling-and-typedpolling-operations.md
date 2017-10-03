---
title: Esquemas de mensajes para el sondeo y operaciones de TypedPolling para el adaptador SQL en BizTalk | Documentos de Microsoft
description: "Estructura que se utiliza el adaptador de SQL en el módulo de adaptador de BizTalk (BAP) de mensajes de sondeo y TypedPolling"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f18185e4bfaf5502537a68044579b0f7721cd23
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a>Esquemas de mensaje para las operaciones de TypedPolling y sondeo
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies el sondeo y TypedPolling operaciones para devolver el conjunto de resultados de la consulta de sondeo a un cliente de adaptador de entrada.  
  
 Configurar las operaciones de sondeo y TypedPolling estableciendo las propiedades de enlace el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca de estas propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Establece el **PollingStatement** enlace de propiedad para especificar una instrucción SQL (SELECT o EXEC \<procedimiento almacenado >) para la consulta de sondeo. El conjunto de resultados de esta consulta se devuelve como datos en el código en la operación de sondeo y, como datos fuertemente tipados en la operación TypedPolling. La estructura del conjunto de resultados se determina por los metadatos que expone el adaptador para la consulta especificada.  
  
## <a name="polling-message-structure"></a>Estructura de mensaje de sondeo 
  
**Operación**:`Polling`

**Mensaje XML**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling">
    <PolledData>
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">
        <any>[Value]</any>
        <any>[Value]</any>
        …
        </DataSet>
    </PolledData>
 </Polling>
```

**Descripción**: el mensaje entrante que se envía el servidor SQL Server a los clientes de adaptador.  


## <a name="typedpolling-message-structure"></a>Estructura de los mensajes TypedPolling 

**Operación**:`TypedPolling`

**Mensaje XML**:  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

**Descripción**: el mensaje entrante fuertemente tipada que se envía el servidor SQL Server a los clientes de adaptador.
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a>Acción de mensaje para el sondeo y operaciones de TypedPolling  
 La acción de mensaje para el:  
  
-   Operación de sondeo es "sondeo".  
  
-   Operación TypedPolling es "TypedPolling."  
  
