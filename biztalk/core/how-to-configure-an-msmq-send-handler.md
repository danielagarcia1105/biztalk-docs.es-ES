---
title: "Cómo configurar un controlador de envío MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-send-handler"></a><span data-ttu-id="2bf3f-102">Cómo configurar un controlador de envío MSMQ</span><span class="sxs-lookup"><span data-stu-id="2bf3f-102">How to Configure an MSMQ Send Handler</span></span>
<span data-ttu-id="2bf3f-103">El siguiente procedimiento se utiliza para modificar las variables globales de un controlador de envío MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-103">Use the following procedure to change the global variables for an MSMQ send handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bf3f-104">Cada host puede tener solo un controlador de envío asociado a él.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a><span data-ttu-id="2bf3f-105">Para cambiar variables globales de un controlador de envío MSMQ utilizando la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2bf3f-105">To change global variables for an MSMQ send handler by using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="2bf3f-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="2bf3f-107">En la lista de adaptadores expandida, haga clic en **MSMQ**, en el panel derecho, haga el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2bf3f-108">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con la que asociará el controlador de envío y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2bf3f-109">En el **propiedades de transporte de MSMQ** diálogo cuadro, escriba un valor para **tamaño de lote**.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-109">In the **MSMQ Transport Properties** dialog box, enter a value for **Batch Size**.</span></span>  
  
     <span data-ttu-id="2bf3f-110">El controlador de envío MSMQ enviará mensajes a colas de destino utilizando especificado **tamaño de lote** parámetro.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-110">The MSMQ send handler will send messages to destination queues using the specified **Batch Size** parameter.</span></span> <span data-ttu-id="2bf3f-111">El valor predeterminado **tamaño de lote** valor es 5.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-111">The default **Batch Size** value is 5.</span></span>  
  
5.  <span data-ttu-id="2bf3f-112">Haga clic en **Aceptar** y haga clic en **Aceptar** otra vez para cerrar el **propiedades de controlador de adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2bf3f-112">Click **OK** and click **OK** again to close the **Adapter Handler Properties** dialog box.</span></span>