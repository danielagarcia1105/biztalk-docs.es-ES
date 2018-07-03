---
title: Cómo configurar asignaciones de entrada para un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], inbound maps
- configuring, send ports
- send ports, inbound maps
- configuring, inbound maps
- managing [send ports], configuring
- send ports, configuring
ms.assetid: 213c66ba-928f-4c00-9a87-f45eaa9f7dca
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5afe1edd63f10f39619948fb69d657bbaf85b81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996109"
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="4f5f0-102">Cómo configurar asignaciones de entrada para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="4f5f0-102">How to Configure Inbound Maps for a Send Port</span></span>
<span data-ttu-id="4f5f0-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de entrada para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a send port.</span></span> <span data-ttu-id="4f5f0-104">Las asignaciones de entrada se utilizan únicamente con puertos de envío de petición-respuesta estáticos o dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-104">Inbound maps are used only with dynamic or static solicit-response send ports.</span></span> <span data-ttu-id="4f5f0-105">Se utiliza una asignación para aplicar una transformación XSL a un mensaje de respuesta recibido por el puerto, sin tener que procesar el mensaje a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-105">You use a map to apply an XSL transformation to a response message received by the port without processing the message through an orchestration.</span></span> <span data-ttu-id="4f5f0-106">Es posible agregar una asignación de entrada, quitar una asignación o cambiar una ya existente por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="4f5f0-107">Puede agregar más de una asignación a un puerto de envío, aunque cada una de las asignaciones debe tener un único esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-107">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="4f5f0-108">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="4f5f0-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f5f0-109">El desarrollador de aplicaciones puede configurar asignaciones durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-109">The application developer can configure maps during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4f5f0-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f5f0-110">Prerequisites</span></span>  
 <span data-ttu-id="4f5f0-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4f5f0-112">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="4f5f0-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a><span data-ttu-id="4f5f0-113">Para configurar asignaciones de entrada para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="4f5f0-113">To configure inbound maps for a send port</span></span>  
  
1. <span data-ttu-id="4f5f0-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4f5f0-115">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar una asignación de entrada para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound map for a send port.</span></span>  
  
3. <span data-ttu-id="4f5f0-116">Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de entrada**.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-116">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="4f5f0-117">Configure las asignaciones de entrada tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="4f5f0-118">Efectúe las repeticiones necesarias para agregar o quitar varias asignaciones.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-118">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="4f5f0-119">Use</span><span class="sxs-lookup"><span data-stu-id="4f5f0-119">Use this</span></span>|<span data-ttu-id="4f5f0-120">Para</span><span class="sxs-lookup"><span data-stu-id="4f5f0-120">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="4f5f0-121">**Quitar**</span><span class="sxs-lookup"><span data-stu-id="4f5f0-121">**Remove**</span></span>|<span data-ttu-id="4f5f0-122">Quitar la asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-122">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="4f5f0-123">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="4f5f0-123">**Source Document**</span></span>|<span data-ttu-id="4f5f0-124">En la lista desplegable, seleccionar el documento origen para la asignación de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-124">From the drop-down list, select the source document for the inbound map.</span></span>|  
   |<span data-ttu-id="4f5f0-125">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="4f5f0-125">**Map**</span></span>|<span data-ttu-id="4f5f0-126">En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-126">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="4f5f0-127">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="4f5f0-127">**Target Document**</span></span>|<span data-ttu-id="4f5f0-128">En la lista desplegable, seleccionar el documento destino para la asignación de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f5f0-128">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f5f0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f5f0-129">See Also</span></span>  
 <span data-ttu-id="4f5f0-130">[Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="4f5f0-130">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="4f5f0-131">Administración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="4f5f0-131">Managing Maps</span></span>](../core/managing-maps.md)