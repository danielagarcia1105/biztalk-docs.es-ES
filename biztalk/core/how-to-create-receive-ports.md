---
title: "Cómo crear puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, receive
- receive ports
- creating receive ports
ms.assetid: d390320e-12f1-4ead-b608-60bc1e273477
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ca5727422fd7519443cc290d35d0c2e24d499f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports"></a><span data-ttu-id="fd0d7-102">Cómo crear puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="fd0d7-102">How to Create Receive Ports</span></span>
<span data-ttu-id="fd0d7-103">Siga estos pasos para crear un puerto de recepción mediante Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-103">Follow these steps to create a receive port using Visual Studio.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="fd0d7-104">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="fd0d7-104">To create a receive port</span></span>  
  
1.  <span data-ttu-id="fd0d7-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="fd0d7-106">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-106">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="fd0d7-107">En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd0d7-107">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="fd0d7-108">En el **nombre** , escriba `ReceiveFromTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-108">In the **Name** field, type `ReceiveFromTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="fd0d7-109">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-109">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="fd0d7-110">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-110">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="fd0d7-111">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd0d7-111">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="fd0d7-112">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-112">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="fd0d7-113">En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-113">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="fd0d7-114">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-114">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="fd0d7-115">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-115">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="fd0d7-116">En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-116">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="fd0d7-117">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-117">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="fd0d7-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="fd0d7-119">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-119">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="fd0d7-120">En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-120">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="fd0d7-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd0d7-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0d7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd0d7-122">See Also</span></span>  
 [<span data-ttu-id="fd0d7-123">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="fd0d7-123">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)