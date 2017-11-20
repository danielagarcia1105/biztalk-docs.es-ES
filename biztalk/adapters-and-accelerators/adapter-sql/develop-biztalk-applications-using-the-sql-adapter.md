---
title: Desarrollar aplicaciones de BizTalk con el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5471f28e-bce1-4295-b56d-954690e60749
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9963764a298246c5a236d10b6010feee8497278f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sql-adapter"></a><span data-ttu-id="d732d-102">Desarrollar aplicaciones de BizTalk con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-102">Develop BizTalk applications using the SQL adapter</span></span>
<span data-ttu-id="d732d-103">Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="d732d-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="d732d-104">Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="d732d-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="d732d-105">CBR puede utilizarse en escenarios donde los mensajes que se envían a SQL Server no requieren ningún procesamiento intensivo.</span><span class="sxs-lookup"><span data-stu-id="d732d-105">CBR can be used in scenarios where the messages being sent to SQL Server do not require any intensive processing.</span></span> <span data-ttu-id="d732d-106">Por ejemplo, si sabe que el puerto de recepción recibirá mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d732d-106">For example, if you know that the receive port will receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="d732d-107">En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d732d-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d732d-108">Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d732d-108">This section provides information about using BizTalk orchestrations to perform operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d732d-109">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que puede interactuar con un enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="d732d-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d732d-110">Para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="d732d-110">To use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="d732d-111">Para obtener información sobre cómo establecer propiedades de enlace, vea [configurar las propiedades de enlace para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="d732d-111">For information about how to set binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d732d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d732d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d732d-113">Requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-113">Prerequisites to create SQL applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md) 
  
-   [<span data-ttu-id="d732d-114">Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-114">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) 
  
-   [<span data-ttu-id="d732d-115">INSERT, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-115">Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="d732d-116">Ejecutar operaciones en tablas y vistas con los tipos de datos grandes con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-116">Run Operations on Tables and Views with Large Data Types using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="d732d-117">Ejecutar procedimientos almacenados en SQL Server mediante el uso de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-117">Execute Stored Procedures in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="d732d-118">Ejecutar procedimientos almacenados con un parámetro XML único</span><span class="sxs-lookup"><span data-stu-id="d732d-118">Execute Stored Procedures With a Single XML Parameter</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)  
  
-   [<span data-ttu-id="d732d-119">Ejecutar almacenados procedimientos tener una cláusula FOR XML en SQL Server con el servidor BizTalk server</span><span class="sxs-lookup"><span data-stu-id="d732d-119">Execute Stored Procedures Having a FOR XML Clause in SQL Server using BizTalk server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="d732d-120">Ejecutar operaciones compuestas en SQL Server mediante el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-120">Run Composite Operations on SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="d732d-121">Invocar funciones escalares en SQL Server mediante el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-121">Invoke Scalar Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="d732d-122">Invocar funciones con valores de tabla en SQL Server mediante el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-122">Invoke Table-Valued Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md) 
  
-   [<span data-ttu-id="d732d-123">Realizar ExecuteReader, ExecuteScalar u operaciones ExecuteNonQuery mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-123">Performing ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="d732d-124">Sondeo de servidor SQL mediante el adaptador SQL con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-124">Polling SQL Server by Using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)  
  
-   [<span data-ttu-id="d732d-125">Recibir notificaciones de consulta SQL mediante el uso de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d732d-125">Receive SQL Query Notifications by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d732d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d732d-126">See Also</span></span>  
[<span data-ttu-id="d732d-127">Desarrollar las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="d732d-127">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)