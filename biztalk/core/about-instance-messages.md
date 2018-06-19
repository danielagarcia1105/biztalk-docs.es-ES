---
title: Acerca de los mensajes de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf956fb9f201697ac8c2b7da2135e469e03de55e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224780"
---
# <a name="about-instance-messages"></a><span data-ttu-id="35e5a-102">Acerca de los mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="35e5a-102">About Instance Messages</span></span>
<span data-ttu-id="35e5a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía y recibe mensajes de instancia, cada uno de los cuales representa normalmente uno o varios documentos empresariales, como un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="35e5a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends and receives instance messages, each of which typically represents one or more business documents such as a purchase order.</span></span> <span data-ttu-id="35e5a-104">Un mensaje de instancia es una instancia de una estructura de mensaje definida por uno o más esquemas</span><span class="sxs-lookup"><span data-stu-id="35e5a-104">An instance message is an instance of a message structure defined by one or more schemas.</span></span> <span data-ttu-id="35e5a-105">Un esquema, o un conjunto de esquemas utilizados de forma conjunta, define lo que constituye un mensaje de instancia válido.</span><span class="sxs-lookup"><span data-stu-id="35e5a-105">A schema, or a set of schemas being used together, defines what constitutes a valid instance message.</span></span> <span data-ttu-id="35e5a-106">Por ejemplo, se puede establecer que un pedido de compra tenga varios registros dentro; por ejemplo, un registro ShipTo, un registro BillTo, un registro Items, etc.</span><span class="sxs-lookup"><span data-stu-id="35e5a-106">For example, a purchase order might be defined to have several records within it, such as a ShipTo record, a BillTo record, an Items record, and so on.</span></span> <span data-ttu-id="35e5a-107">Cada uno de estos registros se puede definir de modo que contenga sus propios subregistros y campos.</span><span class="sxs-lookup"><span data-stu-id="35e5a-107">Each of these records can be defined to contain their own subrecords and fields.</span></span> <span data-ttu-id="35e5a-108">El esquema correspondiente define el contenido potencial de estos registros y campos, y los mensajes de instancia correspondientes incluyen los pedidos de compra reales que contienen datos de pedidos de compra estructurados en función del esquema.</span><span class="sxs-lookup"><span data-stu-id="35e5a-108">The corresponding schema defines the potential contents of these records and fields and the corresponding instance messages contain actual purchase orders that contain purchase order data structured according to the schema.</span></span>  
  
 <span data-ttu-id="35e5a-109">BizTalk Server puede enviar y recibir mensajes de instancia en una variedad ampliable de formatos, aunque un formato, XML, tiene una importancia especial como el formato al que se convierten todos los formatos de mensajes para el procesamiento interno.</span><span class="sxs-lookup"><span data-stu-id="35e5a-109">BizTalk Server can send and receive instance messages in an extensible variety of formats although one format, XML, has special significance as the format into which all message formats are translated for internal processing.</span></span> <span data-ttu-id="35e5a-110">Un documento XML específico utiliza un conjunto definido de etiquetas de inicio y finalización, organizadas de forma jerárquica, para organizar los datos dentro del mensaje y determinar dónde termina una elemento de datos y dónde empieza otro.</span><span class="sxs-lookup"><span data-stu-id="35e5a-110">A particular XML document uses a well-defined set of starting and ending tags, arranged hierarchically, to organize the data within the message and determine where one data item ends and another begins.</span></span> <span data-ttu-id="35e5a-111">Uno o más esquemas XML correspondientes definen qué etiquetas se permiten dentro de otras etiquetas, además de en qué orden, con lo que se establece la estructura que rige los mensajes que cumplen las especificaciones.</span><span class="sxs-lookup"><span data-stu-id="35e5a-111">One or more corresponding XML schemas define which tags are allowed within other tags, in what order, thereby governing the structure of conforming messages.</span></span>  
  
 <span data-ttu-id="35e5a-112">Otra amplia categoría de formatos, conocida como formatos de archivo sin formato, la utilizan habitualmente los sistemas heredados.</span><span class="sxs-lookup"><span data-stu-id="35e5a-112">Another broad category of formats, known as flat file formats, are commonly used by legacy systems.</span></span> <span data-ttu-id="35e5a-113">Estos formatos usan una combinación de delimitadores (como caracteres de tabulación) y campos de longitud fija para determinar dónde termina un elemento de datos y dónde empieza otro.</span><span class="sxs-lookup"><span data-stu-id="35e5a-113">These formats use some combination of delimiters (such as tabs) and fixed length fields to determine where one data item ends and another begins.</span></span>  
  
 <span data-ttu-id="35e5a-114">En esta sección se proporciona información general avanzada sobre la estructura de estos dos tipos de mensajes que utiliza habitualmente BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="35e5a-114">This section provides a high-level overview of the structure of these two types of messages that are commonly handled by BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35e5a-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="35e5a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="35e5a-116">Estructura de un mensaje XML</span><span class="sxs-lookup"><span data-stu-id="35e5a-116">Structure of an XML Message</span></span>](../core/structure-of-an-xml-message.md)  
  
-   [<span data-ttu-id="35e5a-117">Estructura de un mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="35e5a-117">Structure of a Flat File Message</span></span>](../core/structure-of-a-flat-file-message.md)