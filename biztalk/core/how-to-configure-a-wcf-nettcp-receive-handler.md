---
title: Cómo configurar controlador de recepción WCF-NetTcp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8d7e68e4df5a729aae7f84932b53d319fea0114
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009949"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="7db0c-102">Cómo configurar un controlador de recepción WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="7db0c-102">How to Configure a WCF-NetTcp Receive Handler</span></span>
<span data-ttu-id="7db0c-103">Utilice este procedimiento para configurar un controlador de recepción WCF-NetTcp.</span><span class="sxs-lookup"><span data-stu-id="7db0c-103">Use the following procedure to configure a WCF-NetTcp receive handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="7db0c-104">Para cambiar las variables globales del controlador de recepción WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="7db0c-104">To change global variables for a WCF-NetTcp receive handler</span></span>  

1. <span data-ttu-id="7db0c-105">En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="7db0c-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="7db0c-106">En la lista de adaptadores expandida, haga clic en **WCF-NetTcp**, en el panel derecho, el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7db0c-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="7db0c-107">En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="7db0c-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="7db0c-108">En el **General** , haga clic **propiedades**, en el **controlador de recepción** ficha, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7db0c-108">In the **General** tab, click **Properties**, On the **Receive handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="7db0c-109">Use</span><span class="sxs-lookup"><span data-stu-id="7db0c-109">Use this</span></span>         |                                                                                                                         <span data-ttu-id="7db0c-110">Para</span><span class="sxs-lookup"><span data-stu-id="7db0c-110">To do this</span></span>                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="7db0c-111">**Número máximo de conexiones**</span><span class="sxs-lookup"><span data-stu-id="7db0c-111">**Maximum connections**</span></span> | <span data-ttu-id="7db0c-112">Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7db0c-112">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="7db0c-113">Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.</span><span class="sxs-lookup"><span data-stu-id="7db0c-113">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="7db0c-114">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="7db0c-114">The default is 10.</span></span> |


5. <span data-ttu-id="7db0c-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7db0c-115">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7db0c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7db0c-116">See Also</span></span>  
 <span data-ttu-id="7db0c-117">[Configuración del adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7db0c-117">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="7db0c-118">Publicación de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="7db0c-118">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)