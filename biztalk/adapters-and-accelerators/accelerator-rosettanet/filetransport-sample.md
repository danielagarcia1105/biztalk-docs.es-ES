---
title: Ejemplo de FileTransport | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a4be76ba244418612fe9c4a4996569b3c40b506
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007005"
---
# <a name="filetransport-sample"></a><span data-ttu-id="77919-102">Ejemplo de FileTransport</span><span class="sxs-lookup"><span data-stu-id="77919-102">FileTransport Sample</span></span>
<span data-ttu-id="77919-103">El ejemplo de FileTransport muestra cómo configurar Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para usar puertos de archivo, en lugar de puertos SQL.</span><span class="sxs-lookup"><span data-stu-id="77919-103">The FileTransport sample demonstrates how to configure Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to use File ports, instead of SQL ports.</span></span> <span data-ttu-id="77919-104">El ejemplo de FileTransport usa el protocolo de transferencia de archivos (FTP) para enviar y recibir mensajes, en lugar de HTTP.</span><span class="sxs-lookup"><span data-stu-id="77919-104">The FileTransport sample uses File Transport Protocol (FTP) to send and receive messages, instead of HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77919-105">Este documento se da por supuesto que está instalando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] prueba o demostración solamente para fines internos.</span><span class="sxs-lookup"><span data-stu-id="77919-105">This document assumes that you are installing [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] for internal testing or demonstration purposes only.</span></span> <span data-ttu-id="77919-106">No recomiendan cualquier cuenta de seguridad mínima o configurar.</span><span class="sxs-lookup"><span data-stu-id="77919-106">It does not prescribe any minimum-security account or set up.</span></span> <span data-ttu-id="77919-107">Debe usar una cuenta que tenga permisos administrativos locales a lo largo de los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="77919-107">You must use an account that has local administrative permissions throughout the procedures in this topic.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="77919-108">En este ejemplo no es compatible con los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="77919-108">This sample does not support message attachments.</span></span>  
  
## <a name="filetransport-binding-files"></a><span data-ttu-id="77919-109">Archivos de enlace de FileTransport</span><span class="sxs-lookup"><span data-stu-id="77919-109">FileTransport Binding Files</span></span>  
 <span data-ttu-id="77919-110">El ejemplo de FileTransport incluye dos archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="77919-110">The FileTransport sample includes two binding files.</span></span> <span data-ttu-id="77919-111">Puede usar cada uno de estos archivos de enlace para configurar los puertos de archivo para su uso con una orquestación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="77919-111">You can use each of these binding files to set up File ports for use with a BTARN orchestration.</span></span> <span data-ttu-id="77919-112">Estos archivos de enlace se encuentran en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet \SDK\FileTransport.</span><span class="sxs-lookup"><span data-stu-id="77919-112">These binding files are located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\FileTransport.</span></span> <span data-ttu-id="77919-113">Abra cada archivo de enlace en un editor como el Bloc de notas para ver la configuración de la orquestación, puerto de envío, puerto de recepción y ubicación de recepción, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="77919-113">Open each binding file in an editor like Notepad to see the settings for the orchestration, send port, receive port, and receive location, as listed below.</span></span>  
  
- <span data-ttu-id="77919-114">PrivateInitiatorusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="77919-114">PrivateInitiatorusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="77919-115">Orquestación: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span><span class="sxs-lookup"><span data-stu-id="77919-115">Orchestration: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span></span>  
  
  -   <span data-ttu-id="77919-116">Puerto de envío: PrivateInitiator_To_File</span><span class="sxs-lookup"><span data-stu-id="77919-116">Send port: PrivateInitiator_To_File</span></span>  
  
  -   <span data-ttu-id="77919-117">Puerto de recepción: File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="77919-117">Receive port: File_To_PrivateInitiator</span></span>  
  
  -   <span data-ttu-id="77919-118">Ubicación de recepción: File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="77919-118">Receive location: File_To_PrivateInitiator</span></span>  
  
