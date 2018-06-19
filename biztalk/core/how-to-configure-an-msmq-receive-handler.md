---
title: Cómo configurar controlador de recepción de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f34e1b3f399c93bd92aa9c4e07f6e0082d25204
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247876"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a><span data-ttu-id="9078e-102">Cómo configurar un controlador de recepción de MSMQ</span><span class="sxs-lookup"><span data-stu-id="9078e-102">How to Configure an MSMQ Receive Handler</span></span>
<span data-ttu-id="9078e-103">Utilice el procedimiento siguiente para cambiar el host al que está asociado el controlador de recepción de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9078e-103">Use the following procedure to change the host with which the MSMQ receive handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9078e-104">Cada host solo se puede asociar a un controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="9078e-104">Each host can associate with only one receive handler.</span></span>  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a><span data-ttu-id="9078e-105">Para cambiar el host al que está asociado el controlador de recepción de MSMQ</span><span class="sxs-lookup"><span data-stu-id="9078e-105">To change the host with which the MSMQ receive handler is associated</span></span>  
  
1.  <span data-ttu-id="9078e-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="9078e-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="9078e-107">En la lista de adaptadores expandida, haga clic en **MSMQ**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9078e-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9078e-108">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="9078e-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="9078e-109">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9078e-109">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9078e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9078e-110">See Also</span></span>  
 [<span data-ttu-id="9078e-111">Configurar el adaptador MSMQ</span><span class="sxs-lookup"><span data-stu-id="9078e-111">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)