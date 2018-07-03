---
title: Error al obtener las extensiones de enlace de machine.config. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c65c0341941634bb11bd058bfcbe9c365c612d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990733"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a><span data-ttu-id="67a1a-102">Error al obtener extensiones de enlace de machine.config.</span><span class="sxs-lookup"><span data-stu-id="67a1a-102">Error getting binding extensions from machine.config</span></span>
## <a name="details"></a><span data-ttu-id="67a1a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="67a1a-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="67a1a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67a1a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="67a1a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67a1a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="67a1a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67a1a-106">Event ID</span></span>     |                                         <span data-ttu-id="67a1a-107">0</span><span class="sxs-lookup"><span data-stu-id="67a1a-107">0</span></span>                                          |
|  <span data-ttu-id="67a1a-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67a1a-108">Event Source</span></span>   |                                         <span data-ttu-id="67a1a-109">0</span><span class="sxs-lookup"><span data-stu-id="67a1a-109">0</span></span>                                          |
|    <span data-ttu-id="67a1a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="67a1a-110">Component</span></span>    |                                         <span data-ttu-id="67a1a-111">0</span><span class="sxs-lookup"><span data-stu-id="67a1a-111">0</span></span>                                          |
|  <span data-ttu-id="67a1a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67a1a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="67a1a-113">0</span><span class="sxs-lookup"><span data-stu-id="67a1a-113">0</span></span>                                          |
|  <span data-ttu-id="67a1a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67a1a-114">Message Text</span></span>   |                <span data-ttu-id="67a1a-115">Error al obtener extensiones de enlace de machine.config.</span><span class="sxs-lookup"><span data-stu-id="67a1a-115">Error getting binding extensions from machine.config</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="67a1a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="67a1a-116">Explanation</span></span>  
 <span data-ttu-id="67a1a-117">Este error se produce cuando la configuración de enlace de una ubicación de recepción o un puerto de envío tiene una extensión de enlace definida por el usuario, pero que no está definida en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="67a1a-117">This error occurs when a  receive location or send port binding configuration has a user defined binding extension, but it is not defined in machine.config file.</span></span> <span data-ttu-id="67a1a-118">Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="67a1a-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67a1a-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67a1a-119">User Action</span></span>  
 <span data-ttu-id="67a1a-120">Defina la extensión de enlace usada en la ubicación de recepción o el puerto de envío en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="67a1a-120">Define the binding extension used in the receive location or send port in machine.config file.</span></span> <span data-ttu-id="67a1a-121">Además, para que un elemento de enlace o comportamiento personalizado funcione con el adaptador de WCF-Custom, complete estos pasos:</span><span class="sxs-lookup"><span data-stu-id="67a1a-121">Also, to get a custom behavior or binding element to work with WCF-Custom adapter, complete these steps:</span></span>  
  
1.  <span data-ttu-id="67a1a-122">Almacene el ensamblado en la memoria caché global de ensamblados (GAC)</span><span class="sxs-lookup"><span data-stu-id="67a1a-122">GAC the assembly</span></span>  
  
2.  <span data-ttu-id="67a1a-123">Modifique el archivo machine.config (se encuentra en **%FrameworkDir%\v4.0.30319\CONFIG**).</span><span class="sxs-lookup"><span data-stu-id="67a1a-123">Modify your machine.config file (found in **%FrameworkDir%\v4.0.30319\CONFIG**).</span></span>  
  
    1.  <span data-ttu-id="67a1a-124">Cargar el DLL en el Editor de configuración de servicio de comportamiento (**svcConfigEditor.exe**).</span><span class="sxs-lookup"><span data-stu-id="67a1a-124">Load your behavior DLL inside the Service Configuration Editor (**svcConfigEditor.exe**).</span></span>  
  
    2.  <span data-ttu-id="67a1a-125">Guardar la configuración para un **app.config** archivo</span><span class="sxs-lookup"><span data-stu-id="67a1a-125">Save the configuration to an **app.config** file</span></span>  
  
    3.  <span data-ttu-id="67a1a-126">Copie y pegue el **system.servicemodel** sección de extensiones en una sección similar de machine.config. Si **system.servicemodel** sección no está presente en el archivo machine.config, debe crear uno.</span><span class="sxs-lookup"><span data-stu-id="67a1a-126">Copy and paste the **system.servicemodel** extensions section in a similar section in machine.config. If **system.servicemodel** section is not present in machine.config, your must create one.</span></span> <span data-ttu-id="67a1a-127">A continuación se proporciona un ejemplo de la sección de configuración de un archivo machine.config:</span><span class="sxs-lookup"><span data-stu-id="67a1a-127">The following is an example from the configuration section of a machine.config file:</span></span>  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  <span data-ttu-id="67a1a-128">El código anterior también puede agregarse a la pestaña Extensiones de WCF. Si la extensión debe estar en el lado de recepción, vea el  **\<nombre de Host\> Properties Dialog Box, extensiones de WCF** ficha (WCF-Custom o controlador de recepción del adaptador de WCF-CustomIsolated) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="67a1a-128">The above code can also be added to the WCF Extensions tab. If the extension needs to be on the receive side, see the **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom or WCF-CustomIsolated Adapter Receive Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="67a1a-129">Si la extensión debe estar en el lado de envío, consulte  **\<nombre de Host\> Properties Dialog Box, extensiones de WCF** ficha (controlador de envío de adaptador de WCF-Custom) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="67a1a-129">If the extension needs to be on the send side, see **\<Host Name\> Properties Dialog Box, WCF Extensions** tab (WCF-Custom Adapter Send Handler) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 3. <span data-ttu-id="67a1a-130">Cierre y vuelva a abrir la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="67a1a-130">Close and reopen your admin console.</span></span> <span data-ttu-id="67a1a-131">Debe poder ver el comportamiento personalizado en el adaptador de WCF-Custom y el puerto debería permanecer habilitado cuando lo habilite.</span><span class="sxs-lookup"><span data-stu-id="67a1a-131">You should be able to see your custom behavior in the WCF-Custom adapter, and the port should stay enabled when you enable it.</span></span>