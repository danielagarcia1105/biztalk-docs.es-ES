---
title: Cómo configurar un controlador de envío SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4bcbe39861c37db348e1e37752fbad6d9616033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005485"
---
# <a name="how-to-configure-a-soap-send-handler"></a><span data-ttu-id="2d75c-102">Cómo configurar un controlador de envío SOAP</span><span class="sxs-lookup"><span data-stu-id="2d75c-102">How to Configure a SOAP Send Handler</span></span>
<span data-ttu-id="2d75c-103">Para configurar el controlador de envío de SOAP, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="2d75c-103">Use the following procedure to configure the SOAP send handler.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="2d75c-104">Al usar controladores de adaptador HTTP o SOAP, se recomienda que instale las instancias de host de estos controladores en Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]equipos.</span><span class="sxs-lookup"><span data-stu-id="2d75c-104">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]computers.</span></span>  

### <a name="to-change-global-variables-for-a-soap-send-handler"></a><span data-ttu-id="2d75c-105">Para cambiar las variables globales de un controlador de envío de SOAP</span><span class="sxs-lookup"><span data-stu-id="2d75c-105">To change global variables for a SOAP send handler</span></span>  

1. <span data-ttu-id="2d75c-106">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="2d75c-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="2d75c-107">En la lista de adaptadores expandida, haga clic en **SOAP**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d75c-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="2d75c-108">En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="2d75c-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="2d75c-109">En el **Proxy** ficha, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2d75c-109">On the **Proxy** tab, do the following.</span></span>  


   |   <span data-ttu-id="2d75c-110">Use</span><span class="sxs-lookup"><span data-stu-id="2d75c-110">Use this</span></span>    |                                                                                                                  <span data-ttu-id="2d75c-111">Para</span><span class="sxs-lookup"><span data-stu-id="2d75c-111">To do this</span></span>                                                                                                                   |
   |---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="2d75c-112">**Utilizar proxy**</span><span class="sxs-lookup"><span data-stu-id="2d75c-112">**Use proxy**</span></span> |                                                                                          <span data-ttu-id="2d75c-113">Indicar si el controlador de envío de SOAP utiliza un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2d75c-113">Indicate whether the SOAP send handler uses a proxy server.</span></span>                                                                                          |
   |  <span data-ttu-id="2d75c-114">**Server**</span><span class="sxs-lookup"><span data-stu-id="2d75c-114">**Server**</span></span>   |                  <span data-ttu-id="2d75c-115">Especificar el nombre del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2d75c-115">Specify the name of the proxy server.</span></span><br /><br /> <span data-ttu-id="2d75c-116">Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d75c-116">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2d75c-117">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="2d75c-117">Type: String</span></span><br /><br /> <span data-ttu-id="2d75c-118">Longitud mínima: 0</span><span class="sxs-lookup"><span data-stu-id="2d75c-118">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2d75c-119">Longitud máxima: 256</span><span class="sxs-lookup"><span data-stu-id="2d75c-119">Maximum length: 256</span></span>                   |
   |   <span data-ttu-id="2d75c-120">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="2d75c-120">**Port**</span></span>    | <span data-ttu-id="2d75c-121">Especificar el puerto que utiliza el controlador de envío de SOAP.</span><span class="sxs-lookup"><span data-stu-id="2d75c-121">Specify the port the SOAP send handler uses.</span></span><br /><br /> <span data-ttu-id="2d75c-122">Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d75c-122">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2d75c-123">Valor predeterminado: 80</span><span class="sxs-lookup"><span data-stu-id="2d75c-123">Default Value: 80</span></span><br /><br /> <span data-ttu-id="2d75c-124">Tipo: long</span><span class="sxs-lookup"><span data-stu-id="2d75c-124">Type: Long</span></span><br /><br /> <span data-ttu-id="2d75c-125">Valor mínimo: 0</span><span class="sxs-lookup"><span data-stu-id="2d75c-125">Minimum value: 0</span></span><br /><br /> <span data-ttu-id="2d75c-126">Valor máximo: 65535</span><span class="sxs-lookup"><span data-stu-id="2d75c-126">Maximum value: 65535</span></span> |
   | <span data-ttu-id="2d75c-127">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="2d75c-127">**User name**</span></span> |             <span data-ttu-id="2d75c-128">Especificar el nombre de usuario que se utilizará para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d75c-128">Specify the user name to use for authentication.</span></span><br /><br /> <span data-ttu-id="2d75c-129">Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d75c-129">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2d75c-130">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="2d75c-130">Type: String</span></span><br /><br /> <span data-ttu-id="2d75c-131">Longitud mínima: 0</span><span class="sxs-lookup"><span data-stu-id="2d75c-131">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2d75c-132">Longitud máxima: 256</span><span class="sxs-lookup"><span data-stu-id="2d75c-132">Maximum length: 256</span></span>             |
   | <span data-ttu-id="2d75c-133">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="2d75c-133">**Password**</span></span>  |             <span data-ttu-id="2d75c-134">Especificar la contraseña que se utilizará para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2d75c-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="2d75c-135">Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d75c-135">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2d75c-136">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="2d75c-136">Type: String</span></span><br /><br /> <span data-ttu-id="2d75c-137">Longitud mínima: 0</span><span class="sxs-lookup"><span data-stu-id="2d75c-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2d75c-138">Longitud máxima: 256</span><span class="sxs-lookup"><span data-stu-id="2d75c-138">Maximum length: 256</span></span>              |


5. <span data-ttu-id="2d75c-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d75c-139">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d75c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d75c-140">See Also</span></span>  
 <span data-ttu-id="2d75c-141">[Configuración del adaptador de SOAP](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2d75c-141">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="2d75c-142">Publicación de servicios web</span><span class="sxs-lookup"><span data-stu-id="2d75c-142">Publishing Web Services</span></span>](../core/publishing-web-services.md)