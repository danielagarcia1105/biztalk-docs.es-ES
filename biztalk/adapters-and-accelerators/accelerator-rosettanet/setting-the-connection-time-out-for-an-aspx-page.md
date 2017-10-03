---
title: "Establecer el tiempo de espera de conexión para una página ASPX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a><span data-ttu-id="27278-102">Establecer el tiempo de espera de conexión para una página ASPX</span><span class="sxs-lookup"><span data-stu-id="27278-102">Setting the Connection Time-Out for an ASPX Page</span></span>
<span data-ttu-id="27278-103">Cuando se usa una página ASPX para mensajes sincrónicos, debe aumentar el tiempo de espera de conexión de la página ASPX, por lo que puede esperar a que el mensaje esperado.</span><span class="sxs-lookup"><span data-stu-id="27278-103">When you use an ASPX page for synchronous messages, you must increase the connection time-out for the ASPX page so that it can wait for the expected message.</span></span>  
  
 <span data-ttu-id="27278-104">Aumentar el tiempo de espera de conexión de la página ASPX puede tener consecuencias no deseadas.</span><span class="sxs-lookup"><span data-stu-id="27278-104">Increasing the connection time-out for the ASPX page can have unintended consequences.</span></span> <span data-ttu-id="27278-105">En primer lugar, aumenta el riesgo de un ataque de denegación de servicio y la amenaza de agotar el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="27278-105">First, it increases the risk of a denial-of-service attack and the threat of exhausting the thread pool.</span></span> <span data-ttu-id="27278-106">En segundo lugar, si hay demasiadas conexiones sincrónicas en la página ASPX, puede bloquear el sistema de.</span><span class="sxs-lookup"><span data-stu-id="27278-106">Second, if there are too many synchronous connections on the ASPX page, the system can lock up.</span></span> <span data-ttu-id="27278-107">Por lo tanto, mientras que debe aumentar el tiempo de espera de conexión, tenga cuidado de no lo aumente demasiado.</span><span class="sxs-lookup"><span data-stu-id="27278-107">Therefore, while you must increase the connection time-out, be careful not to increase it too much.</span></span>  
  
 <span data-ttu-id="27278-108">Establece el tiempo de espera de conexión en el mínimo permitido por la organización RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="27278-108">Set the connection time-out to the minimum allowed by the RosettaNet organization.</span></span> <span data-ttu-id="27278-109">Para obtener más información acerca de los parámetros de control de tiempo para un proceso de interfaz de socio (PIP), consulte la tabla 4-3: controles de intercambio de mensajes, en la especificación de PIP de RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="27278-109">For more information about the timing parameters for a Partner Interface Process (PIP), see Table 4-3: Message Exchange Controls, in the RosettaNet PIP Specification.</span></span>  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a><span data-ttu-id="27278-110">Para establecer el tiempo de espera de conexión de la página ASPX</span><span class="sxs-lookup"><span data-stu-id="27278-110">To set the connection time-out for the ASPX page</span></span>  
  
1.  <span data-ttu-id="27278-111">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="27278-111">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="27278-112">En el Administrador de IIS, expanda el nodo para el equipo local y, a continuación, expanda **sitios Web**.</span><span class="sxs-lookup"><span data-stu-id="27278-112">In IIS Manager, expand the node for the local computer, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="27278-113">Haga clic con el botón secundario en **Sitio web predeterminado**y, después, en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="27278-113">Right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="27278-114">En el cuadro de diálogo Propiedades del sitio Web predeterminado, en la **sitio Web** ficha la **tiempo de espera de conexión** , escriba un valor adecuado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27278-114">In the Default Web Site Properties dialog box, on the **Web Site** tab, in the **Connection Timeout** box, type an appropriate value, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27278-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="27278-115">See Also</span></span>  
 [<span data-ttu-id="27278-116">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="27278-116">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)