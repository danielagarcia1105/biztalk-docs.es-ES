---
title: Crear canalizaciones mediante el Diseñador de canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b693a4e8df20a7f39f81fb820810c1191ef637
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238052"
---
# <a name="creating-pipelines-using-pipeline-designer"></a><span data-ttu-id="9217c-102">Crear canalizaciones mediante el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9217c-102">Creating Pipelines Using Pipeline Designer</span></span>
<span data-ttu-id="9217c-103">Microsoft BizTalk Server trabaja principalmente con el formato de documentos XML.</span><span class="sxs-lookup"><span data-stu-id="9217c-103">Microsoft BizTalk Server works mainly with the XML document format.</span></span> <span data-ttu-id="9217c-104">Para que un mensaje pueda sacar el máximo partido del procesamiento del servidor BizTalk Server, a menudo hay que realizar una conversión de su formato nativo a su equivalente XML.</span><span class="sxs-lookup"><span data-stu-id="9217c-104">For a message to take full advantage of BizTalk Server processing, it must often be transformed from its native format into its XML representation.</span></span> <span data-ttu-id="9217c-105">Las canalizaciones del servidor BizTalk Server llevan a cabo esta conversión, así como otras acciones relacionadas específicamente con datos (como cifrado o descifrado de datos, promoción de propiedades, etc.) en mensajes entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="9217c-105">BizTalk Server pipelines perform this transformation, as well as other data-specific actions (such as data encryption or decryption, property promotion, and so on) on incoming and outgoing messages.</span></span> <span data-ttu-id="9217c-106">En esta sección se proporciona información conceptual y específica de tareas sobre las canalizaciones y el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="9217c-106">This section provides conceptual and task-specific information about pipelines and Pipeline Designer.</span></span>  
  
 <span data-ttu-id="9217c-107">El objetivo de una canalización es preparar un mensaje para que el servidor lo procese una vez que un adaptador lo ha recibido o preparar un mensaje para enviarlo una vez que el servidor lo ha procesado.</span><span class="sxs-lookup"><span data-stu-id="9217c-107">The purpose of a pipeline is to prepare a message for processing by the server after being received by an adapter or to prepare a message for sending after being processed by the server.</span></span>  
  
 <span data-ttu-id="9217c-108">Las canalizaciones suelen llevar a cabo:</span><span class="sxs-lookup"><span data-stu-id="9217c-108">Pipelines commonly perform:</span></span>  
  
-   <span data-ttu-id="9217c-109">Normalización de datos de varios formatos a XML.</span><span class="sxs-lookup"><span data-stu-id="9217c-109">Data normalization from various formats to XML.</span></span>  
  
-   <span data-ttu-id="9217c-110">Transformación de datos de XML a varios formatos.</span><span class="sxs-lookup"><span data-stu-id="9217c-110">Data transformation from XML to various formats.</span></span>  
  
-   <span data-ttu-id="9217c-111">Promoción y degradación de propiedades</span><span class="sxs-lookup"><span data-stu-id="9217c-111">Property promotion and demotion.</span></span>  
  
-   <span data-ttu-id="9217c-112">Desensamblado y ensamblado de documentos.</span><span class="sxs-lookup"><span data-stu-id="9217c-112">Document disassembly and assembly.</span></span>  
  
-   <span data-ttu-id="9217c-113">Descodificación y codificación de documentos.</span><span class="sxs-lookup"><span data-stu-id="9217c-113">Document decoding and encoding.</span></span>  
  
-   <span data-ttu-id="9217c-114">Descifrado y cifrado de documentos.</span><span class="sxs-lookup"><span data-stu-id="9217c-114">Document decryption and encryption.</span></span>  
  
-   <span data-ttu-id="9217c-115">Comprobación de firma digital y firma de documentos.</span><span class="sxs-lookup"><span data-stu-id="9217c-115">Document signing and digital signature verification.</span></span>  
  
 <span data-ttu-id="9217c-116">La ilustración que aparece a continuación muestra el flujo de trabajo que conlleva el procesamiento de un mensaje mediante canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="9217c-116">The following figure shows the workflow involved in processing a message by using pipelines.</span></span>  
  
 <span data-ttu-id="9217c-117">![Diagrama de flujo de trabajo para procesar un mensaje. ] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="9217c-117">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
<span data-ttu-id="9217c-118">Representación del flujo de trabajo de procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9217c-118">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="9217c-119">Como se observa en la ilustración, el mensaje se pasa del adaptador a la canalización de recepción, donde se convierte en XML.</span><span class="sxs-lookup"><span data-stu-id="9217c-119">As shown in the figure, the message is passed from the adapter to the receive pipeline where it is transformed to XML.</span></span> <span data-ttu-id="9217c-120">A continuación, el mensaje puede ser utilizado por orquestaciones o pasado a una canalización de envío y, seguidamente, a un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="9217c-120">The message can then be used by orchestrations, or passed to a send pipeline, and then to a send adapter.</span></span>  
  
 <span data-ttu-id="9217c-121">Para obtener información sobre cómo usar métodos abreviados de teclado para el Diseñador de canalizaciones, consulte [métodos abreviados de teclado del Diseñador de canalización](../core/pipeline-designer-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9217c-121">For information about using the keyboard shortcuts for Pipeline Designer, see [Pipeline Designer Keyboard Shortcuts](../core/pipeline-designer-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9217c-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9217c-122">In This Section</span></span>  
  
-   [<span data-ttu-id="9217c-123">Acerca de las canalizaciones, fases y componentes</span><span class="sxs-lookup"><span data-stu-id="9217c-123">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)  
  
-   [<span data-ttu-id="9217c-124">Utilizando el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9217c-124">Using Pipeline Designer</span></span>](../core/using-pipeline-designer.md)  
  
-   [<span data-ttu-id="9217c-125">Crear canalizaciones con el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9217c-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [<span data-ttu-id="9217c-126">Configurar componentes de canalización nativos</span><span class="sxs-lookup"><span data-stu-id="9217c-126">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)  
  
-   [<span data-ttu-id="9217c-127">Cómo implementar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9217c-127">How to Deploy Pipelines</span></span>](../core/how-to-deploy-pipelines.md)  
  
-   [<span data-ttu-id="9217c-128">Cómo proteger canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9217c-128">How to Secure Pipelines</span></span>](../core/how-to-secure-pipelines.md)