---
title: Dividir un intercambio por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67bef19-77fb-47a9-88f3-ee20043b3691
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1cb3c6c912985a81a2265afa11bebc636381c5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024066"
---
# <a name="splitting-a-batched-interchange"></a><span data-ttu-id="29b63-102">Dividir un intercambio por lotes</span><span class="sxs-lookup"><span data-stu-id="29b63-102">Splitting a Batched Interchange</span></span>
<span data-ttu-id="29b63-103">En este tema se describe cómo se configura un acuerdo para procesar un intercambio EDI por lotes mediante la división de los conjuntos de transacciones que componen el intercambio.</span><span class="sxs-lookup"><span data-stu-id="29b63-103">This topic describes how to configure an agreement for processing a batched EDI interchange by splitting the transaction sets from the interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29b63-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="29b63-104">Prerequisites</span></span>  
 <span data-ttu-id="29b63-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29b63-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-receive-a-split-edi-interchange"></a><span data-ttu-id="29b63-106">Para recibir un intercambio EDI dividido</span><span class="sxs-lookup"><span data-stu-id="29b63-106">To receive a split EDI interchange</span></span>  
  
1. <span data-ttu-id="29b63-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo.</span><span class="sxs-lookup"><span data-stu-id="29b63-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node.</span></span> <span data-ttu-id="29b63-108">En el **entidades y perfiles empresariales** página, haga clic en la entidad que tenga el acuerdo que resolverá el intercambio por lotes entrante.</span><span class="sxs-lookup"><span data-stu-id="29b63-108">In the **Parties and Business Profiles** page, click the party that has the agreement that will resolve to the incoming batched interchange.</span></span> <span data-ttu-id="29b63-109">En el **acuerdo** sección de la página, haga clic en el contrato y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="29b63-109">In the **Agreement** section of the page, right-click the agreement and click **Properties**.</span></span> <span data-ttu-id="29b63-110">En el **las propiedades del acuerdo** cuadro de diálogo, en la ficha de acuerdo unidireccional (a la que se resolverá el intercambio por lotes entrante), haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29b63-110">In the **Agreement Properties** dialog box, in the one-way agreement tab (to which the inbound batched interchange will resolve), do the following:</span></span>  
  
   1.  <span data-ttu-id="29b63-111">En el **identificadores** página, asegúrese de escribir los valores correctos para que el intercambio por lotes entrante resuelva este acuerdo.</span><span class="sxs-lookup"><span data-stu-id="29b63-111">In the **Identifiers** page, make sure you enter the correct values so that the incoming batched interchange resolves to this agreement.</span></span>  
  
       -   <span data-ttu-id="29b63-112">En caso de **X12**: establezca ISA5, ISA6, ISA7 e ISA8.</span><span class="sxs-lookup"><span data-stu-id="29b63-112">In case of **X12**: Set ISA5, ISA6, ISA7, and ISA8.</span></span>  
  
       -   <span data-ttu-id="29b63-113">En caso de **Edifact**: establezca UNB2.1, UNB2.2, UNB3.1 y UNB3.2.</span><span class="sxs-lookup"><span data-stu-id="29b63-113">In case of **Edifact**: Set UNB2.1, UNB2.2, UNB3.1, and UNB3.2.</span></span>  
  
   2.  <span data-ttu-id="29b63-114">En el **configuración de Host Local** página (en **configuración de intercambio**), en **configuración del receptor** sección, para el **opción de procesamiento por lotes de entrada** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="29b63-114">In the **Local Host Settings** page (under **Interchange Settings**), under **Receiver’s Settings** section, for the **Inbound batch processing option**, select one the following options:</span></span>  
  
       -   <span data-ttu-id="29b63-115">**Dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en Error** : seleccione esta opción para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente.</span><span class="sxs-lookup"><span data-stu-id="29b63-115">**Split Interchange as Transaction Sets - suspend Transaction Sets on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="29b63-116">Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="29b63-116">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="29b63-117">Con esta opción, si uno o varios conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="29b63-117">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend only those transaction sets.</span></span>  
  
       -   <span data-ttu-id="29b63-118">**Dividir intercambio como conjuntos de transacciones: suspender intercambio en el Error** : seleccione esta opción para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente.</span><span class="sxs-lookup"><span data-stu-id="29b63-118">**Split Interchange as Transaction Sets - suspend Interchange on Error** – Select this option to specify that BizTalk Server should parse each transaction set in an interchange into a separate XML document.</span></span> <span data-ttu-id="29b63-119">Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="29b63-119">BizTalk Server will then apply the appropriate envelope to the transaction set and route the transaction set document to the MessageBox.</span></span> <span data-ttu-id="29b63-120">Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.</span><span class="sxs-lookup"><span data-stu-id="29b63-120">With this option, if one or more transaction sets in the interchange fail validation, BizTalk Server will suspend the entire interchange.</span></span>  
  
2. <span data-ttu-id="29b63-121">Cree un proyecto de Visual Studio para el lote conservado, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="29b63-121">Create a Visual Studio project for the preserved batch as follows:</span></span>  
  
   1. <span data-ttu-id="29b63-122">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un proyecto de BizTalk y agregue los esquemas de todos los mensajes del lote.</span><span class="sxs-lookup"><span data-stu-id="29b63-122">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a BizTalk project and add the schemas for all the messages within the batch.</span></span>  
  
   2. <span data-ttu-id="29b63-123">Compile e implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="29b63-123">Build and deploy the project.</span></span>  
  
3. <span data-ttu-id="29b63-124">En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de envío para enviar lotes divididos, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="29b63-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a send port to send split batches as follows:</span></span>  
  
   1.  <span data-ttu-id="29b63-125">Establecer la canalización de envío **EdiSend** o **AS2EdiSend**.</span><span class="sxs-lookup"><span data-stu-id="29b63-125">Set the send pipeline to **EdiSend** or **AS2EdiSend**.</span></span>  
  
   2.  <span data-ttu-id="29b63-126">Establezca el filtro del puerto de envío en el valor necesario para recoger cada conjunto de transacciones, por ejemplo como BTS.MessageType.</span><span class="sxs-lookup"><span data-stu-id="29b63-126">Set the filter of the send port to the value required to pick up each transaction set, for example, to BTS.MessageType.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b63-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="29b63-127">See Also</span></span>  
 <span data-ttu-id="29b63-128">[La configuración de lotes EDI](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="29b63-128">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="29b63-129">Cómo crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="29b63-129">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)