---
title: Cómo configurar asignaciones de entrada para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b840f4c418c835765345adc01da5c9c18812d3ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985605"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="6780f-102">Cómo configurar asignaciones de entrada para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="6780f-102">How to Configure Inbound Maps for a Receive Port</span></span>
<span data-ttu-id="6780f-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de entrada para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="6780f-103">This topic describes how to use the BizTalk Server Administration console to configure inbound maps for a receive port.</span></span> <span data-ttu-id="6780f-104">Las asignaciones de entrada pueden utilizarse para transformar mensajes de entrada de un esquema a otro (por ejemplo, para transformar mensajes recibidos de un socio comercial en un esquema utilizado en su empresa).</span><span class="sxs-lookup"><span data-stu-id="6780f-104">You use inbound maps to transform inbound messages from one schema to another; for example to transform messages received from a partner into a schema that your company uses.</span></span>  
  
 <span data-ttu-id="6780f-105">Se utiliza una asignación para aplicar una transformación XSL a un mensaje enviado por el puerto de recepción, sin tener que procesar el mensaje a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="6780f-105">You use a map to apply an XSL transformation to a message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="6780f-106">Es posible agregar una asignación de entrada, quitar una asignación o cambiar una ya existente por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="6780f-106">You can add an inbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="6780f-107">Puede agregar más de una asignación a un puerto de recepción, aunque cada asignación debe tener un único esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="6780f-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="6780f-108">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="6780f-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6780f-109">El desarrollador de aplicaciones puede configurar asignaciones para un puerto de recepción durante el proceso de desarrollo mediante el procedimiento de este.</span><span class="sxs-lookup"><span data-stu-id="6780f-109">The application developer can configure maps for a receive port during the development process by using the procedure in this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6780f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6780f-110">Prerequisites</span></span>  
 <span data-ttu-id="6780f-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6780f-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6780f-112">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="6780f-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a><span data-ttu-id="6780f-113">Para configurar asignaciones de entrada para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="6780f-113">To configure inbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="6780f-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6780f-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6780f-115">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar una asignación de entrada para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="6780f-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure an inbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="6780f-116">Haga clic en **puertos de recepción**, haga clic en el puerto de recepción, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de entrada**.</span><span class="sxs-lookup"><span data-stu-id="6780f-116">Click **Receive Ports**, right-click the receive port, click **Properties**, and then click **Inbound Maps**.</span></span>  
  
4. <span data-ttu-id="6780f-117">Configure las asignaciones de entrada tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6780f-117">Configure the inbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="6780f-118">Use</span><span class="sxs-lookup"><span data-stu-id="6780f-118">Use this</span></span>|<span data-ttu-id="6780f-119">Para</span><span class="sxs-lookup"><span data-stu-id="6780f-119">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="6780f-120">**Quitar**</span><span class="sxs-lookup"><span data-stu-id="6780f-120">**Remove**</span></span>|<span data-ttu-id="6780f-121">Quitar la asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6780f-121">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="6780f-122">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="6780f-122">**Source Document**</span></span>|<span data-ttu-id="6780f-123">Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6780f-123">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="6780f-124">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="6780f-124">**Map**</span></span>|<span data-ttu-id="6780f-125">Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6780f-125">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="6780f-126">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="6780f-126">**Target Document**</span></span>|<span data-ttu-id="6780f-127">Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6780f-127">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6780f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6780f-128">See Also</span></span>  
 <span data-ttu-id="6780f-129">[Administrar puertos de recepción](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="6780f-129">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="6780f-130">Administración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="6780f-130">Managing Maps</span></span>](../core/managing-maps.md)