---
title: Cómo configurar controlador de recepción de POP3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, POP3 adapters
- POP3 adapters, receive handlers
- configuring [POP3 adapters], receive handlers
ms.assetid: 2191c201-545e-4d5a-a1ca-3c38c7b8258d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8868ce589fa7556da185dcaf4c71b5bfd5cae159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247788"
---
# <a name="how-to-configure-a-pop3-receive-handler"></a><span data-ttu-id="3c206-102">Cómo configurar controlador de recepción de POP3</span><span class="sxs-lookup"><span data-stu-id="3c206-102">How to Configure a POP3 Receive Handler</span></span>
<span data-ttu-id="3c206-103">Siga el procedimiento que se especifica a continuación para modificar el host asociado al controlador de recepción POP3.</span><span class="sxs-lookup"><span data-stu-id="3c206-103">Use the following procedure to change the host associated with the POP3 receive handler.</span></span>  
  
### <a name="to-configure-the-general-properties-for-a-pop3-receive-handler"></a><span data-ttu-id="3c206-104">Para configurar las propiedades generales de un controlador de recepción POP3</span><span class="sxs-lookup"><span data-stu-id="3c206-104">To configure the general properties for a POP3 receive handler</span></span>  
  
1.  <span data-ttu-id="3c206-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="3c206-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="3c206-106">En la lista de adaptadores expandida, haga clic en **POP3**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3c206-106">In the expanded adapter list, click **POP3**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3c206-107">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="3c206-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="3c206-108">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c206-108">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c206-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c206-109">See Also</span></span>  
 [<span data-ttu-id="3c206-110">Consideraciones para ejecutar controladores del adaptador en un Host en clúster</span><span class="sxs-lookup"><span data-stu-id="3c206-110">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)