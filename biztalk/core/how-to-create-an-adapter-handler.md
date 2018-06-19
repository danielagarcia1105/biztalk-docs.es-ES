---
title: Cómo crear un controlador de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e26caf02978006040e52ed3c62e520f51362e2c4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969866"
---
# <a name="how-to-create-an-adapter-handler"></a><span data-ttu-id="ea72b-102">Cómo crear un controlador de adaptador</span><span class="sxs-lookup"><span data-stu-id="ea72b-102">How to Create an Adapter Handler</span></span>
<span data-ttu-id="ea72b-103">Se puede crear un controlador de adaptador de envío o recepción utilizando la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ea72b-103">You can create a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea72b-104">Es preciso ser miembro del grupo de administradores de inicio de sesión único para crear un controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea72b-104">You must be a member of the Single Sign-On Administrators group to create an adapter handler.</span></span>  
  
### <a name="to-create-an-adapter-handler"></a><span data-ttu-id="ea72b-105">Para crear un controlador de adaptador</span><span class="sxs-lookup"><span data-stu-id="ea72b-105">To create an adapter handler</span></span>  
  
1.  <span data-ttu-id="ea72b-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="ea72b-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="ea72b-107">En la lista de adaptadores expandida, haga clic en el adaptador para el que desea agregar un envío o controlador de recepción, seleccione **New**y, a continuación, haga clic en **controlador de envío** para crear un controlador de envío o haga clic en  **Controlador de recepción** para crear un controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="ea72b-107">In the expanded adapter list, right-click the adapter for which you would like to add a send or receive handler, point to **New**, and then click **Send Handler** to create a send handler or click **Receive Handler** to create a receive handler.</span></span>  
  
3.  <span data-ttu-id="ea72b-108">En el  **\<nombre de host\> propiedades** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con el que el adaptador se asociará el controlador.</span><span class="sxs-lookup"><span data-stu-id="ea72b-108">In the **\<host name\> Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the adapter handler will be associated.</span></span>  
  
4.  <span data-ttu-id="ea72b-109">Si va a crear un controlador de envío de adaptador, seleccione la opción de **establecer este controlador como predeterminado** si desea que sea el controlador de envío predeterminado para este adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea72b-109">If you are creating an adapter send handler, select the option to **Make this the default handler** if you would like for this to be the default send handler for this adapter.</span></span>  
  
5.  <span data-ttu-id="ea72b-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea72b-110">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea72b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea72b-111">See Also</span></span>  
 [<span data-ttu-id="ea72b-112">Creación y eliminación de controladores de adaptador</span><span class="sxs-lookup"><span data-stu-id="ea72b-112">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)