---
title: "Agregar el adaptador de Siebel a la consola de administración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b64d0bdc-ac83-46c9-b27d-625088a013d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb4a946c9fd987c1a97fa24a9b50d3cdf2f7d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="00fc5-102">Agregar el adaptador de Siebel a la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="00fc5-102">Add the Siebel Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="00fc5-103">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="00fc5-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="00fc5-104">Si desea utilizar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00fc5-104">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="00fc5-105">Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="00fc5-105">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="00fc5-106">Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="00fc5-106">This topic provides instructions on how to add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00fc5-107">No es necesario realizar estas tareas si desea configurar un puerto personalizado de WCF para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00fc5-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="add-the-siebel-adapter"></a><span data-ttu-id="00fc5-108">Agregar el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="00fc5-108">Add the Siebel adapter</span></span>  
  
1.  <span data-ttu-id="00fc5-109">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="00fc5-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="00fc5-110">En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="00fc5-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="00fc5-111">Haga clic en **adaptadores**, seleccione **New**y haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="00fc5-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
     <span data-ttu-id="00fc5-112">![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="00fc5-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="00fc5-113">En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y de la **adaptador** lista, seleccione **WCF-Siebel**.</span><span class="sxs-lookup"><span data-stu-id="00fc5-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-Siebel**.</span></span>  
  
     <span data-ttu-id="00fc5-114">![Agregar WCF &#45; Adaptador de Siebel a BizTalk consola](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span><span class="sxs-lookup"><span data-stu-id="00fc5-114">![Add WCF&#45;Siebel adapter to BizTalk console](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span></span>  
  
5.  <span data-ttu-id="00fc5-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00fc5-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00fc5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="00fc5-116">See Also</span></span>  
[<span data-ttu-id="00fc5-117">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="00fc5-117">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)