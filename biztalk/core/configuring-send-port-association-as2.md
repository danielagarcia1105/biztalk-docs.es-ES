---
title: Configuración de la asociación de puerto de envío (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8624d4c-cee8-4072-bff7-2468d83a06de
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: babc3084515b50e0414c296f9029f223511305e3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006653"
---
# <a name="configuring-send-port-association-as2"></a><span data-ttu-id="b3900-102">Configuración de la asociación de puerto de envío (AS2)</span><span class="sxs-lookup"><span data-stu-id="b3900-102">Configuring Send Port Association (AS2)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b3900-103"> usa la asociación de puertos de envío para resolver un acuerdo para un intercambio de AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="b3900-103"> uses send port association to resolve an agreement for an outgoing AS2 message.</span></span> <span data-ttu-id="b3900-104">Un mensaje AS2 se resuelve para un acuerdo haciendo coincidir el puerto de envío que suscribió el mensaje con el puerto de envío asociado a un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-104">An AS2 message is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="b3900-105">Este tema proporciona instrucciones sobre cómo asociar los puertos de envío a un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b3900-106">En BizTalk Server, la asociación de puertos de envío se realiza en el nivel de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-106">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="b3900-107">Sin embargo, en BizTalk Server 2009, los puertos de envío se asociaron en el nivel de entidad.</span><span class="sxs-lookup"><span data-stu-id="b3900-107">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="b3900-108">Por compatibilidad con versiones anteriores, un **puertos de envío** página también está disponible como parte de las propiedades de entidad (vea [configurar propiedades de entidad General (AS2)](../core/configuring-general-party-properties-as2.md)).</span><span class="sxs-lookup"><span data-stu-id="b3900-108">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties (AS2)](../core/configuring-general-party-properties-as2.md)).</span></span> <span data-ttu-id="b3900-109">Siempre que asocie un puerto de envío con un acuerdo, la configuración del puerto de envío se propaga a la configuración de la entidad y también se puede ver la asociación de puerto de envío en esta página.</span><span class="sxs-lookup"><span data-stu-id="b3900-109">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="b3900-110">Sin embargo, el proceso inverso no es verdadero.</span><span class="sxs-lookup"><span data-stu-id="b3900-110">However, the reverse is not true.</span></span> <span data-ttu-id="b3900-111">No se puede asociar un puerto de envío con una entidad y, después, hacer que ese puerto de envío esté automáticamente disponible como parte de la configuración del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-111">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b3900-112">La cuadrícula de asociación de puerto de envío está deshabilitada en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación mientras creaba la entidad para la que va a crear el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-112">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="b3900-113">La cuadrícula solo se deshabilita en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="b3900-113">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="b3900-114">Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la cuadrícula está deshabilitada en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="b3900-114">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b3900-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b3900-115">Prerequisites</span></span>  
 <span data-ttu-id="b3900-116">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3900-116">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-send-port-association"></a><span data-ttu-id="b3900-117">Para configurar la asociación de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="b3900-117">To configure send port association</span></span>  
  
1.  <span data-ttu-id="b3900-118">Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md).</span><span class="sxs-lookup"><span data-stu-id="b3900-118">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="b3900-119">Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3900-119">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b3900-120">En una ficha de acuerdo unidireccional, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="b3900-120">On a one-way agreement tab, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="b3900-121">Haga clic en la celda vacía situada bajo la **nombre** columna y en la lista desplegable, seleccione el puerto de envío para asociar el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b3900-121">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="b3900-122">El **URI** columna muestra la dirección del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="b3900-122">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="b3900-123">Para quitar una asociación de puerto de envío, seleccione la fila de un puerto de envío y haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="b3900-123">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="b3900-124">Para ver las propiedades de un puerto de envío, seleccione la fila de un puerto de envío y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3900-124">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b3900-125">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b3900-125">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3900-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3900-126">See Also</span></span>  
 [<span data-ttu-id="b3900-127">Configuración de las propiedades de acuerdo AS2</span><span class="sxs-lookup"><span data-stu-id="b3900-127">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)