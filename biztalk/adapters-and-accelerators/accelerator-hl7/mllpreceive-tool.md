---
title: Herramienta de MllpReceive | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c23aac352b47a328cfc8f412bb3beca50a61e1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mllpreceive-tool"></a><span data-ttu-id="0d613-102">Herramienta MllpReceive</span><span class="sxs-lookup"><span data-stu-id="0d613-102">MllpReceive Tool</span></span>
<span data-ttu-id="0d613-103">Puede utilizar la herramienta MllpReceive para recibir datos de un puerto de envío MLLP.</span><span class="sxs-lookup"><span data-stu-id="0d613-103">You can use the MllpReceive tool to receive data from an MLLP send port.</span></span>  
  
 <span data-ttu-id="0d613-104">Instalar esta herramienta a través de la [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] procedimiento de instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="0d613-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="0d613-105">Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial.</span><span class="sxs-lookup"><span data-stu-id="0d613-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="0d613-106">En la pantalla instalación personalizada, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="0d613-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="0d613-107">Para obtener más información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span><span class="sxs-lookup"><span data-stu-id="0d613-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="0d613-108">El programa de instalación de BTAHL7 instala esta herramienta en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for HL7\SDK\MLLP utilidades.</span><span class="sxs-lookup"><span data-stu-id="0d613-108">BTAHL7 setup installs this tool in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="0d613-109">Use esta herramienta en el [-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), el [Tutorial Interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), el [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)y el [mensaje enriquecimiento Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="0d613-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="0d613-110">Si ha instalado [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a través de la instalación predeterminada y no se ha instalado la herramienta MLLPTest (incluidos MllpReceive y MllpSend), no podrá probar los resultados del tutoriales.</span><span class="sxs-lookup"><span data-stu-id="0d613-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLPTest tool (including MllpReceive and MllpSend), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="0d613-111">Uso de la herramienta</span><span class="sxs-lookup"><span data-stu-id="0d613-111">Tool Usage</span></span>  
 <span data-ttu-id="0d613-112">A continuación muestra la sintaxis usada para invocar esta herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="0d613-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="0d613-113">En la tabla siguiente describe cada parte de la sintaxis que se utiliza la herramienta MllpReceive.</span><span class="sxs-lookup"><span data-stu-id="0d613-113">The following table describes each part of the syntax the MllpReceive tool uses.</span></span>  
  
|<span data-ttu-id="0d613-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d613-114">Syntax</span></span>|<span data-ttu-id="0d613-115">Significado</span><span class="sxs-lookup"><span data-stu-id="0d613-115">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="0d613-116">/?</span><span class="sxs-lookup"><span data-stu-id="0d613-116">/?</span></span>|<span data-ttu-id="0d613-117">Muestra esta Ayuda.</span><span class="sxs-lookup"><span data-stu-id="0d613-117">Displays this help.</span></span>|  
|<span data-ttu-id="0d613-118">/I \<IP ></span><span class="sxs-lookup"><span data-stu-id="0d613-118">/I \<IP></span></span>|<span data-ttu-id="0d613-119">Indica la dirección para escuchar.</span><span class="sxs-lookup"><span data-stu-id="0d613-119">Denotes the address to listen to.</span></span> <span data-ttu-id="0d613-120">El valor predeterminado es direcciones IP disponible.</span><span class="sxs-lookup"><span data-stu-id="0d613-120">The default is all available IPs.</span></span>|  
|<span data-ttu-id="0d613-121">/P \<PUERTO ></span><span class="sxs-lookup"><span data-stu-id="0d613-121">/P \<PORT></span></span>|<span data-ttu-id="0d613-122">Indica el número de puerto para escuchar.</span><span class="sxs-lookup"><span data-stu-id="0d613-122">Denotes the port number to listen to.</span></span> <span data-ttu-id="0d613-123">El valor predeterminado es 12000.</span><span class="sxs-lookup"><span data-stu-id="0d613-123">The default value is 12000.</span></span>|  
|<span data-ttu-id="0d613-124">/D \<DIRECTORIO ></span><span class="sxs-lookup"><span data-stu-id="0d613-124">/D \<DIRECTORY></span></span>|<span data-ttu-id="0d613-125">Almacena recibidos todos los mensajes en el directorio \<directorio >.</span><span class="sxs-lookup"><span data-stu-id="0d613-125">Stores all received message(s) in the directory in \<DIRECTORY>.</span></span> <span data-ttu-id="0d613-126">Si no se especifica \<DIRECTORY >, el directorio predeterminado es % TEMP %.</span><span class="sxs-lookup"><span data-stu-id="0d613-126">If you do not specify \<DIRECTORY>, the default directory is %TEMP%.</span></span>|  
|<span data-ttu-id="0d613-127">/ DIVISIÓN</span><span class="sxs-lookup"><span data-stu-id="0d613-127">/SPLIT</span></span>|<span data-ttu-id="0d613-128">Divide los datos recibidos en mensajes independientes en función de los delimitadores.</span><span class="sxs-lookup"><span data-stu-id="0d613-128">Splits the received data into separate messages based on the delimiters.</span></span> <span data-ttu-id="0d613-129">Se requiere SB y EB.</span><span class="sxs-lookup"><span data-stu-id="0d613-129">SB and EB are required.</span></span> <span data-ttu-id="0d613-130">CR es opcional.</span><span class="sxs-lookup"><span data-stu-id="0d613-130">CR is optional.</span></span>|  
|<span data-ttu-id="0d613-131">/ STATICACK</span><span class="sxs-lookup"><span data-stu-id="0d613-131">/STATICACK</span></span>|<span data-ttu-id="0d613-132">La confirmación estática que se devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="0d613-132">The static acknowledgment returned to the sender.</span></span> <span data-ttu-id="0d613-133">Aplicará el modo de división.</span><span class="sxs-lookup"><span data-stu-id="0d613-133">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="0d613-134">/ HL7ACK</span><span class="sxs-lookup"><span data-stu-id="0d613-134">/HL7ACK</span></span>|<span data-ttu-id="0d613-135">La confirmación de HL7 devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="0d613-135">The HL7 acknowledgment returned to the sender.</span></span> <span data-ttu-id="0d613-136">Nombre de archivo indica el nombre del archivo que contiene la confirmación HL7.</span><span class="sxs-lookup"><span data-stu-id="0d613-136">FILENAME denotes the name of the file containing the HL7 ACK.</span></span> <span data-ttu-id="0d613-137">Aplicará el modo de división.</span><span class="sxs-lookup"><span data-stu-id="0d613-137">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="0d613-138">/ SB</span><span class="sxs-lookup"><span data-stu-id="0d613-138">/SB</span></span>|<span data-ttu-id="0d613-139">Establece el valor ASCII de bytes de delimitador de bloque de inicio.</span><span class="sxs-lookup"><span data-stu-id="0d613-139">Sets the ASCII value of Start Block Delimiter Byte.</span></span> <span data-ttu-id="0d613-140">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="0d613-140">The default is none.</span></span>|  
|<span data-ttu-id="0d613-141">/EB</span><span class="sxs-lookup"><span data-stu-id="0d613-141">/EB</span></span>|<span data-ttu-id="0d613-142">Establece el valor ASCII de bytes de delimitador de bloque final.</span><span class="sxs-lookup"><span data-stu-id="0d613-142">Sets the ASCII value of End Block Delimiter Byte.</span></span> <span data-ttu-id="0d613-143">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="0d613-143">The default is none.</span></span>|  
|<span data-ttu-id="0d613-144">/CR</span><span class="sxs-lookup"><span data-stu-id="0d613-144">/CR</span></span>|<span data-ttu-id="0d613-145">Establece el valor ASCII de bytes de transporte devolver delimitador.</span><span class="sxs-lookup"><span data-stu-id="0d613-145">Sets the ASCII value of Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="0d613-146">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="0d613-146">The default is none.</span></span>|  
  
## <a name="example-of-tool-use"></a><span data-ttu-id="0d613-147">Ejemplo de uso de herramienta</span><span class="sxs-lookup"><span data-stu-id="0d613-147">Example of Tool Use</span></span>  
 <span data-ttu-id="0d613-148">Puede usar el siguiente comando para escuchar al puerto 10000 en localhost y guardar mensajes para separar archivos en C:\TEMP:</span><span class="sxs-lookup"><span data-stu-id="0d613-148">You can use the following command to listen to port 10000 on localhost, and save messages to separate files on C:\TEMP:</span></span>  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d613-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d613-149">See Also</span></span>  
 [<span data-ttu-id="0d613-150">Utilidades</span><span class="sxs-lookup"><span data-stu-id="0d613-150">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)