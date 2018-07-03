---
title: 'Paso 6: Configurar un puerto de envío para enviar datos a su organización | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b38182ff9f46688447e11f444ab543d8e0aa1d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975181"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a><span data-ttu-id="a7051-102">Paso 6: Configurar un puerto de envío para enviar datos a su organización</span><span class="sxs-lookup"><span data-stu-id="a7051-102">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>
<span data-ttu-id="a7051-103">![Paso 6 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span><span class="sxs-lookup"><span data-stu-id="a7051-103">![Step 6 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span></span>  

 <span data-ttu-id="a7051-104">En este paso, configurará un puerto de envío para enviar el mensaje 850 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a la entidad OrderSystem que representa la organización.</span><span class="sxs-lookup"><span data-stu-id="a7051-104">In this step you configure a send port to send the 850 message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the OrderSystem party that represents your organization.</span></span> <span data-ttu-id="a7051-105">Este puerto de envío aplica la **Inbound4010850_to_OrderFile** mapa, transformar el mensaje de salida desde el formato del mensaje de entrada al formato especificado en el mapa.</span><span class="sxs-lookup"><span data-stu-id="a7051-105">This send port applies the **Inbound4010850_to_OrderFile** map, transforming the output message from the format of the input message to the format specified in the map.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="a7051-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a7051-106">Prerequisites</span></span>  
 <span data-ttu-id="a7051-107">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7051-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-configure-a-send-port-for-the-850-message"></a><span data-ttu-id="a7051-108">Para configurar un puerto de envío para el mensaje 850.</span><span class="sxs-lookup"><span data-stu-id="a7051-108">To configure a send port for the 850 message</span></span>  

1. <span data-ttu-id="a7051-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **canalizaciones**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Pipelines**, and then click **Refresh**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7051-110">Puede que sea necesaria la actualización de la lista de canalizaciones para poder seleccionar SendOrderFilePipeline para el puerto de envío que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="a7051-110">Refreshing the pipelines list may be necessary to be able to select the SendOrderFilePipeline for the send port that you will create.</span></span>  

2. <span data-ttu-id="a7051-111">Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="a7051-111">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="a7051-112">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7051-112">In the **Send Port Properties** dialog box, do the following:</span></span>  

   |<span data-ttu-id="a7051-113">Use</span><span class="sxs-lookup"><span data-stu-id="a7051-113">Use this</span></span>|<span data-ttu-id="a7051-114">Para</span><span class="sxs-lookup"><span data-stu-id="a7051-114">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="a7051-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a7051-115">**Name**</span></span>|<span data-ttu-id="a7051-116">Escriba `toOrderSystem`.</span><span class="sxs-lookup"><span data-stu-id="a7051-116">Enter `toOrderSystem`.</span></span>|  
   |<span data-ttu-id="a7051-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a7051-117">**Type**</span></span>|<span data-ttu-id="a7051-118">Seleccione **archivo**.</span><span class="sxs-lookup"><span data-stu-id="a7051-118">Select **FILE**.</span></span>|  
   |<span data-ttu-id="a7051-119">**Configurar**</span><span class="sxs-lookup"><span data-stu-id="a7051-119">**Configure**</span></span>|<span data-ttu-id="a7051-120">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-120">Click **Configure**.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="a7051-121">El tipo de transporte del puerto de envío es Archivo ya que el mensaje de prueba es un archivo sin formato que va a enviarse a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="a7051-121">The transport type of the send port is FILE because the test message is a flat file to be delivered into a folder.</span></span>  

4. <span data-ttu-id="a7051-122">En el **propiedades de transporte de archivo** diálogo cuadro, haga lo siguiente y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="a7051-122">In the **FILE Transport Properties** dialog box, do the following and then click **OK**:</span></span>  


   |        <span data-ttu-id="a7051-123">Use</span><span class="sxs-lookup"><span data-stu-id="a7051-123">Use this</span></span>        |                                                                                                               <span data-ttu-id="a7051-124">Para</span><span class="sxs-lookup"><span data-stu-id="a7051-124">To do this</span></span>                                                                                                               |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="a7051-125">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="a7051-125">**Destination folder**</span></span> | <span data-ttu-id="a7051-126">Haga clic en **examinar**y en el **Buscar carpeta** cuadro de diálogo, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ escenario A\toOrderSystem</span><span class="sxs-lookup"><span data-stu-id="a7051-126">Click **Browse**, and in the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ Scenario A\toOrderSystem</span></span> |
   |     <span data-ttu-id="a7051-127">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="a7051-127">**File name**</span></span>      |                                                                                            <span data-ttu-id="a7051-128">Escriba `%MessageID%.txt`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-128">Enter `%MessageID%.txt`, and then click **OK**.</span></span>                                                                                             |

   > [!NOTE]
   >  <span data-ttu-id="a7051-129">El valor establecido para el **nombre de archivo** propiedad asegura que el archivo de salida tendrá una extensión. txt.</span><span class="sxs-lookup"><span data-stu-id="a7051-129">The value set for the **File name** property ensures that the output file will have a .txt extension.</span></span>  

5. <span data-ttu-id="a7051-130">En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **SendOrderFilePipeline**.</span><span class="sxs-lookup"><span data-stu-id="a7051-130">In the **Send Port Properties** dialog box, for **Send pipeline**, select **SendOrderFilePipeline**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7051-131">El **SendOrderFilePipeline** enviar canalización incluye un ensamblador de archivo sin formato que ensambla el archivo de salida .txt con datos asignados desde el mensaje de entrada 850.</span><span class="sxs-lookup"><span data-stu-id="a7051-131">The **SendOrderFilePipeline** send pipeline includes a flat-file assembler that assembles the .txt output file, using data mapped from the input 850 message.</span></span> <span data-ttu-id="a7051-132">Dado que el archivo de salida es un archivo .txt, no aparecerá en el informe de estado de intercambios y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="a7051-132">Since the output file is a .txt file, it will not show up in the Interchange/ACK status report.</span></span>  

6. <span data-ttu-id="a7051-133">En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7051-133">In the console tree, click **Filters**, and then do the following:</span></span>  

   |<span data-ttu-id="a7051-134">Use</span><span class="sxs-lookup"><span data-stu-id="a7051-134">Use this</span></span>|<span data-ttu-id="a7051-135">Para</span><span class="sxs-lookup"><span data-stu-id="a7051-135">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="a7051-136">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a7051-136">**Property**</span></span>|<span data-ttu-id="a7051-137">Seleccione **BTS. ReceivePortName**.</span><span class="sxs-lookup"><span data-stu-id="a7051-137">Select **BTS.ReceivePortName**.</span></span>|  
   |<span data-ttu-id="a7051-138">**Operador**</span><span class="sxs-lookup"><span data-stu-id="a7051-138">**Operator**</span></span>|<span data-ttu-id="a7051-139">Seleccione **==**.</span><span class="sxs-lookup"><span data-stu-id="a7051-139">Select **==**.</span></span>|  
   |<span data-ttu-id="a7051-140">**Value**</span><span class="sxs-lookup"><span data-stu-id="a7051-140">**Value**</span></span>|<span data-ttu-id="a7051-141">Escriba `ReceiveEDI_fromTHEM_A`.</span><span class="sxs-lookup"><span data-stu-id="a7051-141">Enter `ReceiveEDI_fromTHEM_A`.</span></span>|  
   |<span data-ttu-id="a7051-142">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="a7051-142">**Group by**</span></span>|<span data-ttu-id="a7051-143">Seleccione **y**.</span><span class="sxs-lookup"><span data-stu-id="a7051-143">Select **And**.</span></span>|  
   |<span data-ttu-id="a7051-144">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="a7051-144">**Property**</span></span>|<span data-ttu-id="a7051-145">En la línea siguiente, seleccione **BTS. MessageType**.</span><span class="sxs-lookup"><span data-stu-id="a7051-145">On the next line, select **BTS.MessageType**.</span></span>|  
   |<span data-ttu-id="a7051-146">**Operador**</span><span class="sxs-lookup"><span data-stu-id="a7051-146">**Operator**</span></span>|<span data-ttu-id="a7051-147">Seleccione **! =**.</span><span class="sxs-lookup"><span data-stu-id="a7051-147">Select **!=**.</span></span>|  
   |<span data-ttu-id="a7051-148">**Value**</span><span class="sxs-lookup"><span data-stu-id="a7051-148">**Value**</span></span>|<span data-ttu-id="a7051-149">Escriba `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span><span class="sxs-lookup"><span data-stu-id="a7051-149">Enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="a7051-150">El filtro asegura que el puerto de envío tomará los mensajes que se recibieron en la ubicación de recepción Receive_EDI_fromTHEM_A y que el puerto de envío no tomará las confirmaciones 997, si no únicamente los mensajes 850.</span><span class="sxs-lookup"><span data-stu-id="a7051-150">The filter ensures that the send port will pick up messages that were received by the Receive_EDI_fromTHEM_A receive location, and that the send port will not pick up 997 acknowledgments, but will pick only 850 messages.</span></span>  

7. <span data-ttu-id="a7051-151">En el árbol de consola, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="a7051-151">In the console tree, click **OutboundMaps**.</span></span> <span data-ttu-id="a7051-152">En el **asignaciones de salida** panel, en el **mapa** columna, en la primera fila, seleccione **Inbound4010850_to_OrderFile**.</span><span class="sxs-lookup"><span data-stu-id="a7051-152">In the **Outbound Maps** pane, in the **Map** column, on the first row, select **Inbound4010850_to_OrderFile**.</span></span> <span data-ttu-id="a7051-153">(La entrada en el **documento de origen** columna será X12_00401_850.)</span><span class="sxs-lookup"><span data-stu-id="a7051-153">(The entry in the **Source Document** column will be X12_00401_850.)</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7051-154">Este paso garantiza que el mensaje de salida conste solo de los datos asignados desde el mensaje de entrada según el **Inbound4010850_to_OrderFile** mapa.</span><span class="sxs-lookup"><span data-stu-id="a7051-154">This step ensures that the output message will consist only of the data mapped from the input message according to the **Inbound4010850_to_OrderFile** map.</span></span>  

8. <span data-ttu-id="a7051-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7051-155">Click **OK**.</span></span>  

9. <span data-ttu-id="a7051-156">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a7051-156">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Send Ports**.</span></span> <span data-ttu-id="a7051-157">Haga clic en **toOrderSystem**y, a continuación, haga clic en **iniciar** para dar de alta e iniciar el puerto.</span><span class="sxs-lookup"><span data-stu-id="a7051-157">Right-click **toOrderSystem**, and then click **Start** to enlist and start the port.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="a7051-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a7051-158">Next Steps</span></span>  
 <span data-ttu-id="a7051-159">Configurar el puerto de envío (**toTHEM_997**) para enviar el 997 confirmación de nuevo a Fabrikam, tal como se describe en [paso 7: configurar un puerto de envío para enviar la confirmación a su socio comercial](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md).</span><span class="sxs-lookup"><span data-stu-id="a7051-159">You configure the send port (**toTHEM_997**) to send the 997 acknowledgment back to Fabrikam, as described in [Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="a7051-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7051-160">See Also</span></span>  
 [<span data-ttu-id="a7051-161">Configuración de un puerto de envío estático para enviar intercambios y confirmaciones de EDI</span><span class="sxs-lookup"><span data-stu-id="a7051-161">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)