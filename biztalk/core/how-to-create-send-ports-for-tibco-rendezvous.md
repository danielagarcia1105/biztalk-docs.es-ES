---
title: "Cómo crear puertos de envío para TIBCO Rendezvous | Documentos de Microsoft"
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
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="4c7a6-102">Creación de puertos de envío para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="4c7a6-102">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="4c7a6-103">Siga estos pasos para crear un puerto de envío mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c7a6-103">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="4c7a6-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="4c7a6-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="4c7a6-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="4c7a6-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="4c7a6-107">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c7a6-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4c7a6-108">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-108">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="4c7a6-109">Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-109">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="4c7a6-110">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="4c7a6-111">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="4c7a6-112">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="4c7a6-113">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="4c7a6-114">En el **propiedades de transporte de TIBCO Rendezvous** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c7a6-114">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4c7a6-115">Especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-115">Enter the properties.</span></span>  
  
         <span data-ttu-id="4c7a6-116">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="4c7a6-117">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-117">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="4c7a6-118">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="4c7a6-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="4c7a6-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c7a6-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7a6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c7a6-121">See Also</span></span>  
 [<span data-ttu-id="4c7a6-122">Crear controladores de envío TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="4c7a6-122">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)