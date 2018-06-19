---
title: 'Paso 3: Configurar un puerto de envío de archivos unidireccional | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceb055f0d4d41eb82eb79cb549b082212fd1bbd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277332"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a><span data-ttu-id="ef06a-102">Paso 3: Configurar un puerto de envío de archivos unidireccional</span><span class="sxs-lookup"><span data-stu-id="ef06a-102">Step 3: Configure a One-way FILE Send Port</span></span>
<span data-ttu-id="ef06a-103">En este paso, configurará un puerto de envío de archivos unidireccional que consume el mensaje de respuesta recibido de la interfaz REST y lo copia en una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="ef06a-103">In this step you configure a one-way FILE send port that consumes the response message received from the REST interface and copies it to a file location.</span></span>  
  
### <a name="to-configure-a-file-send-port"></a><span data-ttu-id="ef06a-104">Procedimiento para configurar un puerto de envío de FILE</span><span class="sxs-lookup"><span data-stu-id="ef06a-104">To configure a FILE send port</span></span>  
  
1.  <span data-ttu-id="ef06a-105">Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **estático Puerto de envío unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ef06a-106">En la ficha General, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef06a-106">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="ef06a-107">Use</span><span class="sxs-lookup"><span data-stu-id="ef06a-107">Use this</span></span>|<span data-ttu-id="ef06a-108">Para</span><span class="sxs-lookup"><span data-stu-id="ef06a-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ef06a-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ef06a-109">**Name**</span></span>|<span data-ttu-id="ef06a-110">Tipo de **SendPortOutAzureMarketPlaceData**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-110">Type **SendPortOutAzureMarketPlaceData**.</span></span>|  
    |<span data-ttu-id="ef06a-111">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ef06a-111">**Type**</span></span>|<span data-ttu-id="ef06a-112">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-112">Select **FILE**.</span></span>|  
    |<span data-ttu-id="ef06a-113">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="ef06a-113">**Send handler**</span></span>|<span data-ttu-id="ef06a-114">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-114">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="ef06a-115">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="ef06a-115">**Send pipeline**</span></span>|<span data-ttu-id="ef06a-116">Seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-116">Select **PassThruTransmit**.</span></span>|  
  
     <span data-ttu-id="ef06a-117">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-117">Click **Configure**.</span></span>  
  
3.  <span data-ttu-id="ef06a-118">Desde Propiedades de transporte de archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef06a-118">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="ef06a-119">Use</span><span class="sxs-lookup"><span data-stu-id="ef06a-119">Use this</span></span>|<span data-ttu-id="ef06a-120">Para</span><span class="sxs-lookup"><span data-stu-id="ef06a-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ef06a-121">**Carpeta de recepción**</span><span class="sxs-lookup"><span data-stu-id="ef06a-121">**Receive folder**</span></span>|<span data-ttu-id="ef06a-122">Escriba una ubicación en la que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ef06a-122">Type a location where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copies the response message.</span></span>|  
    |<span data-ttu-id="ef06a-123">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="ef06a-123">**File name**</span></span>|<span data-ttu-id="ef06a-124">Conservar`%MessageID%.xml`</span><span class="sxs-lookup"><span data-stu-id="ef06a-124">Retain `%MessageID%.xml`</span></span>|  
  
4.  <span data-ttu-id="ef06a-125">En el **filtros** ficha, especifique el filtro para consumir todos los mensajes que se escriben en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensaje mediante el puerto de recepción que creó en [paso 2: configurar un puerto de envío de WCF-WebHttp de bidireccional](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="ef06a-125">On the **Filters** tab, specify the filter to consume all messages that are written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Message Box database by the receive port you created in [Step 2: Configure a Two-way WCF-WebHttp Send Port](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="ef06a-126">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="ef06a-126">**Property**</span></span>|<span data-ttu-id="ef06a-127">Establecido en **BTS. SPName**</span><span class="sxs-lookup"><span data-stu-id="ef06a-127">Set to **BTS.SPName**</span></span>|  
    |<span data-ttu-id="ef06a-128">**Operador**</span><span class="sxs-lookup"><span data-stu-id="ef06a-128">**Operator**</span></span>|<span data-ttu-id="ef06a-129">Establecido en**==**</span><span class="sxs-lookup"><span data-stu-id="ef06a-129">Set to **==**</span></span>|  
    |<span data-ttu-id="ef06a-130">**Valor**</span><span class="sxs-lookup"><span data-stu-id="ef06a-130">**Value**</span></span>|<span data-ttu-id="ef06a-131">Establecido en`SendPortRESTAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="ef06a-131">Set to `SendPortRESTAzureMarketPlace`</span></span>|  
  
5.  <span data-ttu-id="ef06a-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef06a-132">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef06a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef06a-133">See Also</span></span>  
 [<span data-ttu-id="ef06a-134">Tutorial 5: Invocar una interfaz REST con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ef06a-134">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)