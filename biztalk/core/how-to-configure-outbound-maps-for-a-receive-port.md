---
title: "Cómo configurar asignaciones de salida para un puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="0a53c-102">Cómo configurar asignaciones de salida para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="0a53c-102">How to Configure Outbound Maps for a Receive Port</span></span>
<span data-ttu-id="0a53c-103">En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de salida para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a53c-103">This topic describes how to use the BizTalk Server Administration console to configure outbound maps for a receive port.</span></span> <span data-ttu-id="0a53c-104">Las asignaciones de salida pueden utilizarse con puertos de recepción de solicitud-respuesta para transformar mensajes de salida de un esquema a otro (por ejemplo, para transformar mensajes que utiliza la empresa en un esquema que utiliza un socio comercial).</span><span class="sxs-lookup"><span data-stu-id="0a53c-104">You can use outbound maps with request-response receive ports to transform outbound messages from one schema to another; for example to transform messages that your company uses into a schema that a partner uses.</span></span>  
  
 <span data-ttu-id="0a53c-105">Se utiliza una asignación para aplicar una transformación XSL a un mensaje de respuesta enviado por el puerto de recepción, sin tener que procesar el mensaje a través de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="0a53c-105">You use a map to apply an XSL transformation to a response message sent by the receive port without processing the message through an orchestration.</span></span> <span data-ttu-id="0a53c-106">Es posible agregar una asignación de salida, quitar una asignación o cambiar una ya existente por otra distinta.</span><span class="sxs-lookup"><span data-stu-id="0a53c-106">You can add an outbound map, remove a map, or change an existing map to a different one.</span></span> <span data-ttu-id="0a53c-107">Puede agregar más de una asignación a un puerto de recepción, aunque cada asignación debe tener un único esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="0a53c-107">You can add more than one map to a receive port, but each map must have a unique source schema.</span></span> <span data-ttu-id="0a53c-108">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="0a53c-108">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a53c-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0a53c-109">Prerequisites</span></span>  
 <span data-ttu-id="0a53c-110">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0a53c-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0a53c-111">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0a53c-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a><span data-ttu-id="0a53c-112">Para configurar asignaciones de salida para un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="0a53c-112">To configure outbound maps for a receive port</span></span>  
  
1.  <span data-ttu-id="0a53c-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0a53c-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0a53c-114">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar asignaciones de salida para un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="0a53c-114">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure outbound maps for a receive port.</span></span>  
  
3.  <span data-ttu-id="0a53c-115">Expanda **puertos de recepción**, haga clic en el puerto de recepción, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de salida**.</span><span class="sxs-lookup"><span data-stu-id="0a53c-115">Expand **Receive Ports**, right-click the receive port, click **Properties**, and then click **Outbound Maps**.</span></span>  
  
4.  <span data-ttu-id="0a53c-116">Configurar las asignaciones de salida tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a53c-116">Configure the outbound maps as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="0a53c-117">Use</span><span class="sxs-lookup"><span data-stu-id="0a53c-117">Use this</span></span>|<span data-ttu-id="0a53c-118">Para</span><span class="sxs-lookup"><span data-stu-id="0a53c-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0a53c-119">**Quitar**</span><span class="sxs-lookup"><span data-stu-id="0a53c-119">**Remove**</span></span>|<span data-ttu-id="0a53c-120">Quitar la asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0a53c-120">Click to remove the selected map.</span></span>|  
    |<span data-ttu-id="0a53c-121">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="0a53c-121">**Source Document**</span></span>|<span data-ttu-id="0a53c-122">Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0a53c-122">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="0a53c-123">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="0a53c-123">**Map**</span></span>|<span data-ttu-id="0a53c-124">Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0a53c-124">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="0a53c-125">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="0a53c-125">**Target Document**</span></span>|<span data-ttu-id="0a53c-126">Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0a53c-126">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a53c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a53c-127">See Also</span></span>  
 <span data-ttu-id="0a53c-128">[Administrar puertos de recepción](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="0a53c-128">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 [<span data-ttu-id="0a53c-129">Administración de mapas</span><span class="sxs-lookup"><span data-stu-id="0a53c-129">Managing Maps</span></span>](../core/managing-maps.md)