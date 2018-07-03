---
title: Agregar el adaptador SAP a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a8913e982a94a2b850bae1aab668f9672e86fe8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986629"
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="b475a-102">Agregar el adaptador SAP a la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b475a-102">Add the SAP Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="b475a-103">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF SAP en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b475a-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SAP port.</span></span> <span data-ttu-id="b475a-104">Si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b475a-104">If you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="b475a-105">Sin embargo, si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de SAP de WCF, primero debe agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b475a-105">However, if you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-SAP port, you must first add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="b475a-106">Este tema proporciona instrucciones sobre cómo agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b475a-106">This topic provides instructions on how to add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b475a-107">No es necesario realizar estas tareas si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b475a-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="add-the-sap-adapter"></a><span data-ttu-id="b475a-108">Agregar el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="b475a-108">Add the SAP Adapter</span></span>  
  
1. <span data-ttu-id="b475a-109">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b475a-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="b475a-110">En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="b475a-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="b475a-111">Haga clic en **adaptadores**, apunte a **New**y haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="b475a-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="b475a-112">![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="b475a-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="b475a-113">En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y desde el **adaptador** lista, seleccione **SAP de WCF**.</span><span class="sxs-lookup"><span data-stu-id="b475a-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-SAP**.</span></span>  
  
    <span data-ttu-id="b475a-114">![Agregar adaptador SAP a BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="b475a-114">![Add SAP Adapter to BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  
  
5. <span data-ttu-id="b475a-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b475a-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b475a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b475a-116">See Also</span></span>  
[<span data-ttu-id="b475a-117">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="b475a-117">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)