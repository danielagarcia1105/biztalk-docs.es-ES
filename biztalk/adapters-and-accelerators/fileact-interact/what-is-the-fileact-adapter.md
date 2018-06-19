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
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225324"
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="ded82-103">¿Qué es el adaptador de FileAct?</span><span class="sxs-lookup"><span data-stu-id="ded82-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="ded82-104">El adaptador de FileAct para SWIFTNet proporciona conectividad entre BizTalk Server y la sociedad para red de IP de seguros de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo (SIPN) para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="ded82-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="ded82-105">La SIPN transfiere archivos y mensajes a través de una red privada segura que conecta las instituciones financieras, infraestructuras de sector financiero y los clientes.</span><span class="sxs-lookup"><span data-stu-id="ded82-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="ded82-106">El adaptador de FileAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).</span><span class="sxs-lookup"><span data-stu-id="ded82-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="ded82-107">El adaptador de FileAct proporciona un mecanismo para SWIFT a participantes de forma segura y confiable intercambiar archivos y la información relativa a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="ded82-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="ded82-108">Admite la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="ded82-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="ded82-109">Enviar archivos a un usuario SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="ded82-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="ded82-110">Recuperar archivos de un usuario SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="ded82-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="ded82-111">Para confirmar la recepción de archivo por un destinatario de notificación de entrega</span><span class="sxs-lookup"><span data-stu-id="ded82-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="ded82-112">Anulación de las transferencias en curso</span><span class="sxs-lookup"><span data-stu-id="ded82-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="ded82-113">Supervisión de estado de transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="ded82-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="ded82-114">Transferencias de archivos simultáneas</span><span class="sxs-lookup"><span data-stu-id="ded82-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="ded82-115">Garantía de autenticidad de los datos y de integridad</span><span class="sxs-lookup"><span data-stu-id="ded82-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="ded82-116">Confidencialidad de los datos de archivo en tránsito</span><span class="sxs-lookup"><span data-stu-id="ded82-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="ded82-117">Sin rechazo de las transferencias de archivos</span><span class="sxs-lookup"><span data-stu-id="ded82-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="ded82-118">Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="ded82-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="ded82-119">El servicio de FileAct</span><span class="sxs-lookup"><span data-stu-id="ded82-119">The FileAct Service</span></span>  
 <span data-ttu-id="ded82-120">El adaptador de FileAct para SWIFTNet proporciona a una transferencia segura y confiable de archivos, como lotes de mensajes estructurados de financieros o informes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="ded82-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="ded82-121">Las aplicaciones típicas incluyen las transferencias de crédito repetitivos como pensión o pagos de salario, información de valor añadido de títulos y elaboración de informes y legales.</span><span class="sxs-lookup"><span data-stu-id="ded82-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="ded82-122">SWIFTNet FileAct ofrece una variedad de modos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="ded82-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
-   <span data-ttu-id="ded82-123">**Transferencia de archivos de almacenamiento y reenvío.**</span><span class="sxs-lookup"><span data-stu-id="ded82-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="ded82-124">Capacidad de almacenamiento y reenvío de SWIFTNet FileAct quita la incertidumbre y los inconvenientes de tener que preocuparse de si son o no sus correspondientes en línea en el momento de que transmitir el archivo.</span><span class="sxs-lookup"><span data-stu-id="ded82-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="ded82-125">El archivo se entregará tan pronto como el destinatario está listo para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="ded82-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="ded82-126">Como resultado, proporciona una forma ideal de enviar archivos a un gran número de correspondientes, algunos de los cuales pueden ser en zonas horarias diferentes.</span><span class="sxs-lookup"><span data-stu-id="ded82-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
-   <span data-ttu-id="ded82-127">**Transferencia de archivos en tiempo real.**</span><span class="sxs-lookup"><span data-stu-id="ded82-127">**Real-time file transfer.**</span></span> <span data-ttu-id="ded82-128">Mensajería en tiempo real ofrece una alternativa de bajo costo para almacenar y reenviar para los archivos que están destinados a correspondientes que están en línea en el momento de la transmisión.</span><span class="sxs-lookup"><span data-stu-id="ded82-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="ded82-129">Como resultado es ideal para enviar archivos a unos correspondientes grandes o infraestructuras de mercado.</span><span class="sxs-lookup"><span data-stu-id="ded82-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
-   <span data-ttu-id="ded82-130">**Recuperación de archivos en tiempo real.**</span><span class="sxs-lookup"><span data-stu-id="ded82-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="ded82-131">Se trata de un servicio interactivo que se utiliza normalmente para recuperar los archivos en el contexto de los sistemas basados en la estación de trabajo y a menudo junto con SWIFTNet Examinar.</span><span class="sxs-lookup"><span data-stu-id="ded82-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="ded82-132">Se admite este modo.</span><span class="sxs-lookup"><span data-stu-id="ded82-132">We will support this mode.</span></span>  
  
 <span data-ttu-id="ded82-133">Las características de SWIFTNet FileAct opcionales (en forma de archivo por archivo) se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ded82-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
-   <span data-ttu-id="ded82-134">**Prioridad del mensaje.**</span><span class="sxs-lookup"><span data-stu-id="ded82-134">**Message priority.**</span></span> <span data-ttu-id="ded82-135">Las transferencias de archivos se pueden marcar como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ded82-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
-   <span data-ttu-id="ded82-136">**Notificación de entrega (modos de almacenamiento y reenvío y en tiempo real).**</span><span class="sxs-lookup"><span data-stu-id="ded82-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="ded82-137">Proporciona la confirmación de que el destinatario recibe el archivo.</span><span class="sxs-lookup"><span data-stu-id="ded82-137">Provides confirmation that your correspondent received your file.</span></span>  
  
-   <span data-ttu-id="ded82-138">**Sin rechazo de recepción y de emisión.**</span><span class="sxs-lookup"><span data-stu-id="ded82-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="ded82-139">En caso de conflicto, permite SWIFT confirmar que la transferencia de archivos tuvo lugar como reclamado.</span><span class="sxs-lookup"><span data-stu-id="ded82-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
 <span data-ttu-id="ded82-140">Las características de SWIFTNet FileAct estándares incluyen seguridad SWIFTNet PKI **.**</span><span class="sxs-lookup"><span data-stu-id="ded82-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security **.**</span></span> <span data-ttu-id="ded82-141">SWIFTNet FileAct se protege con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ded82-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
 <span data-ttu-id="ded82-142">Todos los mensajes y archivos intercambiados en SWIFTNet debe someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="ded82-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="ded82-143">Estas comprobaciones se realizan mediante la aplicación de puerta de enlace de SWIFTAlliance (SAG).</span><span class="sxs-lookup"><span data-stu-id="ded82-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded82-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ded82-144">See Also</span></span>  
 <span data-ttu-id="ded82-145">[Introducción a la FileAct e interactuar adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="ded82-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="ded82-146">[¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="ded82-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="ded82-147">¿Qué es el adaptador de interactuar?</span><span class="sxs-lookup"><span data-stu-id="ded82-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)