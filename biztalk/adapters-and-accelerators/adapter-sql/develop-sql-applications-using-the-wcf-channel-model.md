---
title: Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a><span data-ttu-id="62027-102">Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="62027-102">Develop SQL applications using the WCF Channel Model</span></span>
<span data-ttu-id="62027-103">Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62027-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] by sending XML messages directly over a channel instance created with the SQL Server Binding.</span></span>  
  
 <span data-ttu-id="62027-104">Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en la base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="62027-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SQL database.</span></span> <span data-ttu-id="62027-105">Este control procede del hecho de que en el modelo de canal WCF, puede controlar directamente el contenido de los mensajes que envía a través del canal.</span><span class="sxs-lookup"><span data-stu-id="62027-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="62027-106">En determinados escenarios, este nivel adicional de control puede ser beneficioso.</span><span class="sxs-lookup"><span data-stu-id="62027-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="62027-107">Por ejemplo, cuando se usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar selectivamente las columnas de las filas de destino mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="62027-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="62027-108">Las únicas columnas que son necesarias son los que tienen "nillable = false" en el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="62027-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="62027-109">El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipada de la plantilla que incluye todas las columnas en el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="62027-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="62027-110">Las secciones en este tema explica cómo realizar operaciones en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="62027-110">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62027-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="62027-111">In This Section</span></span>  
  
-   [<span data-ttu-id="62027-112">Información general sobre el modelo de canal WCF con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="62027-112">Overview of the WCF channel model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="62027-113">Crear un canal con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="62027-113">Create a channel using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="62027-114">Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="62027-114">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="62027-115">Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="62027-115">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a><span data-ttu-id="62027-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="62027-116">See Also</span></span>  
[<span data-ttu-id="62027-117">Desarrollar las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="62027-117">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)