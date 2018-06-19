---
title: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e75d63118c24602439434c9c7ba281fa9cbc7805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222372"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a><span data-ttu-id="9aeeb-102">Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL</span><span class="sxs-lookup"><span data-stu-id="9aeeb-102">Configure Transaction Isolation Level and Transaction Timeout with SQL</span></span>
<span data-ttu-id="9aeeb-103">Al realizar operaciones de entrada (sondeo y la notificación) mediante la [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe configurar de manera adecuada el nivel de aislamiento de transacción y los valores de tiempo de espera de transacción.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="9aeeb-104">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="9aeeb-104">To do this:</span></span>  
  
1.  <span data-ttu-id="9aeeb-105">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="9aeeb-106">En el árbol de consola, expanda el **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="9aeeb-107">Expanda la aplicación en la que desea implementar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aeeb-107">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="9aeeb-108">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="9aeeb-109">En el **propiedades de puerto de recepción** cuadro de diálogo, en la **General** ficha, escriba un nombre para el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="9aeeb-110">En el panel izquierdo de la **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho para definir una nueva ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  
  
7.  <span data-ttu-id="9aeeb-111">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **WCF-Custom** en el **tipo** lista.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  
  
8.  <span data-ttu-id="9aeeb-112">Haga clic en **configurar** junto a la **tipo** lista.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-112">Click **Configure** adjacent to the **Type** list.</span></span>  
  
9. <span data-ttu-id="9aeeb-113">En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
10. <span data-ttu-id="9aeeb-114">En el **comportamiento** lista, haga clic en **ServiceBehavior**y haga clic en **Agregar extensión**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  
  
11. <span data-ttu-id="9aeeb-115">En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **sqlAdapterInboundTransactionBehavior**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-115">In the **Select Behavior Extension** dialog box, select **sqlAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  
  
12. <span data-ttu-id="9aeeb-116">En el panel izquierdo de la **propiedades de transporte de WCF-Custom**, seleccione la **sqlAdapterInboundTransactionBehavior** servicio bajo **ServiceBehavior**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-116">In the left pane of the **WCF-Custom Transport Properties**, select the **sqlAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span> <span data-ttu-id="9aeeb-117">Para recibir (mensaje de operación entrante), se pueden usar el sqlAdapterInboundTransactionBehavior para controlar el nivel de aislamiento y el valor predeterminado es **ReadCommitted**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-117">For receive (Inbound operation message), one can use the sqlAdapterInboundTransactionBehavior to control the isolation level and the default value is **ReadCommitted**.</span></span>  
  
13. <span data-ttu-id="9aeeb-118">En el panel derecho de la **propiedades de transporte de WCF-Custom**, especifique los valores adecuados para el **transactionIsolationLevel** y **transactionTimeout** parámetros.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-118">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="9aeeb-119">Puede seleccionar cualquiera de los siguientes niveles de aislamiento de transacción: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Instantánea**, **Chaos**, y **sin especificar**.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-119">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9aeeb-120">El valor predeterminado del nivel de aislamiento de transacción es **Serializable** para el adaptador de WCF-SQL para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-120">The default value of Transaction Isolation Level is **Serializable** for the WCF-SQL adapter for both inbound and outbound operations.</span></span> <span data-ttu-id="9aeeb-121">Para obtener información acerca de estos niveles de aislamiento de transacción, vea el **miembros** sección en [enumeración de nivel de aislamiento](http://go.microsoft.com/fwlink/?LinkId=126983) (http://go.microsoft.com/fwlink/?LinkId=126983).</span><span class="sxs-lookup"><span data-stu-id="9aeeb-121">For information about these transaction isolation levels, see the **Members** section at [Isolation Level Enumeration](http://go.microsoft.com/fwlink/?LinkId=126983) (http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  
  
     <span data-ttu-id="9aeeb-122">![Establecer el nivel de aislamiento de transacción](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span><span class="sxs-lookup"><span data-stu-id="9aeeb-122">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span></span>  
  
14. <span data-ttu-id="9aeeb-123">Haga clic en **Aceptar** en el **propiedades de transporte de WCF-Custom** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-123">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="9aeeb-124">Haga clic en **Aceptar** en los cuadros de diálogo abiertos para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9aeeb-124">Click **OK** in the open dialog boxes to save the changes.</span></span>