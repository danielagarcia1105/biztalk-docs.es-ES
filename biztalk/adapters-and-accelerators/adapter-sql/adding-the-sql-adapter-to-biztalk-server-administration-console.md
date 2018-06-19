---
title: Agregar el adaptador de SQL a la consola de administración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3510fb31bffe4c5823593fac34d5d5f1d5849c65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222052"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="0dfe0-102">Agregar el adaptador de SQL a la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0dfe0-102">Adding the SQL Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="0dfe0-103">La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede usarse como un puerto de WCF-Custom o WCF-SQL en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SQL port.</span></span> <span data-ttu-id="0dfe0-104">Si desea utilizar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-104">If you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="0dfe0-105">Sin embargo, si desea usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de un puerto de WCF-SQL, primero debe agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-105">However, if you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-SQL port, you must first add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="0dfe0-106">Este tema muestra cómo agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-106">This topic shows you how to add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0dfe0-107">No es necesario seguir estos pasos si desea configurar un puerto personalizado de WCF para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfe0-107">You do not need to follow these steps if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="add-the-sql-adapter"></a><span data-ttu-id="0dfe0-108">Agregar el adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="0dfe0-108">Add the SQL Adapter</span></span>  
  
1.  <span data-ttu-id="0dfe0-109">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-109">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="0dfe0-110">Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-110">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3.  <span data-ttu-id="0dfe0-111">Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-111">Right-click **Adapters**, point to **New**, and select **Adapter**.</span></span>  
  
     <span data-ttu-id="0dfe0-112">![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="0dfe0-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="0dfe0-113">En el **propiedades del adaptador** diálogo cuadro, escriba un nombre para el adaptador y de la **adaptador** lista, seleccione **WCF-SQL**.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-113">In the **Adapter Properties** dialog box, enter a name for the adapter, and from the **Adapter** list, select **WCF-SQL**.</span></span>  
  
     <span data-ttu-id="0dfe0-114">![Agregar WCF &#45; Adaptador SQL a BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span><span class="sxs-lookup"><span data-stu-id="0dfe0-114">![Add WCF&#45;SQL adapter to BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span></span>  
  
5.  <span data-ttu-id="0dfe0-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0dfe0-115">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dfe0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dfe0-116">See Also</span></span>  
 [<span data-ttu-id="0dfe0-117">Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="0dfe0-117">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)