---
title: Usar el direccionamiento IPv6 con adaptadores de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5726d5b05c548fd728228fcad39e56ce535fbb5
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710627"
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="d8973-102">Usar el direccionamiento de IPv6 de los adaptadores de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d8973-102">Using IPv6 Addressing with BizTalk Adapters</span></span>
<span data-ttu-id="d8973-103">Adaptadores de BizTalk Server admiten el uso del direccionamiento IPv6.</span><span class="sxs-lookup"><span data-stu-id="d8973-103">BizTalk Server adapters support the use of IPv6 addressing.</span></span> <span data-ttu-id="d8973-104">Este tema describe la nomenclatura que debe utilizarse para especificar una dirección IPv6 para una ruta UNC, la nomenclatura para especificar una dirección IPv6 literal y el uso de identificadores de ámbito IPv6 con los adaptadores de HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="d8973-104">This topic describes the nomenclature that should be used to specify an IPv6 address for a UNC path, the nomenclature for specifying a literal IPv6 address, and the use of IPv6 scope identifiers with the HTTP and SOAP adapters.</span></span>  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a><span data-ttu-id="d8973-105">Nomenclatura de dirección IPv6 utilizada para una ruta UNC</span><span class="sxs-lookup"><span data-stu-id="d8973-105">IPv6 Address Nomenclature Used for a UNC Path</span></span>  
 <span data-ttu-id="d8973-106">Siga estos pasos para especificar una dirección IPv6 literal en una ruta UNC:</span><span class="sxs-lookup"><span data-stu-id="d8973-106">Follow these steps when specifying a literal IPv6 address in a UNC path:</span></span>  
  
1.  <span data-ttu-id="d8973-107">Reemplace cualquier carácter de dos puntos ":" por un guión "-" caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8973-107">Replace any colon ":" characters with a dash "-" character.</span></span>  
  
