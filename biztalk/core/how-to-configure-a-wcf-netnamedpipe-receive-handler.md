---
title: Cómo configurar controlador de recepción de WCF-NetNamedPipe | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9339cca7f8065d3412686cfcc84d84028ef39faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248612"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="0d409-102">Cómo configurar un controlador de recepción WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0d409-102">How to Configure a WCF-NetNamedPipe Receive Handler</span></span>
<span data-ttu-id="0d409-103">Utilice este procedimiento para configurar un controlador de recepción WCF-NetNamedPipe.</span><span class="sxs-lookup"><span data-stu-id="0d409-103">Use the following procedure to configure a WCF-NetNamedPipe receive handler.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="0d409-104">Para cambiar las variables globales del controlador de recepción WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0d409-104">To change global variables for a WCF-NetNamedPipe receive handler</span></span>  
  
1.  <span data-ttu-id="0d409-105">En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="0d409-105">In the BizTalk Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="0d409-106">En la lista de adaptadores expandida, haga clic en **WCF-NetNamedPipe**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0d409-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0d409-107">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="0d409-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="0d409-108">En el **General** , haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0d409-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="0d409-109">En el **controlador de recepción** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d409-109">On the **Receive handler** tab, do the following:</span></span>  
  
    |<span data-ttu-id="0d409-110">Use</span><span class="sxs-lookup"><span data-stu-id="0d409-110">Use this</span></span>|<span data-ttu-id="0d409-111">Para</span><span class="sxs-lookup"><span data-stu-id="0d409-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0d409-112">**Número máximo de conexiones**</span><span class="sxs-lookup"><span data-stu-id="0d409-112">**Maximum connections**</span></span>|<span data-ttu-id="0d409-113">Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d409-113">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="0d409-114">Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.</span><span class="sxs-lookup"><span data-stu-id="0d409-114">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="0d409-115">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="0d409-115">The default is 10.</span></span>|  
  
5.  <span data-ttu-id="0d409-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d409-116">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d409-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d409-117">See Also</span></span>  
 <span data-ttu-id="0d409-118">[Publicar servicios WCF](../core/publishing-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="0d409-118">[Publishing WCF Services](../core/publishing-wcf-services.md) </span></span>  
 [<span data-ttu-id="0d409-119">Configurar el adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0d409-119">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)