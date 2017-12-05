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
ms.openlocfilehash: 0cd6a281bfca73e74f23ce25bb9fa08761a07789
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="ea97a-103">Esquemas de mensaje para las operaciones de TypedPolling y sondeo</span><span class="sxs-lookup"><span data-stu-id="ea97a-103">Message Schemas for the Polling and TypedPolling Operations</span></span>
<span data-ttu-id="ea97a-104">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies el sondeo y TypedPolling operaciones para devolver el conjunto de resultados de la consulta de sondeo a un cliente de adaptador de entrada.</span><span class="sxs-lookup"><span data-stu-id="ea97a-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Polling and TypedPolling inbound operations to return the result set of the polling query to an adapter client.</span></span>  
  
 <span data-ttu-id="ea97a-105">Configurar las operaciones de sondeo y TypedPolling estableciendo las propiedades de enlace el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea97a-105">You configure the Polling and TypedPolling operations by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ea97a-106">Para obtener más información acerca de estas propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ea97a-106">For more information about these binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="ea97a-107">Establece el **PollingStatement** enlace de propiedad para especificar una instrucción SQL (SELECT o EXEC \<procedimiento almacenado\>) para la consulta de sondeo.</span><span class="sxs-lookup"><span data-stu-id="ea97a-107">You set the **PollingStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the polling query.</span></span> <span data-ttu-id="ea97a-108">El conjunto de resultados de esta consulta se devuelve como datos en el código en la operación de sondeo y, como datos fuertemente tipados en la operación TypedPolling.</span><span class="sxs-lookup"><span data-stu-id="ea97a-108">The result set of this query is returned as data to your code in the Polling operation, and as strongly-typed data in the TypedPolling operation.</span></span> <span data-ttu-id="ea97a-109">La estructura del conjunto de resultados se determina por los metadatos que expone el adaptador para la consulta especificada.</span><span class="sxs-lookup"><span data-stu-id="ea97a-109">The structure of the result set is determined by the metadata that the adapter surfaces for the specified query.</span></span>  
  
## <a name="polling-message-structure"></a><span data-ttu-id="ea97a-110">Estructura de mensaje de sondeo</span><span class="sxs-lookup"><span data-stu-id="ea97a-110">Polling message structure</span></span> 
  
<span data-ttu-id="ea97a-111">**Operación**:`Polling`</span><span class="sxs-lookup"><span data-stu-id="ea97a-111">**Operation**: `Polling`</span></span>

<span data-ttu-id="ea97a-112">**Mensaje XML**:</span><span class="sxs-lookup"><span data-stu-id="ea97a-112">**XML Message**:</span></span>  
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

<span data-ttu-id="ea97a-113">**Descripción**: el mensaje entrante que se envía el servidor SQL Server a los clientes de adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea97a-113">**Description**: The inbound message that is sent by the SQL Server to the adapter clients.</span></span>  


## <a name="typedpolling-message-structure"></a><span data-ttu-id="ea97a-114">Estructura de los mensajes TypedPolling</span><span class="sxs-lookup"><span data-stu-id="ea97a-114">TypedPolling message structure</span></span> 

<span data-ttu-id="ea97a-115">**Operación**:`TypedPolling`</span><span class="sxs-lookup"><span data-stu-id="ea97a-115">**Operation**: `TypedPolling`</span></span>

<span data-ttu-id="ea97a-116">**Mensaje XML**:</span><span class="sxs-lookup"><span data-stu-id="ea97a-116">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

<span data-ttu-id="ea97a-117">**Descripción**: el mensaje entrante fuertemente tipada que se envía el servidor SQL Server a los clientes de adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea97a-117">**Description**: The strongly-typed inbound message that is sent by the SQL Server to the adapter clients.</span></span>
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="ea97a-118">Acción de mensaje para el sondeo y operaciones de TypedPolling</span><span class="sxs-lookup"><span data-stu-id="ea97a-118">Message Action for the Polling and TypedPolling Operations</span></span>  
 <span data-ttu-id="ea97a-119">La acción de mensaje para el:</span><span class="sxs-lookup"><span data-stu-id="ea97a-119">The message action for the:</span></span>  
  
-   <span data-ttu-id="ea97a-120">Operación de sondeo es "sondeo".</span><span class="sxs-lookup"><span data-stu-id="ea97a-120">Polling operation is “Polling.”</span></span>  
  
-   <span data-ttu-id="ea97a-121">Operación TypedPolling es "TypedPolling."</span><span class="sxs-lookup"><span data-stu-id="ea97a-121">TypedPolling operation is “TypedPolling.”</span></span>  
  
