---
title: Agregar el adaptador de base de datos de Oracle a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d71e161-addc-47d4-9103-3655f3fb0b0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95ef6f3c4f33ddfdb6dbaca3e1823149ede66abf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997877"
---
# <a name="adding-the-oracle-database-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="ca3af-102">Agregar el adaptador de base de datos de Oracle a la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ca3af-102">Adding the Oracle Database Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="ca3af-103">Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ca3af-103">This topic provides instructions on how to add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca3af-104">No es necesario realizar estas tareas si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca3af-104">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="add-the-oracle-database-adapter"></a><span data-ttu-id="ca3af-105">Agregar el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ca3af-105">Add the Oracle Database Adapter</span></span>  
  
1. <span data-ttu-id="ca3af-106">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="ca3af-106">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ca3af-107">Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="ca3af-107">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3. <span data-ttu-id="ca3af-108">Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ca3af-108">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
    <span data-ttu-id="ca3af-109">![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="ca3af-109">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="ca3af-110">En el **propiedades del adaptador** diálogo cuadro, escriba un nombre para el adaptador y desde el **adaptador** lista, seleccione **WCF-OracleDB**.</span><span class="sxs-lookup"><span data-stu-id="ca3af-110">In the **Adapter Properties** dialog box, enter a name for the adapter and from the **Adapter** list, select **WCF-OracleDB**.</span></span>  
  
    <span data-ttu-id="ca3af-111">![Adición de WCF&#45;adaptador OracleDB a BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span><span class="sxs-lookup"><span data-stu-id="ca3af-111">![Adding WCF&#45;OracleDB adapter to BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span></span>  
  
5. <span data-ttu-id="ca3af-112">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca3af-112">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3af-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca3af-113">See Also</span></span>  
[<span data-ttu-id="ca3af-114">Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ca3af-114">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)