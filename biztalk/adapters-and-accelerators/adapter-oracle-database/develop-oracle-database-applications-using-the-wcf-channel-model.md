---
title: Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4990ebb9e9aad612a82af42b3d186643da1e91ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002733"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a><span data-ttu-id="e7230-102">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-102">Develop Oracle Database applications using the WCF Channel Model</span></span>
<span data-ttu-id="e7230-103">Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] mediante el envío de mensajes XML directamente a través de una instancia de canal creada con el enlace de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="e7230-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] by sending XML messages directly over a channel instance created with the Oracle DB Binding.</span></span>  
  
 <span data-ttu-id="e7230-104">Una ventaja de utilizar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo de canal proporciona un control más minucioso sobre las operaciones que se realizan en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="e7230-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle database.</span></span> <span data-ttu-id="e7230-105">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="e7230-105">Why?</span></span> <span data-ttu-id="e7230-106">En el modelo de canal WCF controla directamente el contenido de los mensajes que envían a través del canal.</span><span class="sxs-lookup"><span data-stu-id="e7230-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="e7230-107">En determinados escenarios, este nivel adicional de control puede ser beneficioso.</span><span class="sxs-lookup"><span data-stu-id="e7230-107">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="e7230-108">Por ejemplo, cuando usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar columnas de las filas de destino selectivamente mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e7230-108">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="e7230-109">El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipados para la plantilla que incluye todas las columnas en el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="e7230-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span> <span data-ttu-id="e7230-110">Si tiene una columna "nillable = false" en el archivo WSDL, debe actualizarse mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e7230-110">If a column has “nillable=false” in the WSDL, it must be updated using the WCF service model.</span></span>  
  
 <span data-ttu-id="e7230-111">Otra ventaja clave que proporciona el modelo de canal WCF con respecto al modelo de servicio WCF es compatible con más completa al extremo de streaming de tipos de datos de objetos grandes (LOB) de Oracle.</span><span class="sxs-lookup"><span data-stu-id="e7230-111">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for end-to-end streaming of Oracle large object (LOB) data types.</span></span> <span data-ttu-id="e7230-112">Mediante el modelo de canal WCF puede realizar streaming to-end:</span><span class="sxs-lookup"><span data-stu-id="e7230-112">By using the WCF channel model you can perform end-to-end streaming:</span></span>  
  
- <span data-ttu-id="e7230-113">Para actualizar una columna LOB de una tabla o vista mediante la operación UpdateLOB.</span><span class="sxs-lookup"><span data-stu-id="e7230-113">To update an LOB column in a table or view using the UpdateLOB operation.</span></span>  
  
- <span data-ttu-id="e7230-114">Al final y en los parámetros que contienen LOB datos devueltos por procedimientos y funciones.</span><span class="sxs-lookup"><span data-stu-id="e7230-114">On OUT and IN OUT parameters containing LOB data that are returned by procedures and functions.</span></span>  
  
- <span data-ttu-id="e7230-115">En los datos LOB que se encuentra en el resultado de una operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="e7230-115">On LOB data that is contained in the result of a SQLEXECUTE operation.</span></span>  
  
- <span data-ttu-id="e7230-116">En las columnas de datos LOB que se devuelven en la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="e7230-116">On LOB data columns that are returned in the POLLINGSTMT operation.</span></span>  
  
- <span data-ttu-id="e7230-117">En las columnas de datos LOB que son devueltos por una operación Select en una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="e7230-117">On LOB data columns that are returned by a Select operation on a table or view.</span></span>  
  
  <span data-ttu-id="e7230-118">Esto es porque en el modelo de canal WCF directamente controlar cómo proporcionar el cuerpo del mensaje en los mensajes salientes y cómo se procesa el cuerpo del mensaje en los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e7230-118">This is because in the WCF channel model you directly control how you provide the message body on outgoing messages and how you process the message body on incoming messages.</span></span>  
  
  <span data-ttu-id="e7230-119">En cambio, sólo se proporciona el modelo de servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="e7230-119">In contrast, the WCF service model only provides:</span></span>  
  
- <span data-ttu-id="e7230-120">To-end para los datos LOB en una sola operación, la operación ReadLOB de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="e7230-120">End-to-end streaming for LOB data on one operation, the ReadLOB operation.</span></span>  
  
- <span data-ttu-id="e7230-121">Ninguna posibilidad de actualizar los datos LOB en la base de datos de Oracle de manera secuenciada.</span><span class="sxs-lookup"><span data-stu-id="e7230-121">No capability to update LOB data on the Oracle database in a streamed fashion.</span></span>  
  
  <span data-ttu-id="e7230-122">Las secciones de este tema explican cómo realizar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="e7230-122">The sections in this topic explain how to perform operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7230-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e7230-123">In This Section</span></span>  
  
-   [<span data-ttu-id="e7230-124">Información general del modelo del canal WCF con el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="e7230-124">Overview of the WCF channel model with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="e7230-125">Crear un canal con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="e7230-125">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [<span data-ttu-id="e7230-126">Invocar operaciones en la base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-126">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e7230-127">Ejecutar una operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-127">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e7230-128">Ejecutar una operación de inserción en la base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-128">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e7230-129">Invocar una función de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-129">Invoke a Function in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e7230-130">Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-130">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [<span data-ttu-id="e7230-131">Streaming tipos de datos LOB de base de datos de Oracle, mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e7230-131">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)