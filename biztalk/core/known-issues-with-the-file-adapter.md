---
title: Problemas conocidos con el adaptador de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2690803346efc5931a88acd70be9d24af107156f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262892"
---
# <a name="known-issues-with-the-file-adapter"></a><span data-ttu-id="9875c-102">Problemas conocidos del adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="9875c-102">Known Issues with the File Adapter</span></span>
<span data-ttu-id="9875c-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="9875c-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="9875c-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="9875c-104">Known Issues</span></span>  
  
#### <a name="a-file-receive-location-is-disabled"></a><span data-ttu-id="9875c-105">Una ubicación de recepción de archivo está deshabilitada</span><span class="sxs-lookup"><span data-stu-id="9875c-105">A File Receive Location is Disabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9875c-106">Problema</span><span class="sxs-lookup"><span data-stu-id="9875c-106">Problem</span></span>  
 <span data-ttu-id="9875c-107">Una ubicación de recepción de archivo pasa a estar deshabilitada</span><span class="sxs-lookup"><span data-stu-id="9875c-107">A File receive location becomes disabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9875c-108">Causa</span><span class="sxs-lookup"><span data-stu-id="9875c-108">Cause</span></span>  
 <span data-ttu-id="9875c-109">El adaptador de recepción de archivo deshabilita la ubicación de recepción en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9875c-109">The File receive adapter disables the receive location if any of the following occur:</span></span>  
  
-   <span data-ttu-id="9875c-110">El adaptador de recepción de archivo no puede obtener acceso a la ubicación de recepción del sistema de archivos o del recurso compartido de red porque no existe la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="9875c-110">The File receive adapter cannot access the receive location on the file system or network share because the specified path does not exist.</span></span> <span data-ttu-id="9875c-111">En el caso de un recurso compartido de red, el adaptador de recepción de archivo deshabilita la ubicación de recepción tras agotar todos los reintentos.</span><span class="sxs-lookup"><span data-stu-id="9875c-111">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="9875c-112">El adaptador de recepción de archivo no puede obtener acceso a la ubicación de recepción del sistema de archivos o del recurso compartido de red porque la cuenta utilizada por la instancia de host asociada no tiene permiso de lectura y escritura para esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="9875c-112">The File receive adapter cannot access the receive location on the file system or network share because the account used by the associated host instance does not have read-write permission for that location.</span></span> <span data-ttu-id="9875c-113">En el caso de un recurso compartido de red, el adaptador de recepción de archivo deshabilita la ubicación de recepción tras agotar todos los reintentos.</span><span class="sxs-lookup"><span data-stu-id="9875c-113">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="9875c-114">Los archivos con nombres de longitud superior a 256 caracteres se encuentran en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9875c-114">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9875c-115">Solución</span><span class="sxs-lookup"><span data-stu-id="9875c-115">Resolution</span></span>  
  
-   <span data-ttu-id="9875c-116">Asegúrese de que la ruta de acceso o el recurso compartido especificados existen.</span><span class="sxs-lookup"><span data-stu-id="9875c-116">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="9875c-117">Asegúrese de que la cuenta usada como el **inicio de sesión:** tiene lectura cuenta para el archivo de instancia de host de controlador de recepción y ubicación de recepción de permisos de escritura a los especificados.</span><span class="sxs-lookup"><span data-stu-id="9875c-117">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="9875c-118">Asegúrese de que los nombres de los archivos escritos en la carpeta supervisada por el adaptador de recepción de archivo no superen los 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9875c-118">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a><span data-ttu-id="9875c-119">No se leen los archivos de la ubicación de recepción especificada</span><span class="sxs-lookup"><span data-stu-id="9875c-119">Files Are Not Being Read from the Specified Receive Location</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9875c-120">Problema</span><span class="sxs-lookup"><span data-stu-id="9875c-120">Problem</span></span>  
 <span data-ttu-id="9875c-121">El adaptador de recepción de archivo no lee un archivo de la ubicación de recepción especificada.</span><span class="sxs-lookup"><span data-stu-id="9875c-121">The File receive adapter does not read a file from the specified receive location.</span></span> <span data-ttu-id="9875c-122">Cuando un adaptador de recepción de archivo encuentra un archivo de este tipo, registra un error en el registro de eventos y deja el archivo en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9875c-122">When the File receive adapter encounters such a file, it logs an error in the event log and leaves the file in the receive location.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9875c-123">Causa</span><span class="sxs-lookup"><span data-stu-id="9875c-123">Cause</span></span>  
 <span data-ttu-id="9875c-124">El adaptador de recepción de archivo no lee un archivo de la ubicación de recepción en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9875c-124">The File receive adapter does not read a file from the receive location if any of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="9875c-125">El archivo es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9875c-125">The file is read-only.</span></span>  
  
-   <span data-ttu-id="9875c-126">El archivo tiene un atributo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9875c-126">The file has a system attribute.</span></span>  
  
