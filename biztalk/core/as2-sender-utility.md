---
title: AS2 Utilidad del remitente | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69f70e2a404c92393fb02b301b58abf2d97da2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-sender-utility"></a><span data-ttu-id="16d47-102">Utilidad del remitente de AS2</span><span class="sxs-lookup"><span data-stu-id="16d47-102">AS2 Sender Utility</span></span>
<span data-ttu-id="16d47-103">La utilidad del remitente de AS2 incluida con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite enviar un mensaje AS2 a un sitio web en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="16d47-103">The AS2 Sender utility shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to send an AS2 message to a Web site on a single computer.</span></span> <span data-ttu-id="16d47-104">Esta utilidad simula el envío de un mensaje AS2 de un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="16d47-104">This utility simulates the sending of an AS2 message from a separate computer.</span></span>  
  
 <span data-ttu-id="16d47-105">Los archivos de la utilidad del remitente de AS2 se encuentran en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.</span><span class="sxs-lookup"><span data-stu-id="16d47-105">The AS2 Sender utility files are located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16d47-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="16d47-106">Prerequisites</span></span>  
 <span data-ttu-id="16d47-107">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16d47-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="what-this-utility-does"></a><span data-ttu-id="16d47-108">Qué hace esta utilidad</span><span class="sxs-lookup"><span data-stu-id="16d47-108">What This Utility Does</span></span>  
 <span data-ttu-id="16d47-109">La utilidad del remitente de AS2 genera un mensaje AS2 con una carga EDI y envía ese mensaje a un sitio Web que utiliza el filtro ISAPI de BTSHTTPReceive.</span><span class="sxs-lookup"><span data-stu-id="16d47-109">The AS2 Sender utility builds an AS2 message with an EDI payload, and sends that message to a Web site that uses the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="16d47-110">El tutorial realiza lo siguiente de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="16d47-110">By default the tutorial does the following:</span></span>  
  
-   <span data-ttu-id="16d47-111">Envía un mensaje AS2 con el nombre X12_00401_864.edi con una carga cifrada 864 X12.</span><span class="sxs-lookup"><span data-stu-id="16d47-111">Sends an AS2 message named X12_00401_864.edi with an 864 X12-encoded payload.</span></span> <span data-ttu-id="16d47-112">Este mensaje se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.</span><span class="sxs-lookup"><span data-stu-id="16d47-112">This message is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
-   <span data-ttu-id="16d47-113">Envía un MDN asíncrono en respuesta al mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="16d47-113">Prompts an asynchronous MDN in response to the AS2 message.</span></span> <span data-ttu-id="16d47-114">Esto está determinado por el mensaje enviado y puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="16d47-114">This is determined by the message sent, and can be changed.</span></span>  
  
