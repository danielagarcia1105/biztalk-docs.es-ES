---
title: Cómo configurar asignaciones de salida para un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1dc02d2936cad6fd24ee944e3c27c64831bc65f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023186"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="39f75-102">Cómo configurar asignaciones de salida para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="39f75-102">How to Configure Outbound Maps for a Send Port</span></span>
<span data-ttu-id="39f75-103">En este tema se describe cómo configurar asignaciones de salida para un puerto de envío mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f75-103">This topic describes how to configure outbound maps for a send port by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="39f75-104">Se utiliza una asignación para aplicar una transformación XSL a un mensaje enviado por el puerto de envío, sin tener que procesar el mensaje a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="39f75-104">You use a map to apply an XSL transformation to a message sent by the send port without processing the message through an orchestration.</span></span> <span data-ttu-id="39f75-105">Es posible agregar una asignación de salida, quitar una asignación o cambiar una ya existente por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="39f75-105">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="39f75-106">Puede agregar más de una asignación a un puerto de envío, aunque cada una de las asignaciones debe tener un único esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="39f75-106">You can add more than one map to a send port, but each map must have a unique source schema.</span></span> <span data-ttu-id="39f75-107">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="39f75-107">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39f75-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="39f75-108">Prerequisites</span></span>  
 <span data-ttu-id="39f75-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="39f75-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="39f75-110">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="39f75-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a><span data-ttu-id="39f75-111">Para configurar asignaciones de salida para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="39f75-111">To configure outbound maps for a send port</span></span>  
  
1. <span data-ttu-id="39f75-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="39f75-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="39f75-113">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar las asignaciones de salida para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="39f75-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure the outbound maps for a send port.</span></span>  
  
3. <span data-ttu-id="39f75-114">Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="39f75-114">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="39f75-115">Configurar asignaciones de salida como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39f75-115">Configure outbound maps as described in the following table, and then click **OK**.</span></span> <span data-ttu-id="39f75-116">Efectúe las repeticiones necesarias para agregar o quitar varias asignaciones.</span><span class="sxs-lookup"><span data-stu-id="39f75-116">Repeat as needed to add or remove multiple maps.</span></span>  
  
   |<span data-ttu-id="39f75-117">Use</span><span class="sxs-lookup"><span data-stu-id="39f75-117">Use this</span></span>|<span data-ttu-id="39f75-118">Para</span><span class="sxs-lookup"><span data-stu-id="39f75-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="39f75-119">**Quitar**</span><span class="sxs-lookup"><span data-stu-id="39f75-119">**Remove**</span></span>|<span data-ttu-id="39f75-120">Quitar la asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f75-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="39f75-121">**Asignaciones de salida - documento de origen**</span><span class="sxs-lookup"><span data-stu-id="39f75-121">**Outbound maps - Source Document**</span></span>|<span data-ttu-id="39f75-122">En la lista desplegable, seleccionar el documento origen para la asignación de salida.</span><span class="sxs-lookup"><span data-stu-id="39f75-122">From the drop-down list, select the source document for the outbound map.</span></span>|  
   |<span data-ttu-id="39f75-123">**Asignaciones de salida - asignación**</span><span class="sxs-lookup"><span data-stu-id="39f75-123">**Outbound maps - Map**</span></span>|<span data-ttu-id="39f75-124">En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="39f75-124">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
   |<span data-ttu-id="39f75-125">**Asignaciones de salida - documento destino**</span><span class="sxs-lookup"><span data-stu-id="39f75-125">**Outbound maps - Target Document**</span></span>|<span data-ttu-id="39f75-126">En la lista desplegable, seleccionar el documento destino para la asignación de salida.</span><span class="sxs-lookup"><span data-stu-id="39f75-126">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39f75-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="39f75-127">See Also</span></span>  
 <span data-ttu-id="39f75-128">[Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="39f75-128">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 [<span data-ttu-id="39f75-129">Administración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="39f75-129">Managing Maps</span></span>](../core/managing-maps.md)