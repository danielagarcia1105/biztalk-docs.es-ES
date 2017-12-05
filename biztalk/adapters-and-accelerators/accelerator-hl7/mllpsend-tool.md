---
title: Herramienta de MllpSend | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9b666b019fe7dc415f28c0dd01522b728b149c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mllpsend-tool"></a><span data-ttu-id="37a85-102">Herramienta MllpSend</span><span class="sxs-lookup"><span data-stu-id="37a85-102">MllpSend Tool</span></span>
<span data-ttu-id="37a85-103">Puede utilizar la herramienta MllpSend para enviar datos a un MLLP la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="37a85-103">You can use the MllpSend tool to send data to an MLLP receive location.</span></span>  
  
 <span data-ttu-id="37a85-104">Instalar esta herramienta a través de la [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] procedimiento de instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="37a85-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="37a85-105">Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial.</span><span class="sxs-lookup"><span data-stu-id="37a85-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="37a85-106">En la pantalla instalación personalizada, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="37a85-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="37a85-107">Para obtener más información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span><span class="sxs-lookup"><span data-stu-id="37a85-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="37a85-108">El programa de instalación de BTAHL7 instala esta herramienta en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7\SDK\MLLP utilidades.</span><span class="sxs-lookup"><span data-stu-id="37a85-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="37a85-109">Use esta herramienta en el [-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), el [Tutorial Interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), el [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)y el [mensaje enriquecimiento Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="37a85-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="37a85-110">Si ha instalado [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a través de la instalación predeterminada y no se ha instalado el Testtools MLLP (incluidos MllpSend y MllpReceive), no podrá probar los resultados del tutoriales.</span><span class="sxs-lookup"><span data-stu-id="37a85-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLP Testtools (including MllpSend and MllpReceive), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="37a85-111">Uso de la herramienta</span><span class="sxs-lookup"><span data-stu-id="37a85-111">Tool Usage</span></span>  
 <span data-ttu-id="37a85-112">A continuación muestra la sintaxis usada para invocar esta herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="37a85-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="37a85-113">En la tabla siguiente describe cada parte de la sintaxis que se utiliza la herramienta MllpSend.</span><span class="sxs-lookup"><span data-stu-id="37a85-113">The following table describes each part of the syntax the MllpSend tool uses.</span></span>  
  
|<span data-ttu-id="37a85-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37a85-114">Syntax</span></span>|<span data-ttu-id="37a85-115">Description</span><span class="sxs-lookup"><span data-stu-id="37a85-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="37a85-116">**/?**</span><span class="sxs-lookup"><span data-stu-id="37a85-116">**/?**</span></span>|<span data-ttu-id="37a85-117">Muestra la Ayuda en la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="37a85-117">Displays Help in the Command Prompt window.</span></span>|  
|<span data-ttu-id="37a85-118">**/I \<IP\>**</span><span class="sxs-lookup"><span data-stu-id="37a85-118">**/I \<IP\>**</span></span>|<span data-ttu-id="37a85-119">Indica la dirección que se envía a.</span><span class="sxs-lookup"><span data-stu-id="37a85-119">Denotes the address to send to.</span></span> <span data-ttu-id="37a85-120">El valor predeterminado es localhost.</span><span class="sxs-lookup"><span data-stu-id="37a85-120">The default value is localhost.</span></span>|  
|<span data-ttu-id="37a85-121">**/P \<PUERTO\>**</span><span class="sxs-lookup"><span data-stu-id="37a85-121">**/P \<PORT\>**</span></span>|<span data-ttu-id="37a85-122">Indica el número de puerto para enviar a.</span><span class="sxs-lookup"><span data-stu-id="37a85-122">Denotes the port number to send to.</span></span> <span data-ttu-id="37a85-123">El valor predeterminado es **11000**.</span><span class="sxs-lookup"><span data-stu-id="37a85-123">The default value is **11000**.</span></span>|  
|<span data-ttu-id="37a85-124">**/F**</span><span class="sxs-lookup"><span data-stu-id="37a85-124">**/F**</span></span>|<span data-ttu-id="37a85-125">Envía el contenido del archivo de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="37a85-125">Sends content of the file FILENAME.</span></span>|  
|<span data-ttu-id="37a85-126">**/ REPETICIÓN\<n\>**</span><span class="sxs-lookup"><span data-stu-id="37a85-126">**/REPEAT \<n\>**</span></span>|<span data-ttu-id="37a85-127">Envía el mismo mensaje  *n*  veces.</span><span class="sxs-lookup"><span data-stu-id="37a85-127">Sends the same message *n* times.</span></span> <span data-ttu-id="37a85-128">Los caracteres de contenedor se aplicarán a cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="37a85-128">The wrapper characters will be applied to each message.</span></span>|  
|<span data-ttu-id="37a85-129">**/ TWOWAY**</span><span class="sxs-lookup"><span data-stu-id="37a85-129">**/TWOWAY**</span></span>|<span data-ttu-id="37a85-130">El remitente va a esperar una respuesta desde el receptor.</span><span class="sxs-lookup"><span data-stu-id="37a85-130">The sender will wait for a response from the receiver.</span></span> <span data-ttu-id="37a85-131">SB y EB deben especificarse.</span><span class="sxs-lookup"><span data-stu-id="37a85-131">SB and EB need to be specified.</span></span> <span data-ttu-id="37a85-132">CR es opcional.</span><span class="sxs-lookup"><span data-stu-id="37a85-132">CR is optional.</span></span> <span data-ttu-id="37a85-133">En el modo de archivo, la respuesta se almacena en el archivo. RESPUESTA.</span><span class="sxs-lookup"><span data-stu-id="37a85-133">In File mode, the response is stored in the file FILE.RESPONSE.</span></span>|  
|<span data-ttu-id="37a85-134">**/ SB**</span><span class="sxs-lookup"><span data-stu-id="37a85-134">**/SB**</span></span>|<span data-ttu-id="37a85-135">Establece el valor ASCII del Byte de delimitador de bloque de inicio.</span><span class="sxs-lookup"><span data-stu-id="37a85-135">Sets the ASCII value of the Start Block Delimiter Byte.</span></span> <span data-ttu-id="37a85-136">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="37a85-136">The default is none.</span></span>|  
|<span data-ttu-id="37a85-137">**/EB**</span><span class="sxs-lookup"><span data-stu-id="37a85-137">**/EB**</span></span>|<span data-ttu-id="37a85-138">Establece el valor ASCII del Byte de delimitador de bloque final.</span><span class="sxs-lookup"><span data-stu-id="37a85-138">Sets the ASCII value of the End Block Delimiter Byte.</span></span> <span data-ttu-id="37a85-139">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="37a85-139">The default is none.</span></span>|  
|<span data-ttu-id="37a85-140">**/CR**</span><span class="sxs-lookup"><span data-stu-id="37a85-140">**/CR**</span></span>|<span data-ttu-id="37a85-141">Establece el valor ASCII del carro devolver delimitador Byte.</span><span class="sxs-lookup"><span data-stu-id="37a85-141">Sets the ASCII value of the Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="37a85-142">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="37a85-142">The default is none.</span></span>|  
  
## <a name="examples-of-tool-use"></a><span data-ttu-id="37a85-143">Ejemplos de uso de herramienta</span><span class="sxs-lookup"><span data-stu-id="37a85-143">Examples of Tool Use</span></span>  
 <span data-ttu-id="37a85-144">Los ejemplos siguientes muestran cómo puede utilizar la herramienta MllpSend.</span><span class="sxs-lookup"><span data-stu-id="37a85-144">The following examples demonstrate how you can use the MllpSend tool.</span></span>  
  
 <span data-ttu-id="37a85-145">**Ejemplo 1.**</span><span class="sxs-lookup"><span data-stu-id="37a85-145">**Example 1.**</span></span> <span data-ttu-id="37a85-146">Puede utilizar el siguiente comando para enviar un mensaje a un adaptador unidireccional escuchando en el puerto 13000 servidor "myserver".</span><span class="sxs-lookup"><span data-stu-id="37a85-146">You can use the following command to send a message to a one-way adapter listening on port 13000 on server "myserver".</span></span> <span data-ttu-id="37a85-147">Los valores ASCII de los caracteres de contenedor son SB 11, EB 28 y CR 13.</span><span class="sxs-lookup"><span data-stu-id="37a85-147">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 <span data-ttu-id="37a85-148">**Ejemplo 2.**</span><span class="sxs-lookup"><span data-stu-id="37a85-148">**Example 2.**</span></span> <span data-ttu-id="37a85-149">Puede utilizar el siguiente comando para enviar un mensaje de 100 veces a un adaptador bidireccional escuchando en el puerto 11000 servidor "localhost".</span><span class="sxs-lookup"><span data-stu-id="37a85-149">You can use the following command to send a message 100 times to a two-way adapter listening on port 11000 on server "localhost".</span></span> <span data-ttu-id="37a85-150">Los valores ASCII de los caracteres de contenedor son SB 11, EB 28 y CR 13.</span><span class="sxs-lookup"><span data-stu-id="37a85-150">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a><span data-ttu-id="37a85-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="37a85-151">See Also</span></span>  
 [<span data-ttu-id="37a85-152">Utilidades</span><span class="sxs-lookup"><span data-stu-id="37a85-152">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)