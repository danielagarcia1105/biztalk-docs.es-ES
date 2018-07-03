---
title: Cómo habilitar enrutamiento para mensajes erróneos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c00e49afa528bc0008d73272dca561d461660367
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008493"
---
# <a name="how-to-enable-routing-for-failed-messages"></a><span data-ttu-id="7394b-102">Cómo habilitar el enrutamiento para mensajes con errores</span><span class="sxs-lookup"><span data-stu-id="7394b-102">How to Enable Routing for Failed Messages</span></span>
<span data-ttu-id="7394b-103">El enrutamiento de mensajes con errores es una propiedad de los puertos de envío y recepción y se habilita mediante la opción “Habilitar enrutamiento para mensajes con errores” de la página de propiedades del puerto.</span><span class="sxs-lookup"><span data-stu-id="7394b-103">Failed message routing is a property of send and receive ports, and is enabled by indicating "Enable routing for failed messages" on the port's property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7394b-104">La configuración en un puerto de recepción se aplica a todas las ubicaciones de recepción asociadas con dicho puerto.</span><span class="sxs-lookup"><span data-stu-id="7394b-104">The configuration on a receive port applies to all receive locations associated with that receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7394b-105">La configuración en un puerto de envío se aplica a los transportes tanto principales como de reserva.</span><span class="sxs-lookup"><span data-stu-id="7394b-105">The configuration on a send port applies to both the primary and backup transports.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a><span data-ttu-id="7394b-106">Para configurar el enrutamiento de mensajes con errores en un puerto de recepción (se aplica a los puertos de recepción tanto unidireccionales como de solicitud-respuesta)</span><span class="sxs-lookup"><span data-stu-id="7394b-106">To configure failed message routing for a receive port (this applies to both one-way and request-response receive ports)</span></span>  
  
1. <span data-ttu-id="7394b-107">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7394b-107">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="7394b-108">Expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación a la que pertenece el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7394b-108">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="7394b-109">Haga clic en el **puertos de recepción** carpeta.</span><span class="sxs-lookup"><span data-stu-id="7394b-109">Click the **Receive Ports** folder.</span></span>  
  
4. <span data-ttu-id="7394b-110">En el panel de la derecha, haga doble clic en el nombre del puerto de recepción que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="7394b-110">In the right pane, double-click the name of the receive port you want to configure.</span></span>  
  
5. <span data-ttu-id="7394b-111">En la página de propiedades del puerto de recepción, en el panel izquierdo, seleccione el **General** categoría.</span><span class="sxs-lookup"><span data-stu-id="7394b-111">On the receive port's property page, in the left pane, select the **General** category.</span></span>  
  
6. <span data-ttu-id="7394b-112">En el panel derecho, seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7394b-112">In the right pane, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a><span data-ttu-id="7394b-113">Para configurar el enrutamiento de mensajes con errores en un puerto de envío (se aplica solo a los puertos de envío unidireccionales estáticos y de petición-respuesta estáticos)</span><span class="sxs-lookup"><span data-stu-id="7394b-113">To configure failed message routing for a send port (this applies only to static one-way and static solicit-response send ports)</span></span>  
  
1. <span data-ttu-id="7394b-114">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7394b-114">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="7394b-115">Expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación a la que pertenece el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7394b-115">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="7394b-116">Haga clic en el **puertos de envío** carpeta.</span><span class="sxs-lookup"><span data-stu-id="7394b-116">Click the **Send Ports** folder.</span></span>  
  
4. <span data-ttu-id="7394b-117">En el panel de la derecha, haga doble clic en el nombre del puerto de envío que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="7394b-117">In the right pane, double-click the name of the send port you want to configure.</span></span>  
  
5. <span data-ttu-id="7394b-118">En la página de propiedades del puerto de envío, en el panel izquierdo, seleccione el **opciones avanzadas de transporte** categoría.</span><span class="sxs-lookup"><span data-stu-id="7394b-118">On the send port's property page, in the left pane, select the **Transport Advanced Options** category.</span></span>  
  
6. <span data-ttu-id="7394b-119">En el panel derecho, en el **opciones de transporte** cuadro de grupo, seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7394b-119">In the right pane, in the **Transport Options** group box, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7394b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7394b-120">See Also</span></span>  
 [<span data-ttu-id="7394b-121">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="7394b-121">Error Handling</span></span>](../core/error-handling.md)