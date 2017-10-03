---
title: "Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db3d64ad-037d-486a-bdde-45c8199613f1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e818d6ca3fdda05ee877f9e6ef4f04d7a66176
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a><span data-ttu-id="b64ed-102">Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="b64ed-102">Configure transaction isolation level and transaction timeout with Oracle E-Business Suite</span></span>
<span data-ttu-id="b64ed-103">Al realizar operaciones de entrada (sondeo y la notificación) mediante la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar de manera adecuada el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción.</span><span class="sxs-lookup"><span data-stu-id="b64ed-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="b64ed-104">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="b64ed-104">To do this:</span></span>  
  
1.  <span data-ttu-id="b64ed-105">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b64ed-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="b64ed-106">En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="b64ed-107">Expanda la aplicación de BizTalk que haya implementado después de generar los metadatos mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b64ed-107">Expand the BizTalk application that you have deployed after generating the metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="b64ed-108">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="b64ed-109">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="b64ed-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="b64ed-110">En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="b64ed-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  
  
7.  <span data-ttu-id="b64ed-111">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.</span><span class="sxs-lookup"><span data-stu-id="b64ed-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  
  
8.  <span data-ttu-id="b64ed-112">Haga clic en **configurar** junto a la **tipo** lista.</span><span class="sxs-lookup"><span data-stu-id="b64ed-112">Click **Configure** adjacent to the **Type** list.</span></span>  
  
9. <span data-ttu-id="b64ed-113">En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="b64ed-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
10. <span data-ttu-id="b64ed-114">En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  
  
11. <span data-ttu-id="b64ed-115">En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **oracleEBSAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-115">In the **Select Behavior Extension** dialog box, select **oracleEBSAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  
  
12. <span data-ttu-id="b64ed-116">En el panel izquierdo de la **propiedades de transporte de WCF-Custom**, seleccione la **oracleEBSAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-116">In the left pane of the **WCF-Custom Transport Properties**, select the **oracleEBSAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span>  
  
13. <span data-ttu-id="b64ed-117">En el panel derecho de la **propiedades de transporte de WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros.</span><span class="sxs-lookup"><span data-stu-id="b64ed-117">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="b64ed-118">Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**.</span><span class="sxs-lookup"><span data-stu-id="b64ed-118">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span> <span data-ttu-id="b64ed-119">Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span><span class="sxs-lookup"><span data-stu-id="b64ed-119">For information about these transaction isolation levels, see the **Members** section at [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b64ed-120">Oracle E-Business Suite admite sólo los siguientes niveles de aislamiento de dos transacción: ReadCommitted y Serializable.</span><span class="sxs-lookup"><span data-stu-id="b64ed-120">Oracle E-Business Suite supports only the following two transaction isolation levels: ReadCommitted and Serializable.</span></span>  
  
     <span data-ttu-id="b64ed-121">![Establecer el nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span><span class="sxs-lookup"><span data-stu-id="b64ed-121">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span></span>  
  
14. <span data-ttu-id="b64ed-122">Haga clic en **Aceptar** en el **propiedades de transporte de WCF-Custom** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b64ed-122">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="b64ed-123">Haga clic en **Aceptar** en los cuadros de diálogo abiertos para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b64ed-123">Click **OK** in the open dialog boxes to save the changes.</span></span>