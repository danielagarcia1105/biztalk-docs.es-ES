---
title: Problemas conocidos con el adaptador de MQSeries | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be120ec58ebf6ecba62b333655373f3e02f8e487
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990244"
---
# <a name="known-issues-with-the-mqseries-adapter"></a><span data-ttu-id="f85b2-102">Problemas conocidos del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f85b2-102">Known Issues with the MQSeries Adapter</span></span>
<span data-ttu-id="f85b2-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="f85b2-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="know-issues"></a><span data-ttu-id="f85b2-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="f85b2-104">Know Issues</span></span>  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a><span data-ttu-id="f85b2-105">Los errores de acceso denegado se producen al intentar enviar o recibir mensajes</span><span class="sxs-lookup"><span data-stu-id="f85b2-105">Access Denied errors occur when attempting to send or receive messages</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="f85b2-106">Problema</span><span class="sxs-lookup"><span data-stu-id="f85b2-106">Problem</span></span>  
 <span data-ttu-id="f85b2-107">Cuando se utiliza el adaptador de MQSeries para mandar mensajes a o recibir mensajes de un servidor MQSeries, los errores similares al siguiente se registran en el registro de la aplicación del Visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="f85b2-107">When you use the MQSeries adapter to send messages to or receive messages from an MQSeries server, error messages that are similar to the following are logged in the Application log in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  <span data-ttu-id="f85b2-108">En este mensaje de error *servername* es el nombre del servidor y *queuename* es el nombre de la cola.</span><span class="sxs-lookup"><span data-stu-id="f85b2-108">In this error message, *servername* is the name of the server and *queuename* is the name of the queue.</span></span>  
  
 <span data-ttu-id="f85b2-109">Asimismo, al intentar crear la ubicación de recepción o el puerto de envío que está configurado para utilizar el adaptador de BizTalk para MQSeries, puede que visualice el siguiente mensaje de advertencia en el Visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="f85b2-109">Additionally, when you try to create the receive location or the send port that is configured to use the BizTalk Adapter for MQSeries, you may receive the following warning message in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a><span data-ttu-id="f85b2-110">Causa</span><span class="sxs-lookup"><span data-stu-id="f85b2-110">Cause</span></span>  
 <span data-ttu-id="f85b2-111">Este problema se puede producir cuando se cumplen una o más de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f85b2-111">This issue may occur if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="f85b2-112">La cuenta de host para el adaptador de MQSeries no tiene los permisos requeridos para la aplicación MQSAgent COM+ en el servidor de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f85b2-112">The host account for the MQSeries adapter does not have the required permissions for the MQSAgent COM+ application on the MQSeries server.</span></span>  
  
- <span data-ttu-id="f85b2-113">En un servidor basado en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], la cuenta de host para el adaptador de MQSeries no es un miembro del grupo Usuarios de COM distribuido en el servidor de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f85b2-113">On a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, the host account for the MQSeries adapter is not a member of the Distributed COM Users group on the MQSeries server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="f85b2-114">Solución</span><span class="sxs-lookup"><span data-stu-id="f85b2-114">Resolution</span></span>  
 <span data-ttu-id="f85b2-115">Para solucionar este problema, utilice los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f85b2-115">To resolve this issue, use the following methods.</span></span> <span data-ttu-id="f85b2-116">Si un método no soluciona este problema, pruebe con el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="f85b2-116">If a method does not resolve the issue, try the next method.</span></span>  
  
 <span data-ttu-id="f85b2-117">**Método 1: Habilitar el acceso de red COM + en Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-equipo basado en**</span><span class="sxs-lookup"><span data-stu-id="f85b2-117">**Method 1: Enable network COM+ access on the Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer**</span></span>  
  
 <span data-ttu-id="f85b2-118">Habilite el acceso de red COM + en una Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-equipo basado en siguiendo los pasos documentados en [cómo habilitar el acceso de red COM + en Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span><span class="sxs-lookup"><span data-stu-id="f85b2-118">Enable network COM+ access on a Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer by following the steps documented in [How to enable network COM+ access in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span></span>  
  
 <span data-ttu-id="f85b2-119">**Método 2: Configurar MSDTC**</span><span class="sxs-lookup"><span data-stu-id="f85b2-119">**Method 2: Configure MSDTC settings**</span></span>  
  
 <span data-ttu-id="f85b2-120">Siga los pasos descritos en la **establecer las opciones de configuración de seguridad de MSDTC en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]**  sección de [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md) para configurar MSDTC.</span><span class="sxs-lookup"><span data-stu-id="f85b2-120">Follow the steps in the **Set the appropriate MSDTC Security Configuration options on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** section of [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to configure MSDTC settings.</span></span>  
  
 <span data-ttu-id="f85b2-121">**Método 3: Compruebe que la cuenta de host se agrega a la función en la aplicación MQSAgent COM +**</span><span class="sxs-lookup"><span data-stu-id="f85b2-121">**Method 3: Verify that the host account is added to the role in the MQSAgent COM+ application**</span></span>  
  
 <span data-ttu-id="f85b2-122">Compruebe que la cuenta de host para el adaptador de MQSeries se ha agregado a la función que se creó en la aplicación MQSAgent COM+ del servidor MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f85b2-122">Verify that the host account for the MQSeries adapter is added to the role that was created in the MQSAgent COM+ application on the MQSeries server.</span></span> <span data-ttu-id="f85b2-123">Esto lo puede comprobar en la interfaz de administración Servicios de componente.</span><span class="sxs-lookup"><span data-stu-id="f85b2-123">You can verify this in the Component Services management console interface.</span></span>  
  
 <span data-ttu-id="f85b2-124">**Método 4: Comprobar que la cuenta de host del adaptador de MQSeries es miembro del grupo usuarios COM distribuidos**</span><span class="sxs-lookup"><span data-stu-id="f85b2-124">**Method 4: Verify that the host account for the MQSeries adapter is a member of the Distributed COM Users group**</span></span>  
  
 <span data-ttu-id="f85b2-125">En un servidor basado en Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], examine los miembros del grupo de la cuenta de host para el adaptador de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f85b2-125">On a Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, examine the group memberships of the host account for the MQSeries adapter.</span></span> <span data-ttu-id="f85b2-126">Asegúrese de que la cuenta es miembro de la **usuarios COM distribuidos** grupo en el servidor MQSeries server donde está instalada la aplicación MQSAgent COM +.</span><span class="sxs-lookup"><span data-stu-id="f85b2-126">Make sure that the account is a member of the **Distributed COM Users** group on the MQSeries server where the MQSAgent COM+ application is installed.</span></span>  
  
 <span data-ttu-id="f85b2-127">Para obtener más información acerca de las mejoras de seguridad DCOM en Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], consulte [mejoras de seguridad DCOM](http://go.microsoft.com/fwlink/?LinkId=67077).</span><span class="sxs-lookup"><span data-stu-id="f85b2-127">For more information about DCOM security enhancements in Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], see [DCOM Security Enhancements](http://go.microsoft.com/fwlink/?LinkId=67077).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85b2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f85b2-128">See Also</span></span>  
 [<span data-ttu-id="f85b2-129">Solucionar problemas del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f85b2-129">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)