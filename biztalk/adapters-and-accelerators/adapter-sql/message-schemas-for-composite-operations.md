---
title: Esquemas de mensajes para operaciones compuestas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b89c354baea2ddb46abf549752dc09699b9c9695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222516"
---
# <a name="message-schemas-for-composite-operations"></a><span data-ttu-id="8ee16-102">Esquemas de mensaje para operaciones compuestas</span><span class="sxs-lookup"><span data-stu-id="8ee16-102">Message Schemas for Composite Operations</span></span>
<span data-ttu-id="8ee16-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] permite ejecutar operaciones compuestas en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8ee16-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables you to execute composite operations on the SQL Server database.</span></span> <span data-ttu-id="8ee16-104">Una operación compuesta puede contener varias operaciones, incluida la inserción, actualización y eliminar operaciones en las tablas y vistas y las operaciones en los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="8ee16-104">A composite operation can contain multiple operations including the Insert, Update, and Delete operations on the tables and views, and operations on stored procedures.</span></span> <span data-ttu-id="8ee16-105">Una operación compuesta puede incluir estas operaciones en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="8ee16-105">A composite operation can include these operations in any order.</span></span>  
  
 <span data-ttu-id="8ee16-106">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="8ee16-106">For more information about:</span></span>  
  
-   <span data-ttu-id="8ee16-107">Operaciones compuestas, consulte [compatibilidad para operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span><span class="sxs-lookup"><span data-stu-id="8ee16-107">Composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
-   <span data-ttu-id="8ee16-108">Cómo realizar operaciones compuestas mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="8ee16-108">How to perform composite operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Run composite operations in SQL Server  using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="8ee16-109">Estructura del mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="8ee16-109">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="8ee16-110">Puesto que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="8ee16-110">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="8ee16-111">Como una operación compuesta contiene operaciones en tablas, vistas y procedimientos almacenados, el mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="8ee16-111">As a composite operation contains operations on tables, views, and stored procedures, the composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="8ee16-112">En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado que no tome ningún parámetros de entrada y una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="8ee16-112">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="8ee16-113">Operación</span><span class="sxs-lookup"><span data-stu-id="8ee16-113">Operation</span></span>|<span data-ttu-id="8ee16-114">Mensaje XML</span><span class="sxs-lookup"><span data-stu-id="8ee16-114">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ee16-115">Solicitud de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="8ee16-115">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|<span data-ttu-id="8ee16-116">Respuesta de operación compuesta</span><span class="sxs-lookup"><span data-stu-id="8ee16-116">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="8ee16-117">[Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.</span><span class="sxs-lookup"><span data-stu-id="8ee16-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="8ee16-118">[COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8ee16-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="8ee16-119">[Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.</span><span class="sxs-lookup"><span data-stu-id="8ee16-119">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="8ee16-120">[NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.</span><span class="sxs-lookup"><span data-stu-id="8ee16-120">[TABLE_NAME] = Name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="8ee16-121">[FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.</span><span class="sxs-lookup"><span data-stu-id="8ee16-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="8ee16-122">[SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.</span><span class="sxs-lookup"><span data-stu-id="8ee16-122">[SP_NAME] = The stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="8ee16-123">Acción de mensaje para la operación de composición</span><span class="sxs-lookup"><span data-stu-id="8ee16-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="8ee16-124">La acción de mensaje para la operación compuesta es "CompositeOperation."</span><span class="sxs-lookup"><span data-stu-id="8ee16-124">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee16-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ee16-125">See Also</span></span>  
 [<span data-ttu-id="8ee16-126">Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ee16-126">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)