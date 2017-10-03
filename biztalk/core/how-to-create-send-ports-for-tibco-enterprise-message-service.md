---
title: "Cómo crear puertos de envío para TIBCO Enterprise Message Service | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 6e569244-494e-4db4-8030-eda3b390d073
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfadeb3306687bfcbea27c0df41973b12b003563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="c0529-102">Creación de puertos de envío para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="c0529-102">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="c0529-103">Siga estos pasos para crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c0529-103">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="c0529-104">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c0529-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="c0529-105">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c0529-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="c0529-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0529-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="c0529-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="c0529-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="c0529-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0529-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c0529-109">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="c0529-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="c0529-110">Desde el **tipo** lista desplegable, seleccione **TIBCO EMS**.</span><span class="sxs-lookup"><span data-stu-id="c0529-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="c0529-111">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="c0529-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="c0529-112">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="c0529-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="c0529-113">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="c0529-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="c0529-114">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c0529-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="c0529-115">En el **propiedades de transporte de TIBCO EMS** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0529-115">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c0529-116">Escriba **el control de mensajes**, **definición de conexión de servidor**, **compatibilidad con transacciones**, **nombre de usuario**y el  **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="c0529-116">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="c0529-117">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c0529-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="c0529-118">En la lista, seleccione la aplicación afiliada que ha creado para representar el sistema TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="c0529-118">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="c0529-119">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c0529-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="c0529-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0529-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c0529-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c0529-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0529-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0529-122">See Also</span></span>  
 <span data-ttu-id="c0529-123">[Establecer propiedades de transporte TIBCO Enterprise Message Service para el puerto de envío](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="c0529-123">[Setting TIBCO Enterprise Message Service Transport Properties for the Send Port](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span></span>  
 [<span data-ttu-id="c0529-124">Crear controladores de envío TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="c0529-124">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)