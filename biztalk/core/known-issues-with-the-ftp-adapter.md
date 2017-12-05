---
title: Problemas conocidos con el adaptador de FTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13ce12e8514eaa2b5843ba81eff4f505e65d9e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-the-ftp-adapter"></a><span data-ttu-id="dc8ec-102">Problemas conocidos del adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="dc8ec-102">Known Issues with the FTP Adapter</span></span>
<span data-ttu-id="dc8ec-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="dc8ec-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="dc8ec-104">Known Issues</span></span>  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a><span data-ttu-id="dc8ec-105">Puede que se dupliquen o se pierdan datos cuando reciba datos en BizTalk Server mediante el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-105">Data may be duplicated or lost when you receive data in BizTalk Server by using the FTP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc8ec-106">Problema</span><span class="sxs-lookup"><span data-stu-id="dc8ec-106">Problem</span></span>  
 <span data-ttu-id="dc8ec-107">Se duplican o se pierde cuando se reciben los datos en datos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-107">Data is duplicated or lost when you receive data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the FTP Adapter.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc8ec-108">Causa</span><span class="sxs-lookup"><span data-stu-id="dc8ec-108">Cause</span></span>  
 <span data-ttu-id="dc8ec-109">El adaptador de FTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el protocolo de cliente de FTP para sondear el servidor FTP designado y recupera datos del servidor “como tal”.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter uses the FTP client protocol to poll the designated FTP server and retrieves data from the server "as is."</span></span> <span data-ttu-id="dc8ec-110">El adaptador de FTP no valida los datos que recupera.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-110">The FTP adapter does not validate any data that it retrieves.</span></span> <span data-ttu-id="dc8ec-111">El adaptador de FTP envía el documento recuperado al motor de mensajería de BizTalk para procesarlo y luego elimina el documento original desde el servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-111">The FTP adapter sends the retrieved document to the BizTalk Messaging Engine for processing and then it deletes the original document from the FTP server.</span></span> <span data-ttu-id="dc8ec-112">Si el adaptador de FTP recupera un documento del servidor FTP que todavía está escribiendo la aplicación de host, el documento recuperado estará incompleto.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-112">If the FTP adapter retrieves a document from the FTP server that is still being written to by the host application, the retrieved document will be incomplete.</span></span> <span data-ttu-id="dc8ec-113">Si el adaptador de FTP recupera una copia incompleta del documento original, puede que se produzca la duplicación o pérdida de datos en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc8ec-113">If the FTP adapter retrieves an incomplete copy of the original document, data duplication or data loss may occur in the following scenarios:</span></span>  
  
-   <span data-ttu-id="dc8ec-114">Si la aplicación de host todavía está escribiendo el documento original en el servidor FTP, el adaptador de FTP no podrá eliminar el documento y recuperará otra copia del documento en el intervalo de sondeo que está configurado para la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-114">If the original document is still being written to the FTP server by the host application, the FTP adapter cannot delete the document and will retrieve another copy of the document at the next polling interval that is configured for the receive location.</span></span> <span data-ttu-id="dc8ec-115">De este modo se produce la duplicación del documento.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-115">This behavior causes document duplication to occur.</span></span>  
  
-   <span data-ttu-id="dc8ec-116">Si la aplicación de host ha terminado de escribir el documento en el servidor FTP, el documento se eliminará.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-116">If the host application has finished writing the document to the FTP server, the document will be deleted.</span></span> <span data-ttu-id="dc8ec-117">De este modo se produce la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-117">This behavior will cause data loss to occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc8ec-118">Solución</span><span class="sxs-lookup"><span data-stu-id="dc8ec-118">Resolution</span></span>  
 <span data-ttu-id="dc8ec-119">Para solucionar este comportamiento, utilice uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc8ec-119">To work around this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="dc8ec-120">Configure la aplicación de host para escribir en una carpeta temporal del mismo disco duro que la carpeta pública de FTP y mueva periódicamente el contenido de la carpeta temporal a la carpeta de FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-120">Configure the host application to write to a temporary folder on the same hard disk as the public FTP folder and to periodically move the contents of the temporary folder to the FTP folder.</span></span> <span data-ttu-id="dc8ec-121">La carpeta temporal debe estar en el mismo disco duro que la carpeta pública de FTP para garantizar que la operación de desplazamiento sea atómica.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-121">The temporary folder should be on the same hard disk as the public FTP folder to make sure that the move operation is atomic.</span></span> <span data-ttu-id="dc8ec-122">Una operación atómica es una operación funcionalmente indivisible.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-122">An atomic operation is an operation that is functionally indivisible.</span></span> <span data-ttu-id="dc8ec-123">Si escribir datos en la carpeta pública de FTP mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptador de FTP, puede hacerlo mediante la especificación de una propiedad de la carpeta temporal en el cuadro de diálogo Propiedades de transporte FTP cuando se configura un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-123">If you write data to the public FTP folder by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter, you can do this by specifying a Temporary Folder property in the FTP Transport Properties dialog box when you configure a send port.</span></span> <span data-ttu-id="dc8ec-124">Si especifica una propiedad de carpeta temporal, asegúrese de que esta carpeta reside en el mismo disco físico que la carpeta pública de FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-124">If you specify a Temporary Folder property, make sure that this folder is on the same physical disk as the public FTP folder.</span></span>  
  