-   <span data-ttu-id="9875c-127">El adaptador de recepción de archivo no tiene permisos para leer el archivo y escribir en él.</span><span class="sxs-lookup"><span data-stu-id="9875c-127">The File receive adapter does not have permissions to read and write to the file.</span></span>  
  
-   <span data-ttu-id="9875c-128">Los archivos con nombres de longitud superior a 256 caracteres se encuentran en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9875c-128">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9875c-129">Solución</span><span class="sxs-lookup"><span data-stu-id="9875c-129">Resolution</span></span>  
  
-   <span data-ttu-id="9875c-130">Asegúrese de que los archivos de la ubicación de recepción especificada no estén marcados como "sólo lectura".</span><span class="sxs-lookup"><span data-stu-id="9875c-130">Ensure that the files in the specified receive location are not marked as "read only".</span></span>  
  
-   <span data-ttu-id="9875c-131">Asegúrese de que los archivos de la ubicación de recepción especificada no estén marcados con un atributo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9875c-131">Ensure that the files in the specified receive location are not marked with a system attribute.</span></span>  
  
-   <span data-ttu-id="9875c-132">Asegúrese de que la cuenta usada como el **inicio de sesión:** tiene lectura cuenta para el archivo de instancia de host de controlador de recepción y ubicación de recepción de permisos de escritura a los especificados.</span><span class="sxs-lookup"><span data-stu-id="9875c-132">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="9875c-133">Asegúrese de que los nombres de los archivos escritos en la carpeta supervisada por el adaptador de recepción de archivo no superen los 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9875c-133">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a><span data-ttu-id="9875c-134">El adaptador de envío de archivo no envía mensajes</span><span class="sxs-lookup"><span data-stu-id="9875c-134">Messages Are Not Being Sent by the File Send Adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9875c-135">Problema</span><span class="sxs-lookup"><span data-stu-id="9875c-135">Problem</span></span>  
 <span data-ttu-id="9875c-136">El adaptador de envío de archivo no envía un mensaje al directorio o recurso compartido de archivos especificado.</span><span class="sxs-lookup"><span data-stu-id="9875c-136">The File send adapter fails to send a message to the specified directory or file share.</span></span>  
  
 <span data-ttu-id="9875c-137">Si un mensaje no se puede escribir en el directorio o recurso compartido de archivos especificado, se escribirá un error en el registro de eventos del equipo del servidor de BizTalk y se producirá la cadena de eventos siguiente:</span><span class="sxs-lookup"><span data-stu-id="9875c-137">If a message fails to be written to the specified directory or file share, an error is written to the Event log of the BizTalk server computer and the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="9875c-138">El adaptador de envío de archivo volverá a intentar la operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="9875c-138">The File send adapter will retry the write operation.</span></span>  
  
2.  <span data-ttu-id="9875c-139">El adaptador de archivo intentará entregar el archivo mediante el transporte de reserva (si está configurado).</span><span class="sxs-lookup"><span data-stu-id="9875c-139">The File adapter will attempt to deliver the file using the backup transport (if configured).</span></span>  
  
3.  <span data-ttu-id="9875c-140">El mensaje se escribirá en la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="9875c-140">The message will be written to the suspended queue.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9875c-141">Causa</span><span class="sxs-lookup"><span data-stu-id="9875c-141">Cause</span></span>  
  
-   <span data-ttu-id="9875c-142">El adaptador de envío de archivo no puede obtener acceso al directorio desde el que se envían los archivos del sistema de archivos o del recurso compartido de red porque no existe la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="9875c-142">The File send adapter cannot access the directory that files are sent from on the file system or network share because the specified path does not exist.</span></span>  
  
-   <span data-ttu-id="9875c-143">El adaptador de envío de archivo no puede escribir en un archivo de la ubicación de destino del sistema de archivos o del recurso compartido de red porque la instancia de host asociada no cuenta con permiso de escritura para ese archivo o esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="9875c-143">The File send adapter cannot write to a file in the destination location on the file system or network share because the associated host instance does not have write permissions for that file or for that location.</span></span>  
  
-   <span data-ttu-id="9875c-144">El adaptador de envío de archivos no puede escribir en el archivo especificado porque es de solo lectura o se marca con la **system** atributo de archivo.</span><span class="sxs-lookup"><span data-stu-id="9875c-144">The File send adapter cannot write to the file specified because it is read-only or is marked with the **system** file attribute.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9875c-145">Solución</span><span class="sxs-lookup"><span data-stu-id="9875c-145">Resolution</span></span>  
  
-   <span data-ttu-id="9875c-146">Asegúrese de que la ruta de acceso o el recurso compartido especificados existen.</span><span class="sxs-lookup"><span data-stu-id="9875c-146">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="9875c-147">Asegúrese de que la cuenta usada como el **inicio de sesión:** cuenta para la instancia de host del controlador de envío de archivo con permisos lectura / escritura al recurso compartido de archivo o directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="9875c-147">Ensure that the account used as the **Logon:** account for the File send handler host instance has read and write permissions to the specified directory or file share.</span></span>  
  