-   <span data-ttu-id="16d47-115">Envía el mensaje AS2 a una ubicación de recepción a través del directorio virtual de Contoso.</span><span class="sxs-lookup"><span data-stu-id="16d47-115">Sends the AS2 message to a receive location through the Contoso virtual directory.</span></span>  
  
 <span data-ttu-id="16d47-116">La utilidad se puede modificar para cambiar este comportamiento específico.</span><span class="sxs-lookup"><span data-stu-id="16d47-116">The utility can be modified to change this specific behavior.</span></span> <span data-ttu-id="16d47-117">Consulte la [cómo personalizar la utilidad del remitente de AS2](../core/as2-sender-utility.md#BKMK_Custom) sección más adelante.</span><span class="sxs-lookup"><span data-stu-id="16d47-117">See the [How to Customize the AS2 Sender Utility](../core/as2-sender-utility.md#BKMK_Custom) section below.</span></span>  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a><span data-ttu-id="16d47-118">Cómo configurar una solución mediante la utilidad del remitente de AS2</span><span class="sxs-lookup"><span data-stu-id="16d47-118">How to Set Up a Solution Using the AS2 Sender Utility</span></span>  
 <span data-ttu-id="16d47-119">Para configurar una solución con el fin de utilizar la utilidad del remitente de AS2, necesita realizar lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="16d47-119">To set up a solution to use the AS2 Sender utility, you need to do the following.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16d47-120">Estos pasos se muestran en el tutorial de AS2 y en los dos tutoriales sobre el envío de AS2.</span><span class="sxs-lookup"><span data-stu-id="16d47-120">These steps are demonstrated in the AS2 Tutorial and two AS2 send-side walkthroughs.</span></span> <span data-ttu-id="16d47-121">Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md), [tutorial (AS2): enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md), y [tutorial (AS2): enviar EDI a través de AS2 con un asincrónico MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span><span class="sxs-lookup"><span data-stu-id="16d47-121">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md), [Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md), and [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  
  
-   <span data-ttu-id="16d47-122">Habilite el filtro ISAPI de BTSHTTPReceive.</span><span class="sxs-lookup"><span data-stu-id="16d47-122">Enable the BTSHTTPReceive ISAPI filter.</span></span>  
  
-   <span data-ttu-id="16d47-123">Configure una página Web y una ubicación de recepción para recibir el mensaje de AS2.</span><span class="sxs-lookup"><span data-stu-id="16d47-123">Configure a Web page and a receive location to receive the AS2 message.</span></span> <span data-ttu-id="16d47-124">En la utilidad del remitente de AS2 predeterminada, la página Web es la de Contoso.</span><span class="sxs-lookup"><span data-stu-id="16d47-124">In the default AS2 Sender utility, the Web page is the Contoso Web page.</span></span>  
  
-   <span data-ttu-id="16d47-125">Implemente el esquema para el intercambio EDI que vaya a enviar como carga del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="16d47-125">Deploy the schema for the EDI interchange that you will send as a payload of the AS2 message.</span></span>  
  
-   <span data-ttu-id="16d47-126">Establezca las propiedades de entidad de EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="16d47-126">Set the appropriate AS2 and EDI party properties.</span></span>  
  
##  <span data-ttu-id="16d47-127"><a name="BKMK_Custom"></a>Cómo personalizar la utilidad del remitente de AS2</span><span class="sxs-lookup"><span data-stu-id="16d47-127"><a name="BKMK_Custom"></a> How to Customize the AS2 Sender Utility</span></span>  
 <span data-ttu-id="16d47-128">La utilidad del remitente de AS2 predeterminada envía un intercambio de prueba EDI 864 a través de AS2 a una página Web de Contoso mediante el filtro ISAPI de BTSHTTPReceive.</span><span class="sxs-lookup"><span data-stu-id="16d47-128">The default AS2 Sender utility sends a test 864 EDI interchange over AS2 to a Contoso Web page using the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="16d47-129">El mensaje AS2, con el nombre X12_00401_864.edi, solicita un MDN asíncrono.</span><span class="sxs-lookup"><span data-stu-id="16d47-129">The AS2 message, named X12_00401_864.edi, prompts an asynchronous MDN.</span></span> <span data-ttu-id="16d47-130">El código de la utilidad del remitente de AS2 se encuentra en HttpSender.cs en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender.</span><span class="sxs-lookup"><span data-stu-id="16d47-130">The AS2 Sender utility code is located in HttpSender.cs in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender folder.</span></span> <span data-ttu-id="16d47-131">La siguiente línea de código de HttpSender.cs envía el archivo de prueba 864:</span><span class="sxs-lookup"><span data-stu-id="16d47-131">The following line of code in HttpSender.cs sends the default 864 test file:</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  <span data-ttu-id="16d47-132">Puede modificar esta línea con un nombre de archivo distinto y una ruta diferente.</span><span class="sxs-lookup"><span data-stu-id="16d47-132">You can modify this line with a different file name and different path.</span></span>  
  
 <span data-ttu-id="16d47-133">La siguiente línea en HttpSender.cs envía un mensaje de AS2 con el nombre X12_00401_864-Sync.edi.</span><span class="sxs-lookup"><span data-stu-id="16d47-133">The following line in HttpSender.cs sends an AS2 message named X12_00401_864-Sync.edi.</span></span> <span data-ttu-id="16d47-134">Este mensaje solicita un MDN sincrónico.</span><span class="sxs-lookup"><span data-stu-id="16d47-134">This message prompts a synchronous MDN.</span></span> <span data-ttu-id="16d47-135">De forma predeterminada, se hace referencia a esta línea de código en HttpSender.cs en favor de la línea que envía X12_00401_864.edi.</span><span class="sxs-lookup"><span data-stu-id="16d47-135">By default, this line of code in HttpSender.cs is commented out in favor of the line that sends X12_00401_864.edi.</span></span> <span data-ttu-id="16d47-136">Para enviar X12_00401_864-Sync.edi, elimine el comentario de la línea X12_00401_864-Sync.edi y convierte en comentario la línea X12_00401_864.edi.</span><span class="sxs-lookup"><span data-stu-id="16d47-136">To send X12_00401_864-Sync.edi, uncomment the X12_00401_864-Sync.edi line and comment out the X12_00401_864.edi line.</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 <span data-ttu-id="16d47-137">La siguiente línea de código en HttpSender.cs envía el mensaje a la página web de Contoso:</span><span class="sxs-lookup"><span data-stu-id="16d47-137">The following line of code in HttpSender.cs sends the message to the Contoso Web page:</span></span>  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  <span data-ttu-id="16d47-138">Puede modificar esta línea con un filtro ISAPI y un directorio virtual distinto.</span><span class="sxs-lookup"><span data-stu-id="16d47-138">You can modify this line with a different virtual directory and ISAPI filter.</span></span>  
  
### <a name="to-build-the-as2-sender-sample"></a><span data-ttu-id="16d47-139">Para generar el ejemplo del remitente de AS2</span><span class="sxs-lookup"><span data-stu-id="16d47-139">To build the AS2 Sender sample</span></span>  
  
1.  <span data-ttu-id="16d47-140">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto Sender.csproj en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.</span><span class="sxs-lookup"><span data-stu-id="16d47-140">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  
  
2.  <span data-ttu-id="16d47-141">Abra HttpSender.cs en el proyecto del remitente y personalice el código del remitente con la página Web de recepción apropiada y la ruta y nombre de archivo EDI apropiados.</span><span class="sxs-lookup"><span data-stu-id="16d47-141">Open HttpSender.cs in the Sender project, and customize the Sender code with the appropriate receiving Web page and the appropriate EDI filename and path.</span></span>  
  
3.  <span data-ttu-id="16d47-142">Haga clic en el proyecto del remitente y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="16d47-142">Right-click the Sender project, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="16d47-143">Haga clic en **firma** en la consola de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="16d47-143">Click **Signing** in the left-hand console.</span></span> <span data-ttu-id="16d47-144">Asegúrese de que **firmar el ensamblado** está seleccionada, y el archivo de clave de nombre seguro se establece en **Sender.snk**.</span><span class="sxs-lookup"><span data-stu-id="16d47-144">Ensure that **Sign the assembly** is selected, and the strong name key file is set to **Sender.snk**.</span></span> <span data-ttu-id="16d47-145">Asegúrese de que **Retrasar firma sólo** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="16d47-145">Make sure that **Delay sign only** is cleared.</span></span>  
  
5.  <span data-ttu-id="16d47-146">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16d47-146">Build the project.</span></span>  
  
### <a name="to-run-the-as2-sender-sample"></a><span data-ttu-id="16d47-147">Para ejecutar el ejemplo del remitente de AS2</span><span class="sxs-lookup"><span data-stu-id="16d47-147">To run the AS2 Sender sample</span></span>  
  
1.  <span data-ttu-id="16d47-148">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="16d47-148">Open a command prompt.</span></span> <span data-ttu-id="16d47-149">Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="16d47-149">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span>  
  
2.  <span data-ttu-id="16d47-150">ENTRAR **Sender.exe**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="16d47-150">Enter **Sender.exe**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="16d47-151">Compruebe que visualiza un mensaje que indica que un mensaje AS2 se ha enviado correctamente y, a continuación, cierre el símbolo de sistema.</span><span class="sxs-lookup"><span data-stu-id="16d47-151">Verify that you see a message indicating that an AS2 message was successfully sent, and then close the command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d47-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="16d47-152">See Also</span></span>  
 <span data-ttu-id="16d47-153">[Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="16d47-153">[Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md) </span></span>  
 <span data-ttu-id="16d47-154">[Tutorial (AS2): Enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span><span class="sxs-lookup"><span data-stu-id="16d47-154">[Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span></span>  
 [<span data-ttu-id="16d47-155">Tutorial (AS2): Enviar EDI a través de AS2 con un MDN asíncrono</span><span class="sxs-lookup"><span data-stu-id="16d47-155">Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN</span></span>](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)