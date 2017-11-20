---
title: "Agregar el adaptador SAP a la consola de administración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19870e69dc502f9635f34b578c2853aaf8897e00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="ee2e9-102">Agregar el adaptador SAP a la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ee2e9-102">Add the SAP Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="ee2e9-103">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF SAP en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SAP port.</span></span> <span data-ttu-id="ee2e9-104">Si desea utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-104">If you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="ee2e9-105">Sin embargo, si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de SAP de WCF, primero debe agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-105">However, if you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-SAP port, you must first add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="ee2e9-106">Este tema proporciona instrucciones sobre cómo agregar el adaptador SAP de WCF para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-106">This topic provides instructions on how to add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee2e9-107">No es necesario realizar estas tareas si desea configurar un puerto personalizado de WCF para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee2e9-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="add-the-sap-adapter"></a><span data-ttu-id="ee2e9-108">Agregar el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="ee2e9-108">Add the SAP Adapter</span></span>  
  
1.  <span data-ttu-id="ee2e9-109">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ee2e9-110">En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="ee2e9-111">Haga clic en **adaptadores**, seleccione **New**y haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
     <span data-ttu-id="ee2e9-112">![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="ee2e9-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="ee2e9-113">En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y de la **adaptador** lista, seleccione **WCF SAP**.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-SAP**.</span></span>  
  
     <span data-ttu-id="ee2e9-114">![Agregar adaptador SAP a BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="ee2e9-114">![Add SAP Adapter to BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  
  
5.  <span data-ttu-id="ee2e9-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2e9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee2e9-116">See Also</span></span>  
[<span data-ttu-id="ee2e9-117">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="ee2e9-117">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)