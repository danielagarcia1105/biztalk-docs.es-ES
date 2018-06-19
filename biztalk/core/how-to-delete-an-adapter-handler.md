---
title: Cómo eliminar un controlador de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, handlers
- deleting, handlers [adapters]
- handlers [adapters], deleting
ms.assetid: 95db5652-e175-45d1-b713-1ad73655a592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d591779a55fb7050e4ed229e19d19a312645462
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249628"
---
# <a name="how-to-delete-an-adapter-handler"></a><span data-ttu-id="0d35c-102">Cómo eliminar un controlador de adaptador</span><span class="sxs-lookup"><span data-stu-id="0d35c-102">How to Delete an Adapter Handler</span></span>
<span data-ttu-id="0d35c-103">Para eliminar un controlador de adaptador de envío o recepción, utilice la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0d35c-103">You can delete a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="0d35c-104">Antes de quitar un controlador de adaptador, debe quitar todas las ubicaciones de recepción o los puertos de envío con los que está asociado.</span><span class="sxs-lookup"><span data-stu-id="0d35c-104">Before you remove an adapter handler, you must remove all receive locations or send ports with which it is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d35c-105">Debe ser miembro del grupo de administración de SSO para eliminar un controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="0d35c-105">You must be a member of the SSO Administration group to delete an adapter handler.</span></span>  
  
### <a name="to-delete-an-adapter-handler"></a><span data-ttu-id="0d35c-106">Para eliminar un controlador de adaptador</span><span class="sxs-lookup"><span data-stu-id="0d35c-106">To delete an adapter handler</span></span>  
  
1.  <span data-ttu-id="0d35c-107">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="0d35c-107">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="0d35c-108">En la lista de adaptadores expandida, seleccione el adaptador para el que desea eliminar el controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="0d35c-108">In the expanded adapter list, select the adapter for which you want to delete the adapter handler.</span></span>  
  
3.  <span data-ttu-id="0d35c-109">Haga clic en el controlador de adaptador que desea eliminar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0d35c-109">Right-click the adapter handler that you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="0d35c-110">Haga clic en **Sí** para confirmar que desea eliminar este controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="0d35c-110">Click **Yes** to confirm that you want to delete this adapter handler.</span></span>  
  
5.  <span data-ttu-id="0d35c-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d35c-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d35c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d35c-112">See Also</span></span>  
 [<span data-ttu-id="0d35c-113">Crear y eliminar controladores de adaptador</span><span class="sxs-lookup"><span data-stu-id="0d35c-113">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)