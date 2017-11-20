---
title: "Cómo configurar filtros para un grupo de puertos de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632b9232e87448ddb27d71735b09598b1a9fbc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="87351-102">Cómo configurar filtros para un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="87351-102">How to Configure Filters for a Send Port Group</span></span>
<span data-ttu-id="87351-103">En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar uno o varios filtros para un grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="87351-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure one or more filters for a send port group.</span></span> <span data-ttu-id="87351-104">Los filtros pueden utilizarse para crear aplicaciones de enrutamiento por contenidos (CBR) o de mensajería simple.</span><span class="sxs-lookup"><span data-stu-id="87351-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="87351-105">Un filtro establece condiciones para las propiedades o los campos de mensaje que determinan qué mensajes se enrutan al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="87351-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port group.</span></span> <span data-ttu-id="87351-106">Un filtro no filtra los mensajes que una orquestación enruta al grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="87351-106">A filter does not filter the messages that an orchestration routes to the send port group.</span></span>  
  
 <span data-ttu-id="87351-107">Es posible crear una o varias expresiones de filtro formadas por una propiedad de mensaje, un operador y un valor validado con respecto a la propiedad mediante el operador.</span><span class="sxs-lookup"><span data-stu-id="87351-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="87351-108">Por ejemplo, podría crear una expresión similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87351-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="87351-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="87351-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="87351-110">Con este filtro, el grupo de puertos de envío sólo se suscribirá a mensajes cuyo Id. de mensaje de MSMQ sea 1.</span><span class="sxs-lookup"><span data-stu-id="87351-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="87351-111">Puede crear expresiones adicionales y especificar la existencia de una relación con AND u OR entre estas expresiones y otras; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="87351-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="87351-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="87351-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="87351-113">SMTP.From = MyServer</span><span class="sxs-lookup"><span data-stu-id="87351-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="87351-114">En este caso, el grupo de puertos de envío se suscribirá a todos los mensajes cuyo Id. de mensaje de MSMQ sea 1 o que se hayan enviado desde un servidor SMTP denominado MyServer.</span><span class="sxs-lookup"><span data-stu-id="87351-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87351-115">Si crea un filtro para un grupo de puertos de envío en una aplicación que utilice un esquema de propiedades en otra aplicación y si, a continuación, importa la primera aplicación en un nuevo grupo de BizTalk, no recibirá ninguna advertencia de la falta del esquema, y el filtrado no se efectuará una vez instalada e iniciada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87351-115">If you create a filter for a send port group in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="87351-116">Puede corregir el problema importando la aplicación que contiene el esquema antes de instalar la aplicación que no contiene el esquema.</span><span class="sxs-lookup"><span data-stu-id="87351-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87351-117">El desarrollador de aplicaciones puede configurar filtros para un grupo de puertos de envío durante el proceso de desarrollo mediante el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="87351-117">The application developer can configure filters for a send port group during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87351-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="87351-118">Prerequisites</span></span>  
 <span data-ttu-id="87351-119">Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="87351-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="87351-120">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="87351-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="87351-121">Para configurar filtros para un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="87351-121">To configure filters for a send port group</span></span>  
  
1.  <span data-ttu-id="87351-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="87351-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="87351-123">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar un filtro de grupo de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="87351-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure a send port group filter.</span></span>  
  
3.  <span data-ttu-id="87351-124">Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío, haga clic en **propiedades**y, a continuación, haga clic en **filtros**.</span><span class="sxs-lookup"><span data-stu-id="87351-124">Click **Send Port Groups**, right-click the send port group, click **Properties**, and then click **Filters**.</span></span>  
  
4.  <span data-ttu-id="87351-125">Configure los filtros como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87351-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="87351-126">Use</span><span class="sxs-lookup"><span data-stu-id="87351-126">Use this</span></span>|<span data-ttu-id="87351-127">Para</span><span class="sxs-lookup"><span data-stu-id="87351-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="87351-128">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="87351-128">**Delete**</span></span>|<span data-ttu-id="87351-129">Eliminar la expresión de filtro seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87351-129">Click to delete the selected filter expression.</span></span>|  
    |<span data-ttu-id="87351-130">**Subir**</span><span class="sxs-lookup"><span data-stu-id="87351-130">**Move Up**</span></span>|<span data-ttu-id="87351-131">Subir la propiedad seleccionada en la secuencia de expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="87351-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="87351-132">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="87351-132">**Move Down**</span></span>|<span data-ttu-id="87351-133">Bajar la propiedad seleccionada en la secuencia de expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="87351-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="87351-134">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="87351-134">**Property**</span></span>|<span data-ttu-id="87351-135">En la lista, hacer clic en una propiedad de mensaje para utilizarla en esta expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="87351-135">In the list, click a message property to use in this filter expression.</span></span>|  
    |<span data-ttu-id="87351-136">**Operador**</span><span class="sxs-lookup"><span data-stu-id="87351-136">**Operator**</span></span>|<span data-ttu-id="87351-137">Escribir o seleccionar el operador para la expresión.</span><span class="sxs-lookup"><span data-stu-id="87351-137">Type or select the operator for the expression.</span></span>|  
    |<span data-ttu-id="87351-138">**Valor**</span><span class="sxs-lookup"><span data-stu-id="87351-138">**Value**</span></span>|<span data-ttu-id="87351-139">Escribir el valor que se validará con la propiedad.</span><span class="sxs-lookup"><span data-stu-id="87351-139">Type the value to validate against the property.</span></span> <span data-ttu-id="87351-140">El tipo de valor aceptado varía en función del tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="87351-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="87351-141">Para ver qué tipo de valor se acepta para una propiedad, coloque el puntero del mouse sobre ésta.</span><span class="sxs-lookup"><span data-stu-id="87351-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="87351-142">Los valores aceptables son los siguientes: Int: (entero) debe ser un número entero.</span><span class="sxs-lookup"><span data-stu-id="87351-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="87351-143">Cadena: Una cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="87351-143">String: A character string.</span></span> <span data-ttu-id="87351-144">fecha y hora: fecha y hora en. Formato compatible con NET.</span><span class="sxs-lookup"><span data-stu-id="87351-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="87351-145">Para obtener más información sobre formatos de fecha y hora compatibles con .NET, vea "DateTimeFormatInfo Class" en la Ayuda de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87351-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
    |<span data-ttu-id="87351-146">**Agrupar por**</span><span class="sxs-lookup"><span data-stu-id="87351-146">**Group by**</span></span>|<span data-ttu-id="87351-147">Seleccione **y** o **o** para indicar la relación entre las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="87351-147">Select **And** or **Or** to indicate the relationship between filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87351-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="87351-148">See Also</span></span>  
 [<span data-ttu-id="87351-149">Crear y configurar grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="87351-149">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)