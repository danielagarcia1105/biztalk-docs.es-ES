---
title: ¿Qué es el adaptador de FileAct? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6fe9b28e4ea2b5eee087b61866827a766c3e3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971493"
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="dfec5-103">¿Qué es el adaptador de FileAct?</span><span class="sxs-lookup"><span data-stu-id="dfec5-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="dfec5-104">El adaptador de FileAct para SWIFTNet proporciona conectividad entre BizTalk Server y la sociedad de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo Secure IP red (SIPN) para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="dfec5-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="dfec5-105">La SIPN transfiere archivos y mensajes a través de una red privada segura que se conecta a las instituciones financieras, infraestructuras de la industria financiera y clientes.</span><span class="sxs-lookup"><span data-stu-id="dfec5-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="dfec5-106">El adaptador de FileAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).</span><span class="sxs-lookup"><span data-stu-id="dfec5-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="dfec5-107">El adaptador de FileAct proporciona un mecanismo para SWIFT participantes de forma segura y confiable intercambiar archivos y la información relativa a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="dfec5-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="dfec5-108">Admite la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="dfec5-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="dfec5-109">Enviar archivos a un usuario de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="dfec5-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="dfec5-110">Recuperación de archivos de un usuario de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="dfec5-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="dfec5-111">Para confirmar la recepción de archivo por un receptor de notificación de entrega</span><span class="sxs-lookup"><span data-stu-id="dfec5-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="dfec5-112">Anulación de transferencias en curso</span><span class="sxs-lookup"><span data-stu-id="dfec5-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="dfec5-113">Supervisión de estado de transferencia de los archivos</span><span class="sxs-lookup"><span data-stu-id="dfec5-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="dfec5-114">Transferencias de archivos simultáneas</span><span class="sxs-lookup"><span data-stu-id="dfec5-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="dfec5-115">Garantía de integridad y autenticidad de los datos</span><span class="sxs-lookup"><span data-stu-id="dfec5-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="dfec5-116">Confidencialidad de los archivos de datos en tránsito</span><span class="sxs-lookup"><span data-stu-id="dfec5-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="dfec5-117">Sin repudio de transferencias de archivos</span><span class="sxs-lookup"><span data-stu-id="dfec5-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="dfec5-118">Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="dfec5-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="dfec5-119">El servicio de FileAct</span><span class="sxs-lookup"><span data-stu-id="dfec5-119">The FileAct Service</span></span>  
 <span data-ttu-id="dfec5-120">El adaptador de FileAct para SWIFTNet proporciona a transferencia segura y confiable de archivos, como lotes de mensajes estructurados de financieros o informes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="dfec5-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="dfec5-121">Las aplicaciones típicas incluyen transferencias repetitivos como pensiones o los pagos del salario, información de valor añadido de títulos y elaboración de informes y las disposiciones legales.</span><span class="sxs-lookup"><span data-stu-id="dfec5-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="dfec5-122">SWIFTNet FileAct ofrece una variedad de modos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="dfec5-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
- <span data-ttu-id="dfec5-123">**Transferencia de archivos de Store y reenvío.**</span><span class="sxs-lookup"><span data-stu-id="dfec5-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="dfec5-124">Capacidad de almacenamiento y reenvío de SWIFTNet FileAct elimina la incertidumbre y los inconvenientes de tener que preocuparse de si son o no los corresponsales en línea en el momento de que transmitir el archivo.</span><span class="sxs-lookup"><span data-stu-id="dfec5-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="dfec5-125">El archivo se entregará tan pronto como el destinatario está listo para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="dfec5-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="dfec5-126">Como resultado, proporciona una forma ideal de enviar archivos a un gran número de corresponsales, algunos de los cuales pueden estar en distintas zonas horarias.</span><span class="sxs-lookup"><span data-stu-id="dfec5-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
- <span data-ttu-id="dfec5-127">**Transferencia de archivos en tiempo real.**</span><span class="sxs-lookup"><span data-stu-id="dfec5-127">**Real-time file transfer.**</span></span> <span data-ttu-id="dfec5-128">Mensajería en tiempo real, ofrece una alternativa de menor costo para almacenar y reenviar para los archivos que están destinados a corresponsales que están en línea en el momento de la transmisión.</span><span class="sxs-lookup"><span data-stu-id="dfec5-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="dfec5-129">Como resultado es ideal para enviar archivos a unos corresponsales grandes o infraestructuras de mercado.</span><span class="sxs-lookup"><span data-stu-id="dfec5-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
- <span data-ttu-id="dfec5-130">**Recuperación de archivos en tiempo real.**</span><span class="sxs-lookup"><span data-stu-id="dfec5-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="dfec5-131">Se trata de un servicio interactivo que se utiliza normalmente para recuperar archivos en el contexto de los sistemas basados en la estación de trabajo y a menudo junto con SWIFTNet Examinar.</span><span class="sxs-lookup"><span data-stu-id="dfec5-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="dfec5-132">Admitimos este modo.</span><span class="sxs-lookup"><span data-stu-id="dfec5-132">We will support this mode.</span></span>  
  
  <span data-ttu-id="dfec5-133">Las características opcionales de SWIFTNet FileAct (dentro de un archivo por archivo) se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dfec5-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
- <span data-ttu-id="dfec5-134">**Prioridad del mensaje.**</span><span class="sxs-lookup"><span data-stu-id="dfec5-134">**Message priority.**</span></span> <span data-ttu-id="dfec5-135">Las transferencias de archivos pueden marcarse como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus corresponsales.</span><span class="sxs-lookup"><span data-stu-id="dfec5-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
- <span data-ttu-id="dfec5-136">**Notificación de entrega (modos en tiempo real y de almacenamiento y reenvío).**</span><span class="sxs-lookup"><span data-stu-id="dfec5-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="dfec5-137">Proporciona la confirmación de que el destinatario recibe el archivo.</span><span class="sxs-lookup"><span data-stu-id="dfec5-137">Provides confirmation that your correspondent received your file.</span></span>  
  
- <span data-ttu-id="dfec5-138">**Sin repudio de recepción y de emisión.**</span><span class="sxs-lookup"><span data-stu-id="dfec5-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="dfec5-139">En el caso de conflicto, permite SWIFT confirmar que la transferencia de archivos tuvo lugar como reclamado.</span><span class="sxs-lookup"><span data-stu-id="dfec5-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
  <span data-ttu-id="dfec5-140">Las características de SWIFTNet FileAct estándares incluyen seguridad SWIFTNet PKI<strong>.</strong></span><span class="sxs-lookup"><span data-stu-id="dfec5-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security<strong>.</strong></span></span> <span data-ttu-id="dfec5-141">SWIFTNet FileAct está protegida con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dfec5-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
  <span data-ttu-id="dfec5-142">Todos los mensajes y los archivos que se intercambian en SWIFTNet someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="dfec5-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="dfec5-143">Estas comprobaciones se realizan mediante la aplicación de puerta de enlace SWIFTAlliance (SAG).</span><span class="sxs-lookup"><span data-stu-id="dfec5-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfec5-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfec5-144">See Also</span></span>  
 <span data-ttu-id="dfec5-145">[Introducción a la FileAct e interactuar de adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="dfec5-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="dfec5-146">[¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="dfec5-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="dfec5-147">¿Qué es el adaptador de InterAct?</span><span class="sxs-lookup"><span data-stu-id="dfec5-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)