2.  <span data-ttu-id="d8973-108">Agregue el texto "**. IPv6-literal.net**" a la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="d8973-108">Append the text "**.ipv6-literal.net**" to the IP address.</span></span>  
  
 <span data-ttu-id="d8973-109">Por ejemplo, la nomenclatura de un URI que señale a un recurso compartido en un equipo con la dirección IPv6 2001:DB8:2a:1005:230:48ff:fe73:989d sería:</span><span class="sxs-lookup"><span data-stu-id="d8973-109">For example, the nomenclature for a URI that points to a file share on a computer with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 <span data-ttu-id="d8973-110">Donde \< *sharename* \> es el nombre del recurso compartido de archivos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d8973-110">Where \<*sharename*\> is the name of the file share on the target computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8973-111">Asegúrese de que las cuentas de usuario para las instancias de host que están ejecutando los controladores de envío y recepción de archivos tienen los permisos adecuados para el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="d8973-111">Ensure that the user accounts for the host instances that the File send and receive handlers are running in have appropriate permissions to the file share.</span></span> <span data-ttu-id="d8973-112">Para obtener más información acerca de los permisos de carpeta necesarios para recibir archivos con el adaptador de archivo vea [configurar un controlador de recepción de archivo](../core/configure-the-file-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="d8973-112">For more information about the folder permissions required to receive files with the File adapter see [Configure a File Receive Handler](../core/configure-the-file-adapter.md).</span></span> <span data-ttu-id="d8973-113">Para obtener más información acerca de los permisos de carpeta necesarios para enviar archivos con el adaptador de archivo vea [problemas conocidos relacionados con el adaptador de archivo](../core/known-issues-with-the-file-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="d8973-113">For more information about the folder permissions required when sending files with the File adapter see [Known Issues with the File Adapter](../core/known-issues-with-the-file-adapter.md).</span></span> <span data-ttu-id="d8973-114">Para obtener información acerca de los sistemas de archivos que se admiten para su uso con el adaptador de archivo, consulte [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span><span class="sxs-lookup"><span data-stu-id="d8973-114">For information about the file systems that are supported for use with the File adapter, see [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span></span>  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a><span data-ttu-id="d8973-115">Usar identificadores de ámbito de IPv6 con el adaptador de HTTP y el adaptador de envío de SOAP</span><span class="sxs-lookup"><span data-stu-id="d8973-115">Using IPv6 Scope Identifiers with the HTTP Adapter and the SOAP Send Adapter</span></span>  
 <span data-ttu-id="d8973-116">HTTP de envío y recepción de adaptador y el adaptador de envío SOAP requieren que si se utiliza un identificador de ámbito en una dirección IPv6, el identificador de ámbito debe ser caracteres de escape con el código de escape **% 25**.</span><span class="sxs-lookup"><span data-stu-id="d8973-116">The HTTP send and receive adapter and the SOAP send adapter require that if a scope identifier is used in an IPv6 address, the scope identifier must be escaped with the escape code **%25**.</span></span> <span data-ttu-id="d8973-117">Por ejemplo, **fe80::550c:489f:e65e:aef3 %8** es una dirección IPv6 válida que contiene un identificador de ámbito (%8).</span><span class="sxs-lookup"><span data-stu-id="d8973-117">For example, **fe80::550c:489f:e65e:aef3%8** is a valid IPv6 address containing a scope identifier (%8).</span></span> <span data-ttu-id="d8973-118">Para utilizar esta dirección IPv6 con los adaptadores de envío y recepción de HTTP o el adaptador de envío de SOAP, el identificador de ámbito debe ir acompañado del carácter de escape del modo que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="d8973-118">To use this IPv6 address with the HTTP send and receive adapters or the SOAP send adapter, the scope identifier must be escaped as follows:</span></span>  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a><span data-ttu-id="d8973-119">Nomenclatura de URI de adaptador utilizada para una dirección IPv6 literal</span><span class="sxs-lookup"><span data-stu-id="d8973-119">Adapter URI Nomenclature Used for a Literal IPv6 Address</span></span>  
  
-   <span data-ttu-id="d8973-120">Para utilizar una dirección IPv6 literal para un URI de adaptador, encierre la dirección IP entre corchetes "[", "]".</span><span class="sxs-lookup"><span data-stu-id="d8973-120">To use a literal IPv6 address for an adapter URI, enclose the IP address in square brackets "[", "]".</span></span> <span data-ttu-id="d8973-121">Por ejemplo, la nomenclatura de un URI que con la dirección IPv6 2001:DB8:2a:1005:230:48ff:fe73:989d sería:</span><span class="sxs-lookup"><span data-stu-id="d8973-121">For example, the nomenclature for a URI with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d8973-122">El uso de un literal de las direcciones IPv6 de adaptador URI sigue las instrucciones establecidas en [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span><span class="sxs-lookup"><span data-stu-id="d8973-122">The use of literal IPv6 addresses for adapter URIs follows the guidelines established in [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span></span>  
  
-   <span data-ttu-id="d8973-123">Al especificar una dirección IPv6 literal como nombre del servidor para el adaptador de recepción POP3, el adaptador de envío SMTP o los adaptadores de envío y recepción SQL, la dirección IPv6 no deberá encerrarse entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="d8973-123">When specifying a literal IPv6 address as the server name for the POP3 receive adapter, the SMTP send adapter, or the SQL send and receive adapters, the IPv6 address should not be enclosed in square brackets.</span></span>  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="d8973-124">Resumen de consideraciones cuando se utiliza el direccionamiento IPv6 literal con adaptadores de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d8973-124">Summary of Considerations When Using Literal IPv6 Addressing with BizTalk Adapters</span></span>  
 <span data-ttu-id="d8973-125">La tabla siguiente resumen cuando el uso de una dirección IPv6 literal requiere que la dirección IP vaya entre corchetes "[", "]" y cuando el identificador de ámbito que se utiliza en una dirección IPv6 debe ir acompañado de un carácter de escape:</span><span class="sxs-lookup"><span data-stu-id="d8973-125">The table below summarizes when the use of a literal IPv6 address requires that the IP address is enclosed in square brackets "[", "]" and when a scope identifier that is used in an IPv6 address must be escaped:</span></span>  
  
|<span data-ttu-id="d8973-126">Adaptador</span><span class="sxs-lookup"><span data-stu-id="d8973-126">Adapter</span></span>|<span data-ttu-id="d8973-127">¿Necesita que la dirección IPv6 literal vaya entre corchetes?</span><span class="sxs-lookup"><span data-stu-id="d8973-127">Requires that literal IPv6 address is enclosed in square brackets?</span></span>|<span data-ttu-id="d8973-128">¿Necesita que el identificador de ámbito vaya acompañado de un carácter de escape?</span><span class="sxs-lookup"><span data-stu-id="d8973-128">Requires that scope identifier is escaped?</span></span>|  
|---|---|---|  
|<span data-ttu-id="d8973-129">Recepción de POP3</span><span class="sxs-lookup"><span data-stu-id="d8973-129">POP3 receive</span></span>|<span data-ttu-id="d8973-130">no</span><span class="sxs-lookup"><span data-stu-id="d8973-130">No</span></span>|<span data-ttu-id="d8973-131">no</span><span class="sxs-lookup"><span data-stu-id="d8973-131">No</span></span>|  
|<span data-ttu-id="d8973-132">Envío de SMTP</span><span class="sxs-lookup"><span data-stu-id="d8973-132">SMTP send</span></span>|<span data-ttu-id="d8973-133">no</span><span class="sxs-lookup"><span data-stu-id="d8973-133">No</span></span>|<span data-ttu-id="d8973-134">no</span><span class="sxs-lookup"><span data-stu-id="d8973-134">No</span></span>|  
|<span data-ttu-id="d8973-135">Envío y recepción de SQL</span><span class="sxs-lookup"><span data-stu-id="d8973-135">SQL send and receive</span></span>|<span data-ttu-id="d8973-136">no</span><span class="sxs-lookup"><span data-stu-id="d8973-136">No</span></span>|<span data-ttu-id="d8973-137">no</span><span class="sxs-lookup"><span data-stu-id="d8973-137">No</span></span>|  
|<span data-ttu-id="d8973-138">Envío y recepción de archivos</span><span class="sxs-lookup"><span data-stu-id="d8973-138">File send and receive</span></span>|<span data-ttu-id="d8973-139">No (consulte la sección **nomenclatura de dirección IPv6 utiliza para una ruta de acceso UNC**)</span><span class="sxs-lookup"><span data-stu-id="d8973-139">No (see section **IPv6 Address Nomenclature Used for a UNC Path**)</span></span>|<span data-ttu-id="d8973-140">no</span><span class="sxs-lookup"><span data-stu-id="d8973-140">No</span></span>|  
|<span data-ttu-id="d8973-141">Envío y recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="d8973-141">HTTP send and receive</span></span>|<span data-ttu-id="d8973-142">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-142">Yes</span></span>|<span data-ttu-id="d8973-143">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-143">Yes</span></span>|  
|<span data-ttu-id="d8973-144">Envío y recepción de MQSeries</span><span class="sxs-lookup"><span data-stu-id="d8973-144">MQSeries send and receive</span></span>|<span data-ttu-id="d8973-145">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-145">Yes</span></span>|<span data-ttu-id="d8973-146">no</span><span class="sxs-lookup"><span data-stu-id="d8973-146">No</span></span>|  
|<span data-ttu-id="d8973-147">Envío y recepción de MSMQ</span><span class="sxs-lookup"><span data-stu-id="d8973-147">MSMQ send and receive</span></span>|<span data-ttu-id="d8973-148">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-148">Yes</span></span>|<span data-ttu-id="d8973-149">no</span><span class="sxs-lookup"><span data-stu-id="d8973-149">No</span></span>|  
|<span data-ttu-id="d8973-150">Envío de SOAP</span><span class="sxs-lookup"><span data-stu-id="d8973-150">SOAP send</span></span>|<span data-ttu-id="d8973-151">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-151">Yes</span></span>|<span data-ttu-id="d8973-152">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-152">Yes</span></span>|  
|<span data-ttu-id="d8973-153">Recepción de SOAP</span><span class="sxs-lookup"><span data-stu-id="d8973-153">SOAP receive</span></span>|<span data-ttu-id="d8973-154">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-154">Yes</span></span>|<span data-ttu-id="d8973-155">no</span><span class="sxs-lookup"><span data-stu-id="d8973-155">No</span></span>|  
|<span data-ttu-id="d8973-156">Envío y recepción de WCF</span><span class="sxs-lookup"><span data-stu-id="d8973-156">WCF send and receive</span></span>|<span data-ttu-id="d8973-157">Sí</span><span class="sxs-lookup"><span data-stu-id="d8973-157">Yes</span></span>|<span data-ttu-id="d8973-158">no</span><span class="sxs-lookup"><span data-stu-id="d8973-158">No</span></span>|