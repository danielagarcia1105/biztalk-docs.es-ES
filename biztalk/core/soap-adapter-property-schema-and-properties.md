---
title: Esquema de propiedades del adaptador SOAP y propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277516"
---
# <a name="soap-adapter-property-schema-and-properties"></a><span data-ttu-id="d3d3c-102">Propiedades y esquema de propiedades del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="d3d3c-102">SOAP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="d3d3c-103">La tabla siguiente enumera las propiedades incluidas en el esquema de propiedades del adaptador de SOAP.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-103">The following table lists the properties in the SOAP adapter property schema.</span></span>  
  
 <span data-ttu-id="d3d3c-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span><span class="sxs-lookup"><span data-stu-id="d3d3c-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties</span></span>  
  
|<span data-ttu-id="d3d3c-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="d3d3c-105">Name</span></span>|<span data-ttu-id="d3d3c-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="d3d3c-106">Type</span></span>|<span data-ttu-id="d3d3c-107">Description</span><span class="sxs-lookup"><span data-stu-id="d3d3c-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="d3d3c-108">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-108">**AssemblyName**</span></span>|<span data-ttu-id="d3d3c-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-109">xs:string</span></span>|<span data-ttu-id="d3d3c-110">Identifica el tipo .NET y el ensamblado que se va a cargar y a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-110">Identifies the .NET type and assembly to be loaded and executed.</span></span>|  
|<span data-ttu-id="d3d3c-111">**MethodName**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-111">**MethodName**</span></span>|<span data-ttu-id="d3d3c-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-112">xs:string</span></span>|<span data-ttu-id="d3d3c-113">Identifica el método de destino en el ensamblado .NET que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-113">Identifies the target method on the .NET assembly that is to be invoked.</span></span>|  
|<span data-ttu-id="d3d3c-114">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-114">**Username**</span></span>|<span data-ttu-id="d3d3c-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-115">xs:string</span></span>|<span data-ttu-id="d3d3c-116">Nombre de usuario que se utiliza para la autenticación con el servidor.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-116">User name to use for authentication with the server.</span></span>|  
|<span data-ttu-id="d3d3c-117">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-117">**Password**</span></span>|<span data-ttu-id="d3d3c-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-118">xs:string</span></span>|<span data-ttu-id="d3d3c-119">Contraseña de usuario que se utilizará para la autenticación con el servidor.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-119">User password to use for authentication with the server.</span></span>|  
|<span data-ttu-id="d3d3c-120">**ClientCertificate**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-120">**ClientCertificate**</span></span>|<span data-ttu-id="d3d3c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-121">xs:string</span></span>|<span data-ttu-id="d3d3c-122">Huella digital del certificado de cliente SSL.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-122">Thumbprint of the client SSL certificate.</span></span>|  
|<span data-ttu-id="d3d3c-123">**UseProxy**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-123">**UseProxy**</span></span>|<span data-ttu-id="d3d3c-124">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="d3d3c-124">xs:Boolean</span></span>|<span data-ttu-id="d3d3c-125">Especifica si el adaptador de SOAP utilizará un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-125">Specifies whether the SOAP adapter uses a proxy server.</span></span>|  
|<span data-ttu-id="d3d3c-126">**ProxyAddress**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-126">**ProxyAddress**</span></span>|<span data-ttu-id="d3d3c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-127">xs:string</span></span>|<span data-ttu-id="d3d3c-128">Especifica la dirección del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-128">Specifies the proxy server address.</span></span>|  
|<span data-ttu-id="d3d3c-129">**ProxyPort**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-129">**ProxyPort**</span></span>|<span data-ttu-id="d3d3c-130">xs:int</span><span class="sxs-lookup"><span data-stu-id="d3d3c-130">xs:int</span></span>|<span data-ttu-id="d3d3c-131">Especifica el puerto del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-131">Specifies the proxy server port.</span></span>|  
|<span data-ttu-id="d3d3c-132">**ProxyUsername**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-132">**ProxyUsername**</span></span>|<span data-ttu-id="d3d3c-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-133">xs:string</span></span>|<span data-ttu-id="d3d3c-134">Especifica el nombre de usuario para la autenticación con el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-134">Specifies the user name for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="d3d3c-135">**ProxyPassword**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-135">**ProxyPassword**</span></span>|<span data-ttu-id="d3d3c-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-136">xs:string</span></span>|<span data-ttu-id="d3d3c-137">Especifica la contraseña de usuario para la autenticación con el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-137">Specifies the user password for authentication with the proxy server.</span></span>|  
|<span data-ttu-id="d3d3c-138">**UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-138">**UnknownHeaders**</span></span>|<span data-ttu-id="d3d3c-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-139">xs:string</span></span>|<span data-ttu-id="d3d3c-140">Especifica la lista serializada de encabezados SOAP desconocidos.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-140">Specifies the serialized list of unknown SOAP headers.</span></span>|  
|<span data-ttu-id="d3d3c-141">**AffiliateApplicationName**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-141">**AffiliateApplicationName**</span></span>|<span data-ttu-id="d3d3c-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-142">xs:string</span></span>|<span data-ttu-id="d3d3c-143">Define el nombre de la aplicación afiliada que se utilizará para SSO.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-143">Defines the name of the affiliate application to use for SSO.</span></span>|  
|<span data-ttu-id="d3d3c-144">**AuthenticationScheme**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-144">**AuthenticationScheme**</span></span>|<span data-ttu-id="d3d3c-145">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-145">xs:string</span></span>|<span data-ttu-id="d3d3c-146">Especifica el tipo de autenticación que se utilizará con el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-146">Specifies the type of authentication to use with the destination server.</span></span>|  
|<span data-ttu-id="d3d3c-147">**UseSSO**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-147">**UseSSO**</span></span>|<span data-ttu-id="d3d3c-148">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="d3d3c-148">xs:boolean</span></span>|<span data-ttu-id="d3d3c-149">Determina si el adaptador de SOAP utilizará SSO para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-149">Specifies whether the SOAP adapter uses SSO for the send port.</span></span>|  
|<span data-ttu-id="d3d3c-150">**UseHandlerSetting**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-150">**UseHandlerSetting**</span></span>|<span data-ttu-id="d3d3c-151">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="d3d3c-151">xs:boolean</span></span>|<span data-ttu-id="d3d3c-152">Determina si el puerto de envío de SOAP utilizará la configuración del servidor proxy para el controlador.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-152">Specifies whether the SOAP send port uses the proxy configuration for the handler.</span></span>|  
|<span data-ttu-id="d3d3c-153">**ClientConnectionTimeout**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-153">**ClientConnectionTimeout**</span></span>|<span data-ttu-id="d3d3c-154">xs:int</span><span class="sxs-lookup"><span data-stu-id="d3d3c-154">xs:int</span></span>|<span data-ttu-id="d3d3c-155">Especifica el periodo de tiempo de espera de una respuesta por parte del servidor.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-155">Specifies the time-out period of waiting for a response from the server.</span></span> <span data-ttu-id="d3d3c-156">Si se establece como cero (0), el sistema calculará el tiempo de espera en función del tamaño del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-156">If set to zero (0), the system will calculate the time-out based on the request message size.</span></span>|  
|<span data-ttu-id="d3d3c-157">**UserDefined**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-157">**UserDefined**</span></span>|<span data-ttu-id="d3d3c-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3d3c-158">xs:string</span></span>|<span data-ttu-id="d3d3c-159">Define las clases definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-159">Defines user-defined classes.</span></span>|  
|<span data-ttu-id="d3d3c-160">**UseSoap12**</span><span class="sxs-lookup"><span data-stu-id="d3d3c-160">**UseSoap12**</span></span>|<span data-ttu-id="d3d3c-161">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="d3d3c-161">xs:boolean</span></span>|<span data-ttu-id="d3d3c-162">Especifica si se genera código de proxy que admita el protocolo SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="d3d3c-162">Specifies whether to generate proxy code that supports the SOAP 1.2 protocol.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3d3c-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3d3c-163">See Also</span></span>  
 [<span data-ttu-id="d3d3c-164">Configurar el adaptador SOAP</span><span class="sxs-lookup"><span data-stu-id="d3d3c-164">Configuring the SOAP Adapter</span></span>](../core/configuring-the-soap-adapter.md)