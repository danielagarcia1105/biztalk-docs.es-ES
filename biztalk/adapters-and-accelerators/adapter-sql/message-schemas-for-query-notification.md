---
title: "Esquemas de mensajes de notificación de consulta mediante el adaptador de SQL en BizTalk | Documentos de Microsoft"
description: Usar el adaptador SQL para recibir las notificaciones de consulta de una base de datos de SQL Server de BizTalk
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f662f34a9ac31dd5ce200d776bc8b542008e98e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-query-notification"></a><span data-ttu-id="a3ca9-103">Esquemas de mensaje de notificación de consulta</span><span class="sxs-lookup"><span data-stu-id="a3ca9-103">Message Schemas for Query Notification</span></span>
<span data-ttu-id="a3ca9-104">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de la operación de notificación para recibir las notificaciones de consulta de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Notification operation to receive query notifications from the SQL Server database.</span></span>  
  
 <span data-ttu-id="a3ca9-105">Configurar la operación de notificación estableciendo las propiedades de enlace el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ca9-105">You configure the Notification operation by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="a3ca9-106">Para obtener más información acerca de las propiedades de enlace relacionadas con notificaciones, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca9-106">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="a3ca9-107">Establece el **NotificationStatement** enlace de propiedad para especificar una instrucción SQL (SELECT o EXEC \<procedimiento almacenado\>) para la notificación de consulta.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-107">You set the **NotificationStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the query notification.</span></span> <span data-ttu-id="a3ca9-108">El conjunto de resultados de esta consulta se devuelve como datos fuertemente tipados en el código en la operación de notificación.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-108">The result set of this query is returned as strongly-typed data to your code in the Notification operation.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="a3ca9-109">Estructura del mensaje para la operación de notificación</span><span class="sxs-lookup"><span data-stu-id="a3ca9-109">Message Structure for the Notification operation</span></span>  
 <span data-ttu-id="a3ca9-110">En la tabla siguiente se muestra la estructura del mensaje XML para la operación de notificación.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-110">The following table shows the XML message structure for the Notification operation.</span></span>  

<span data-ttu-id="a3ca9-111">**Operación**:`Notification`</span><span class="sxs-lookup"><span data-stu-id="a3ca9-111">**Operation**: `Notification`</span></span>

<span data-ttu-id="a3ca9-112">**Mensaje XML**:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-112">**XML message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

<span data-ttu-id="a3ca9-113">**Descripción**: este es el mensaje entrante que se envía el servidor SQL Server a los clientes de adaptador.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-113">**Description**: This is the inbound message that is sent by the SQL Server to the adapter clients.</span></span> <span data-ttu-id="a3ca9-114">En el mensaje:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-114">In the message:</span></span>

- <span data-ttu-id="a3ca9-115">La `<Info>` etiqueta indica el motivo de la notificación.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-115">The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="a3ca9-116">Por ejemplo, un valor de "inserción" en esta etiqueta indica que se ha insertado datos en una o varias de las tablas que se hace referencia en la instrucción de notificación.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span>
- <span data-ttu-id="a3ca9-117">La `<Source>` etiqueta indica el origen para la notificación.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-117">The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="a3ca9-118">Por ejemplo, un valor de "datos" en esta etiqueta indica un cambio en los datos de referencia a un objeto.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="a3ca9-119">De forma similar, un valor de "object" en esta etiqueta indica un cambio en un objeto que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span>
- <span data-ttu-id="a3ca9-120">La `<Type>` etiqueta indica el tipo de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-120">The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="a3ca9-121">Mensajes de notificación de consulta son de dos tipos: cambiar y suscribirse.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-121">Query notification messages are of two types: change and subscribe.</span></span> <span data-ttu-id="a3ca9-122">Un "cambiar" valor de la `<Type>` etiqueta indica que los resultados de la consulta han cambiado, mientras que un valor "suscribirse" en la `<Type>` etiqueta indica que ha fallado una solicitud de suscripción.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-122">A “change” value in the `<Type>` tag indicates that the results of the query have changed, whereas a “subscribe” value in the `<Type>` tag indicates that a subscription request failed.</span></span>

  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="a3ca9-123">Acción de mensaje para la operación de notificación</span><span class="sxs-lookup"><span data-stu-id="a3ca9-123">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="a3ca9-124">La acción de mensaje para la operación de notificación es "Notificaciones".</span><span class="sxs-lookup"><span data-stu-id="a3ca9-124">The message action for the notification operation is “Notification.”</span></span>  
  