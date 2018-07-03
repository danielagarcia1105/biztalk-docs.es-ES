---
title: Cómo configurar asignaciones de salida para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c74fcc259b833a64a480bbe88f4cc0273d2a83c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023610"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="bf12a-102">Cómo configurar asignaciones de salida para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="bf12a-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="bf12a-103">En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de salida para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="bf12a-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="bf12a-104">Las asignaciones de salida pueden utilizarse con puertos de recepción de solicitud-respuesta para transformar mensajes de salida de un esquema a otro (por ejemplo, para transformar mensajes que utiliza la empresa en un esquema que utiliza un socio comercial).</span><span class="sxs-lookup"><span data-stu-id="bf12a-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="bf12a-105">Se utiliza una asignación para aplicar una transformación XSL a un mensaje de respuesta enviado por el puerto de recepción, sin tener que procesar el mensaje a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="bf12a-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="bf12a-106">Es posible agregar una asignación de salida, quitar una asignación o cambiar una ya existente por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="bf12a-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="bf12a-107">Puede agregar más de una asignación a un puerto de recepción, aunque cada asignación debe tener un único esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="bf12a-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="bf12a-108">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="bf12a-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf12a-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bf12a-109">Prerequisites</span></span>  
 <span data-ttu-id="bf12a-110">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="bf12a-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="bf12a-111">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="bf12a-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="bf12a-112">Para configurar asignaciones de salida para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="bf12a-112">To configure outbound maps for a receive port</span></span>  
  
1. <span data-ttu-id="bf12a-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="bf12a-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bf12a-114">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar asignaciones de salida para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="bf12a-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3. <span data-ttu-id="bf12a-115">Expanda **puertos de recepción**, haga clic en el puerto de recepción, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="bf12a-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4. <span data-ttu-id="bf12a-116">Configure las asignaciones de salida tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf12a-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="bf12a-117">Use</span><span class="sxs-lookup"><span data-stu-id="bf12a-117">Use this</span></span>|<span data-ttu-id="bf12a-118">Para</span><span class="sxs-lookup"><span data-stu-id="bf12a-118">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="bf12a-119">**Quitar**</span><span class="sxs-lookup"><span data-stu-id="bf12a-119">**Remove**</span></span>|<span data-ttu-id="bf12a-120">Quitar la asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf12a-120">Click to remove the selected map.</span></span>|  
   |<span data-ttu-id="bf12a-121">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="bf12a-121">**Source Document**</span></span>|<span data-ttu-id="bf12a-122">Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bf12a-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
   |<span data-ttu-id="bf12a-123">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="bf12a-123">**Map**</span></span>|<span data-ttu-id="bf12a-124">Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bf12a-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
   |<span data-ttu-id="bf12a-125">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="bf12a-125">**Target Document**</span></span>|<span data-ttu-id="bf12a-126">Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bf12a-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf12a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf12a-127">See Also</span></span>  
 <span data-ttu-id="bf12a-128">[Administrar puertos de recepción](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="bf12a-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="bf12a-129">Administración de asignaciones</span><span class="sxs-lookup"><span data-stu-id="bf12a-129">Managing Maps</span></span>](../core/managing-maps.md)