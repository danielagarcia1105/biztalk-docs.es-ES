---
title: Cómo configurar controlador de recepción de SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], receive handlers
- SOAP adapters, receive handlers
- receive handlers, SOAP adapters
ms.assetid: e1174381-f36c-4131-83b7-26bfa879802e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4054635a8ffa4e019f7db9513e5e20e997f7e291
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247316"
---
# <a name="how-to-configure-a-soap-receive-handler"></a><span data-ttu-id="e720f-102">Cómo configurar controlador de recepción de SOAP</span><span class="sxs-lookup"><span data-stu-id="e720f-102">How to Configure a SOAP Receive Handler</span></span>
<span data-ttu-id="e720f-103">Puede configurar los parámetros del controlador de recepción de SOAP con la consola de administración de servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e720f-103">You can configure the SOAP receive handler settings by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="e720f-104">Si configura el adaptador utilizando la consola de administración BizTalk Server, no será necesario definir las propiedades de reemplazo del controlador en el Explorador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e720f-104">If you configure the adapter using the BizTalk Server Administration Console, the handler override properties do not need to be set in BizTalk Explorer.</span></span>  
  
### <a name="to-change-global-variables-for-the-soap-receive-handler"></a><span data-ttu-id="e720f-105">Para cambiar las variables globales del controlador de recepción de SOAP</span><span class="sxs-lookup"><span data-stu-id="e720f-105">To change global variables for the SOAP receive handler</span></span>  
  
1.  <span data-ttu-id="e720f-106">En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="e720f-106">In the BizTalk Server Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="e720f-107">En la lista de adaptadores expandida, haga clic en **SOAP**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e720f-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e720f-108">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con el que estará asociado, el controlador de recepción y, a continuación, Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e720f-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e720f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e720f-109">See Also</span></span>  
 <span data-ttu-id="e720f-110">[Configurar el adaptador SOAP](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e720f-110">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="e720f-111">Consumir servicios Web</span><span class="sxs-lookup"><span data-stu-id="e720f-111">Consuming Web Services</span></span>](../core/consuming-web-services.md)