-   <span data-ttu-id="dc8ec-125">Configure la ubicación de recepción FTP para operar en una ventana de servicio cuando la aplicación de host no escriba datos en el servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-125">Configure the FTP receive location to operate within a service window when the host application is not writing data to the FTP server.</span></span> <span data-ttu-id="dc8ec-126">Puede determinar la ventana de servicio cuando configura las propiedades de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-126">You can specify the service window when you configure the receive location properties.</span></span>  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a><span data-ttu-id="dc8ec-127">El adaptador FTP no admite la comprobación de revocaciones en los certificados del servidor</span><span class="sxs-lookup"><span data-stu-id="dc8ec-127">FTP Adapter does not support revocation checks on the server certificates</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc8ec-128">Problema</span><span class="sxs-lookup"><span data-stu-id="dc8ec-128">Problem</span></span>  
 <span data-ttu-id="dc8ec-129">El adaptador de FTP en BizTalk Server se ha mejorado para admitir la transferencia de archivos de forma segura a y desde un servidor FTPS mediante SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-129">The FTP adapter in BizTalk Server is enhanced to support secure file transfer to and from an FTPS server using SSL/TLS.</span></span> <span data-ttu-id="dc8ec-130">La lista de revocación de certificados (CRL) contiene una lista de certificados que se han revocado y que ya no son válidos.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-130">The Certificate Revocation List (CRL) contains a list of certificates that have been revoked and are no longer valid.</span></span> <span data-ttu-id="dc8ec-131">El adaptador FTP no consulta la CRL para autenticar el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-131">The FTP adapter does not consult the CRL for authenticating the server certificate.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc8ec-132">Causa</span><span class="sxs-lookup"><span data-stu-id="dc8ec-132">Cause</span></span>  
 <span data-ttu-id="dc8ec-133">Por diseño, el adaptador FTP no consulta la CRL antes de aceptar un certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-133">By design, the FTP adapter does not consult the CRL before accepting a server certificate.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc8ec-134">Solución</span><span class="sxs-lookup"><span data-stu-id="dc8ec-134">Resolution</span></span>  
 <span data-ttu-id="dc8ec-135">Se requiere; ninguna acción Este comportamiento es así por diseño.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-135">No action is required; this behavior is by design.</span></span>  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a><span data-ttu-id="dc8ec-136">El adaptador FTP descarga archivos más grandes que el tamaño máximo de archivo</span><span class="sxs-lookup"><span data-stu-id="dc8ec-136">FTP Adapter downloads files larger than Max File Size</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc8ec-137">Problema</span><span class="sxs-lookup"><span data-stu-id="dc8ec-137">Problem</span></span>  
 <span data-ttu-id="dc8ec-138">El adaptador de recepción FTP descarga archivos cuyo tamaño es mayor que el especificado en la propiedad de tamaño máximo de archivo de los siguientes servidores FTP:</span><span class="sxs-lookup"><span data-stu-id="dc8ec-138">The FTP receive adapter downloads files whose size is larger than the specified Max File Size property from the following FTP servers:</span></span>  
  
-   <span data-ttu-id="dc8ec-139">AIX</span><span class="sxs-lookup"><span data-stu-id="dc8ec-139">AIX</span></span>  
  
-   <span data-ttu-id="dc8ec-140">MVS</span><span class="sxs-lookup"><span data-stu-id="dc8ec-140">MVS</span></span>  
  
-   <span data-ttu-id="dc8ec-141">AS400</span><span class="sxs-lookup"><span data-stu-id="dc8ec-141">AS400</span></span>  
  
-   <span data-ttu-id="dc8ec-142">GXS</span><span class="sxs-lookup"><span data-stu-id="dc8ec-142">GXS</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc8ec-143">Causa</span><span class="sxs-lookup"><span data-stu-id="dc8ec-143">Cause</span></span>  
 <span data-ttu-id="dc8ec-144">Por diseño, el adaptador FTP no respeta el tamaño máximo de archivo al descargar archivos de estos servidores FTP.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-144">By design, the FTP adapter does not respect the maximum file size when downloading files from these FTP servers.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc8ec-145">Solución</span><span class="sxs-lookup"><span data-stu-id="dc8ec-145">Resolution</span></span>  
 <span data-ttu-id="dc8ec-146">Se requiere; ninguna acción Este comportamiento es así por diseño.</span><span class="sxs-lookup"><span data-stu-id="dc8ec-146">No action is required; this behavior is by design.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8ec-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc8ec-147">See Also</span></span>  
 <span data-ttu-id="dc8ec-148">[Cómo configurar ubicación de recepción de FTP](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span><span class="sxs-lookup"><span data-stu-id="dc8ec-148">[How to Configure an FTP Receive Location](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span></span>  
 [<span data-ttu-id="dc8ec-149">Solucionar problemas del adaptador FTP</span><span class="sxs-lookup"><span data-stu-id="dc8ec-149">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)