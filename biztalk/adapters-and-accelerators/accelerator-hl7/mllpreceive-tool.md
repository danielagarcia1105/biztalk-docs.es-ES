---
title: Herramienta de MllpReceive | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e990c49a221653289619a33c30100accc3c68d6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961514"
---
# <a name="mllpreceive-tool"></a><span data-ttu-id="b1e89-102">Herramienta MllpReceive</span><span class="sxs-lookup"><span data-stu-id="b1e89-102">MllpReceive Tool</span></span>
<span data-ttu-id="b1e89-103">Puede utilizar la herramienta MllpReceive para recibir datos de un puerto de envío MLLP.</span><span class="sxs-lookup"><span data-stu-id="b1e89-103">You can use the MllpReceive tool to receive data from an MLLP send port.</span></span>  
  
 <span data-ttu-id="b1e89-104">Instalar esta herramienta a través de la [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] procedimiento de instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="b1e89-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="b1e89-105">Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b1e89-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="b1e89-106">En la pantalla instalación personalizada, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="b1e89-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="b1e89-107">Para obtener más información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span><span class="sxs-lookup"><span data-stu-id="b1e89-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="b1e89-108">El programa de instalación de BTAHL7 instala esta herramienta en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7\SDK\MLLP utilidades.</span><span class="sxs-lookup"><span data-stu-id="b1e89-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="b1e89-109">Use esta herramienta en el [-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), el [Tutorial Interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), el [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)y el [mensaje enriquecimiento Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b1e89-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="b1e89-110">Si ha instalado [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a través de la instalación predeterminada y no se ha instalado la herramienta MLLPTest (incluidos MllpReceive y MllpSend), no podrá probar los resultados del tutoriales.</span><span class="sxs-lookup"><span data-stu-id="b1e89-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLPTest tool (including MllpReceive and MllpSend), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="b1e89-111">Uso de la herramienta</span><span class="sxs-lookup"><span data-stu-id="b1e89-111">Tool Usage</span></span>  
 <span data-ttu-id="b1e89-112">A continuación muestra la sintaxis usada para invocar esta herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b1e89-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="b1e89-113">En la tabla siguiente describe cada parte de la sintaxis que se utiliza la herramienta MllpReceive.</span><span class="sxs-lookup"><span data-stu-id="b1e89-113">The following table describes each part of the syntax the MllpReceive tool uses.</span></span>  
  
|<span data-ttu-id="b1e89-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1e89-114">Syntax</span></span>|<span data-ttu-id="b1e89-115">Significado</span><span class="sxs-lookup"><span data-stu-id="b1e89-115">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="b1e89-116">/?</span><span class="sxs-lookup"><span data-stu-id="b1e89-116">/?</span></span>|<span data-ttu-id="b1e89-117">Muestra esta Ayuda.</span><span class="sxs-lookup"><span data-stu-id="b1e89-117">Displays this help.</span></span>|  
|<span data-ttu-id="b1e89-118">/I \<IP\></span><span class="sxs-lookup"><span data-stu-id="b1e89-118">/I \<IP\></span></span>|<span data-ttu-id="b1e89-119">Indica la dirección para escuchar.</span><span class="sxs-lookup"><span data-stu-id="b1e89-119">Denotes the address to listen to.</span></span> <span data-ttu-id="b1e89-120">El valor predeterminado es direcciones IP disponible.</span><span class="sxs-lookup"><span data-stu-id="b1e89-120">The default is all available IPs.</span></span>|  
|<span data-ttu-id="b1e89-121">/P \<PUERTO\></span><span class="sxs-lookup"><span data-stu-id="b1e89-121">/P \<PORT\></span></span>|<span data-ttu-id="b1e89-122">Indica el número de puerto para escuchar.</span><span class="sxs-lookup"><span data-stu-id="b1e89-122">Denotes the port number to listen to.</span></span> <span data-ttu-id="b1e89-123">El valor predeterminado es 12000.</span><span class="sxs-lookup"><span data-stu-id="b1e89-123">The default value is 12000.</span></span>|  
|<span data-ttu-id="b1e89-124">/D \<DIRECTORY\></span><span class="sxs-lookup"><span data-stu-id="b1e89-124">/D \<DIRECTORY\></span></span>|<span data-ttu-id="b1e89-125">Almacena recibidos todos los mensajes en el directorio \<DIRECTORY\>.</span><span class="sxs-lookup"><span data-stu-id="b1e89-125">Stores all received message(s) in the directory in \<DIRECTORY\>.</span></span> <span data-ttu-id="b1e89-126">Si no se especifica \<directorio\>, el directorio predeterminado es % TEMP %.</span><span class="sxs-lookup"><span data-stu-id="b1e89-126">If you do not specify \<DIRECTORY\>, the default directory is %TEMP%.</span></span>|  
|<span data-ttu-id="b1e89-127">/ DIVISIÓN</span><span class="sxs-lookup"><span data-stu-id="b1e89-127">/SPLIT</span></span>|<span data-ttu-id="b1e89-128">Divide los datos recibidos en mensajes independientes en función de los delimitadores.</span><span class="sxs-lookup"><span data-stu-id="b1e89-128">Splits the received data into separate messages based on the delimiters.</span></span> <span data-ttu-id="b1e89-129">Se requiere SB y EB.</span><span class="sxs-lookup"><span data-stu-id="b1e89-129">SB and EB are required.</span></span> <span data-ttu-id="b1e89-130">CR es opcional.</span><span class="sxs-lookup"><span data-stu-id="b1e89-130">CR is optional.</span></span>|  
|<span data-ttu-id="b1e89-131">/ STATICACK</span><span class="sxs-lookup"><span data-stu-id="b1e89-131">/STATICACK</span></span>|<span data-ttu-id="b1e89-132">La confirmación estática que se devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="b1e89-132">The static acknowledgment returned to the sender.</span></span> <span data-ttu-id="b1e89-133">Aplicará el modo de división.</span><span class="sxs-lookup"><span data-stu-id="b1e89-133">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="b1e89-134">/ HL7ACK</span><span class="sxs-lookup"><span data-stu-id="b1e89-134">/HL7ACK</span></span>|<span data-ttu-id="b1e89-135">La confirmación de HL7 devuelve al remitente.</span><span class="sxs-lookup"><span data-stu-id="b1e89-135">The HL7 acknowledgment returned to the sender.</span></span> <span data-ttu-id="b1e89-136">Nombre de archivo indica el nombre del archivo que contiene la confirmación HL7.</span><span class="sxs-lookup"><span data-stu-id="b1e89-136">FILENAME denotes the name of the file containing the HL7 ACK.</span></span> <span data-ttu-id="b1e89-137">Aplicará el modo de división.</span><span class="sxs-lookup"><span data-stu-id="b1e89-137">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="b1e89-138">/ SB</span><span class="sxs-lookup"><span data-stu-id="b1e89-138">/SB</span></span>|<span data-ttu-id="b1e89-139">Establece el valor ASCII de bytes de delimitador de bloque de inicio.</span><span class="sxs-lookup"><span data-stu-id="b1e89-139">Sets the ASCII value of Start Block Delimiter Byte.</span></span> <span data-ttu-id="b1e89-140">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="b1e89-140">The default is none.</span></span>|  
|<span data-ttu-id="b1e89-141">/EB</span><span class="sxs-lookup"><span data-stu-id="b1e89-141">/EB</span></span>|<span data-ttu-id="b1e89-142">Establece el valor ASCII de bytes de delimitador de bloque final.</span><span class="sxs-lookup"><span data-stu-id="b1e89-142">Sets the ASCII value of End Block Delimiter Byte.</span></span> <span data-ttu-id="b1e89-143">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="b1e89-143">The default is none.</span></span>|  
|<span data-ttu-id="b1e89-144">/CR</span><span class="sxs-lookup"><span data-stu-id="b1e89-144">/CR</span></span>|<span data-ttu-id="b1e89-145">Establece el valor ASCII de bytes de transporte devolver delimitador.</span><span class="sxs-lookup"><span data-stu-id="b1e89-145">Sets the ASCII value of Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="b1e89-146">El valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="b1e89-146">The default is none.</span></span>|  
  
## <a name="example-of-tool-use"></a><span data-ttu-id="b1e89-147">Ejemplo de uso de herramienta</span><span class="sxs-lookup"><span data-stu-id="b1e89-147">Example of Tool Use</span></span>  
 <span data-ttu-id="b1e89-148">Puede usar el siguiente comando para escuchar al puerto 10000 en localhost y guardar mensajes para separar archivos en C:\TEMP:</span><span class="sxs-lookup"><span data-stu-id="b1e89-148">You can use the following command to listen to port 10000 on localhost, and save messages to separate files on C:\TEMP:</span></span>  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1e89-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1e89-149">See Also</span></span>  
 [<span data-ttu-id="b1e89-150">Utilidades</span><span class="sxs-lookup"><span data-stu-id="b1e89-150">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)