- <span data-ttu-id="77919-119">PrivateResponderusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="77919-119">PrivateResponderusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="77919-120">Orquestación: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span><span class="sxs-lookup"><span data-stu-id="77919-120">Orchestration: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span></span>  
  
  -   <span data-ttu-id="77919-121">Puerto de envío: PrivateResponder_To_File</span><span class="sxs-lookup"><span data-stu-id="77919-121">Send port: PrivateResponder_To_File</span></span>  
  
  -   <span data-ttu-id="77919-122">Puerto de recepción: File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="77919-122">Receive port: File_To_PrivateResponder</span></span>  
  
  -   <span data-ttu-id="77919-123">Ubicación de recepción: File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="77919-123">Receive location: File_To_PrivateResponder</span></span>  
  
  <span data-ttu-id="77919-124">El siguiente procedimiento describe cómo importar los enlaces desde los archivos de enlace con el comando BTSTask.</span><span class="sxs-lookup"><span data-stu-id="77919-124">The following procedure describes how to import the bindings from the binding files using the BTSTask command.</span></span> <span data-ttu-id="77919-125">Para obtener más información, vea el tema "Comando ImportBindings" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77919-125">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="77919-126">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="77919-126">Procedure</span></span>  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a><span data-ttu-id="77919-127">Para configurar BTARN mediante el uso de carpetas de entrega de archivos</span><span class="sxs-lookup"><span data-stu-id="77919-127">To set up BTARN by using file drop folders</span></span>  
  
1.  <span data-ttu-id="77919-128">Abra el Explorador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="77919-128">Open BizTalk Explorer.</span></span>  
  
2.  <span data-ttu-id="77919-129">Detenga los dos puertos de envío SQL LOB, PrivateInitiator_To_LOB y PrivateResponder_To_LOB.</span><span class="sxs-lookup"><span data-stu-id="77919-129">Stop the two LOB SQL send ports, PrivateInitiator_To_LOB and PrivateResponder_To_LOB.</span></span>  
  
3.  <span data-ttu-id="77919-130">Deshabilite los dos Lob SQL Receive puertos, LOB_To_PrivateInitiator y LOB_To_PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="77919-130">Disable the two Lob SQL Receive ports, LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
4.  <span data-ttu-id="77919-131">Dar de baja Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.</span><span class="sxs-lookup"><span data-stu-id="77919-131">Unenlist Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.</span></span>  
  
5.  <span data-ttu-id="77919-132">Dar de baja Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.</span><span class="sxs-lookup"><span data-stu-id="77919-132">Unenlist Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.</span></span>  
  
6.  <span data-ttu-id="77919-133">Cree una carpeta \FileDrops en la carpeta BTARN de C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet y, a continuación, cree la siguiente estructura de carpetas bajo \FileDrops:</span><span class="sxs-lookup"><span data-stu-id="77919-133">Create a \FileDrops folder under the BTARN folder of C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet , and then create the following folder structure under \FileDrops:</span></span>  
  
    -   <span data-ttu-id="77919-134">\PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="77919-134">\PrivateInitiator</span></span>  
  
         <span data-ttu-id="77919-135">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="77919-135">\FromLOB</span></span>  
  
         <span data-ttu-id="77919-136">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="77919-136">\ToLOB</span></span>  
  
    -   <span data-ttu-id="77919-137">\PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="77919-137">\PrivateResponder</span></span>  
  
         <span data-ttu-id="77919-138">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="77919-138">\FromLOB</span></span>  
  
         <span data-ttu-id="77919-139">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="77919-139">\ToLOB</span></span>  
  
7.  <span data-ttu-id="77919-140">Ejecute el comando siguiente (suponiendo que BTARN está instalado en la unidad C:):</span><span class="sxs-lookup"><span data-stu-id="77919-140">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  <span data-ttu-id="77919-141">Ejecute el comando siguiente (suponiendo que BTARN está instalado en la unidad C:):</span><span class="sxs-lookup"><span data-stu-id="77919-141">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. <span data-ttu-id="77919-142">Iniciar los puertos de envío: PrivateInitiator_To_File y PrivateResponder_To_File.</span><span class="sxs-lookup"><span data-stu-id="77919-142">Start the send ports: PrivateInitiator_To_File and PrivateResponder_To_File.</span></span>  
  
10. <span data-ttu-id="77919-143">Habilite los puertos de recepción: LOB_To_PrivateInitiator y LOB_To_PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="77919-143">Enable the receive ports: LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77919-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="77919-144">See Also</span></span>  
 [<span data-ttu-id="77919-145">Ejemplos de mensajería</span><span class="sxs-lookup"><span data-stu-id="77919-145">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)