-   <span data-ttu-id="9875c-148">Asegúrese de que los archivos existentes en el directorio o en el recurso compartido de archivos especificado no estén marcados con el atributo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9875c-148">Ensure that existing files in the specified directory or file share are not marked with the system attribute.</span></span>  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a><span data-ttu-id="9875c-149">El envío de un archivo mediante el adaptador de archivo es muy lento</span><span class="sxs-lookup"><span data-stu-id="9875c-149">Sending a file using the File adapter is very slow</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9875c-150">Problema</span><span class="sxs-lookup"><span data-stu-id="9875c-150">Problem</span></span>  
 <span data-ttu-id="9875c-151">Rendimiento del adaptador de envío de archivos es más lento cuando la **Permitir caché durante la escritura** propiedad está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="9875c-151">Performance of the File send adapter is slower when the **Allow cache on write** property is set to **False**.</span></span> <span data-ttu-id="9875c-152">El **Permitir caché durante la escritura** propiedad está establecida en **False** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9875c-152">The **Allow cache on write** property is set to **False** by default.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9875c-153">Causa</span><span class="sxs-lookup"><span data-stu-id="9875c-153">Cause</span></span>  
 <span data-ttu-id="9875c-154">Establecer el **Permitir caché durante la escritura** propiedad **False** puede reducir el rendimiento ya que esta configuración impide que el uso de en la memoria de almacenamiento en caché de archivos por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9875c-154">Setting the **Allow cache on write** property to **False** can reduce performance as this setting disallows the use of in-memory caching of files by the operating system.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9875c-155">Solución</span><span class="sxs-lookup"><span data-stu-id="9875c-155">Resolution</span></span>  
 <span data-ttu-id="9875c-156">Para aumentar el rendimiento del archivo enviar cambios de adaptador el **Permitir caché durante la escritura** propiedad **True** (casilla).</span><span class="sxs-lookup"><span data-stu-id="9875c-156">To increase performance of the File send adapter change the **Allow cache on write** property to **True** (check the box).</span></span> <span data-ttu-id="9875c-157">Para obtener más información sobre la **Permitir caché durante la escritura** propiedad, vea [cómo configurar un puerto de envío de archivo](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span><span class="sxs-lookup"><span data-stu-id="9875c-157">For more information about the **Allow cache on write** property, see [How to Configure a File Send Port](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9875c-158">Establecer el **Permitir caché durante la escritura** propiedad **True** aumenta la posibilidad de pérdida de datos en caso de que el sistema operativo experimenta un error.</span><span class="sxs-lookup"><span data-stu-id="9875c-158">Setting the **Allow cache on write** property to **True** increases the possibility of data loss in the event that the operating system experiences a failure.</span></span> <span data-ttu-id="9875c-159">En este escenario, se perderá cualquier dato que se almacene en la caché de archivos en memoria.</span><span class="sxs-lookup"><span data-stu-id="9875c-159">In this scenario, any data that is stored in the in-memory file cache will be lost.</span></span>  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a><span data-ttu-id="9875c-160">El adaptador de archivo elimina los archivos recibidos de cero bytes</span><span class="sxs-lookup"><span data-stu-id="9875c-160">Zero byte files received by the File adapter are deleted</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9875c-161">Problema</span><span class="sxs-lookup"><span data-stu-id="9875c-161">Problem</span></span>  
 <span data-ttu-id="9875c-162">Si el adaptador de recepción de archivo recoge un archivo vacío (de cero bytes), éste se elimina y se escribe una advertencia similar a la siguiente en el registro de aplicaciones del servidor BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="9875c-162">If an empty (zero byte) file is picked up by the File receive adapter, the file is deleted and a warning similar to the following is written to the application log of the BizTalk server:</span></span>  
  
```  
Event Type:Warning  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:7182  
Date:8/30/2006  
Time:1:32:32 PM  
User:N/A  
Computer:BIZTALKSERVER  
Description:  
The FILE receive adapter deleted the empty file "C:\filesource\emptyfile.xml.BTS-WIP" without performing any processing.  
```  
  
##### <a name="cause"></a><span data-ttu-id="9875c-163">Causa</span><span class="sxs-lookup"><span data-stu-id="9875c-163">Cause</span></span>  
 <span data-ttu-id="9875c-164">El adaptador de recepción de archivo está diseñado para eliminar los archivos de cero bytes.</span><span class="sxs-lookup"><span data-stu-id="9875c-164">The File receive adapter deletes zero byte files by design.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9875c-165">Solución</span><span class="sxs-lookup"><span data-stu-id="9875c-165">Resolution</span></span>  
 <span data-ttu-id="9875c-166">No es necesaria ninguna acción; este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="9875c-166">No action is required, this behavior is by design.</span></span>