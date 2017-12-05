---
title: Generar un esquema XSD para mensajes JSON | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88caf75d312179cd45bb1b3b421d6c2c7f25c2a8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="generate-an-xsd-schema-for-json-message"></a><span data-ttu-id="50d78-102">Generar un esquema XSD para mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="50d78-102">Generate an XSD schema for JSON message</span></span>
> [!NOTE]
>  <span data-ttu-id="50d78-103">Este tutorial solo se aplica a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="50d78-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="50d78-104">En esta solución, una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje JSON.</span><span class="sxs-lookup"><span data-stu-id="50d78-104">In this solution, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application receives a JSON message.</span></span> <span data-ttu-id="50d78-105">Para que la aplicación pueda procesar el mensaje, debe convertirlo en esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="50d78-105">Before the application can process the message, it must be converted to an XSD schema.</span></span> <span data-ttu-id="50d78-106">Para ello, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un asistente para esquemas JSON que crea un esquema XSD a partir de un mensaje JSON.</span><span class="sxs-lookup"><span data-stu-id="50d78-106">To do so, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a JSON Schema Wizard that creates an XSD schema from a JSON message.</span></span>  
  
1.  <span data-ttu-id="50d78-107">En Visual Studio, cree un nuevo proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50d78-107">In Visual Studio, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="50d78-108">En el Explorador de soluciones, haga clic en el nombre del proyecto > **agregar** > **nuevo elemento** > **Asistente para esquemas JSON**.</span><span class="sxs-lookup"><span data-stu-id="50d78-108">In the Solution Explorer, right-click the project name > **Add** > **New Item** > **JSON Schema Wizard**.</span></span> <span data-ttu-id="50d78-109">Proporcione un nombre para el esquema (`PO.xsd`) y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="50d78-109">Provide a name for the schema (`PO.xsd`), and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="50d78-110">En el Asistente para esquemas de JSON, en la página de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="50d78-110">In the JSON Schema Wizard, on the welcome page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="50d78-111">En la página Información del esquema JSON, proporcione la ubicación del archivo de pedido de compra JSON que se envía a la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50d78-111">In the JSON Schema Information page, provide the location of the JSON purchase order file that is sent to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="50d78-112">Proporcione un nombre de nodo raíz, un espacio de nombres de destino y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="50d78-112">Provide a root node name, a target namespace, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="50d78-113">![Esquema XSD generado para JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span><span class="sxs-lookup"><span data-stu-id="50d78-113">![Generated XSD schema for JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span></span>  
  
5.  <span data-ttu-id="50d78-114">Con esto se agrega un esquema con el nombre especificado al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50d78-114">A schema with the specified name is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="50d78-115">El archivo de esquema generado (**PO.xsd**) también se proporciona con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50d78-115">The generated schema file (**PO.xsd**) is also provided with the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d78-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d78-116">See Also</span></span>  
 [<span data-ttu-id="50d78-117">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="50d78-117">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)