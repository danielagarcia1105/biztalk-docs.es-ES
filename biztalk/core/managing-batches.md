---
title: Administrar lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4903cf2722f1938ceb1df92c2a3ac2a88fe6d61e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-batches"></a><span data-ttu-id="bd759-102">Administración de lotes</span><span class="sxs-lookup"><span data-stu-id="bd759-102">Managing Batches</span></span>
<span data-ttu-id="bd759-103">Cómo controlar manualmente la versión de procesar por lotes los intercambios, mediante el uso de los controles en la parte superior de la **configuración de lote** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo (en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración) para X12 y codificación EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="bd759-103">How to control manually the release of batched interchanges, using the controls at the top of the **Batch Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box (in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console) for both X12 and EDIFACT encoding.</span></span> <span data-ttu-id="bd759-104">En estos procedimientos se realizan mediante los siguientes controles:</span><span class="sxs-lookup"><span data-stu-id="bd759-104">This involves the following controls:</span></span>  
  
-   <span data-ttu-id="bd759-105">**A partir de un lote**.</span><span class="sxs-lookup"><span data-stu-id="bd759-105">**Starting a batch**.</span></span> <span data-ttu-id="bd759-106">Activa una instancia de la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-106">Activates an instance of the batching orchestration.</span></span> <span data-ttu-id="bd759-107">Después de seleccionar la **iniciar** botón, elementos de procesamiento por lotes se recopilan cuando la instancia está dentro del intervalo de activación.</span><span class="sxs-lookup"><span data-stu-id="bd759-107">After you select the **Start** button, batching elements are collected when the instance is within the activation range.</span></span>  
  
-   <span data-ttu-id="bd759-108">**Invalidar un lote**.</span><span class="sxs-lookup"><span data-stu-id="bd759-108">**Overriding a batch**.</span></span> <span data-ttu-id="bd759-109">Crea un lote con los elementos existentes y se envía de inmediato.</span><span class="sxs-lookup"><span data-stu-id="bd759-109">Creates a batch using existing elements and immediately sends it.</span></span> <span data-ttu-id="bd759-110">A continuación, la orquestación de procesamiento por lotes reanuda el procesamiento por lotes según la configuración establecida.</span><span class="sxs-lookup"><span data-stu-id="bd759-110">After the batch is sent, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
-   <span data-ttu-id="bd759-111">**Detener un lote**.</span><span class="sxs-lookup"><span data-stu-id="bd759-111">**Stopping a batch**.</span></span> <span data-ttu-id="bd759-112">Desactiva una instancia activada de la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-112">Deactivates an activated instance of the batching orchestration.</span></span> <span data-ttu-id="bd759-113">Después de seleccionar la **detener** botón, la orquestación crea un lote a partir de elementos por lotes existentes, entrega el intercambio a la canalización de envío EDI y finaliza.</span><span class="sxs-lookup"><span data-stu-id="bd759-113">After you select the **Stop** button, the orchestration creates a batch from existing batch elements, delivers the interchange to the EDI send pipeline, and terminates.</span></span>  
  
 <span data-ttu-id="bd759-114">Los controles actúan en una única configuración de lote.</span><span class="sxs-lookup"><span data-stu-id="bd759-114">The controls act upon a single batch configuration.</span></span>  
  
 <span data-ttu-id="bd759-115">Las acciones que BizTalk realiza cuando se presiona el **iniciar** botón dependen el **filtro** criterios, **versión** criterios, y **activación**configuración del intervalo en el **configuración de lote** página.</span><span class="sxs-lookup"><span data-stu-id="bd759-115">The actions that BizTalk takes when you press the **Start** button depend upon the **Filter** criteria, **Release** criteria, and **Activation** range settings on the **Batch Configuration** page.</span></span> <span data-ttu-id="bd759-116">Los criterios de filtro determinan qué mensajes se procesarán por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-116">The filter criteria determine which messages are batched.</span></span> <span data-ttu-id="bd759-117">Los criterios de lanzamiento determinan cuándo se lanzan los lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-117">The release criteria determine when batches are released.</span></span> <span data-ttu-id="bd759-118">Las propiedades del intervalo de activación determinan si una instancia activada de la orquestación de procesamiento por lotes recopilará elementos para el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-118">The activation range properties determine whether an activated instance of the batching orchestration will collect elements for batching.</span></span> <span data-ttu-id="bd759-119">Para obtener más información acerca de estas opciones, consulte [configurar un lote saliente](../core/configuring-an-outgoing-batch.md).</span><span class="sxs-lookup"><span data-stu-id="bd759-119">For more information about these settings, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  

<span data-ttu-id="bd759-120">En este tema se muestra cómo iniciar, detener, invalidar y eliminar lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-120">This topic shows you how to start, stop, override, and delete batches.</span></span>  

> [!NOTE]
>  <span data-ttu-id="bd759-121">Para obtener instrucciones sobre cómo configurar lotes, consulte [configurar X12 procesamiento por lotes](../core/configuring-batching-x12.md) o [configuración de procesamiento por lotes de EDIFACT](../core/configuring-batching-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="bd759-121">For instructions on how to configure batches, see [Configuring X12 Batching](../core/configuring-batching-x12.md) or [Configuring EDIFACT Batching](../core/configuring-batching-edifact.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="bd759-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bd759-122">Prerequisites</span></span>  
 <span data-ttu-id="bd759-123">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd759-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd759-124">Los miembros del grupo de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden iniciar, detener o invalidar un lote, pero no pueden cambiar la configuración relativa al procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-124">A member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group can start, stop, or override a batch, but cannot change any configuration setting related to batching.</span></span> <span data-ttu-id="bd759-125">Debe ser miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cambiar la configuración de lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-125">You must be a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to change batch configuration.</span></span>  
  
## <a name="start-stop-and-override-batches"></a><span data-ttu-id="bd759-126">Iniciar, detener o invalidar lotes</span><span class="sxs-lookup"><span data-stu-id="bd759-126">Start, stop, and override batches</span></span>  
  
1.  <span data-ttu-id="bd759-127">Abra  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, expanda el grupo de BizTalk y seleccione **partes**.</span><span class="sxs-lookup"><span data-stu-id="bd759-127">Open **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand the BizTalk group, and select **Parties**.</span></span>  
  
2.  <span data-ttu-id="bd759-128">En el **entidades y perfiles empresariales** página, en la **contratos** sección, haga clic en el acuerdo con la configuración del lote que desea iniciar, detener o invalidar.</span><span class="sxs-lookup"><span data-stu-id="bd759-128">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to start, stop, or override.</span></span>  
  
3.  <span data-ttu-id="bd759-129">En la ficha de acuerdo unidireccional del **propiedades del acuerdo de**, seleccione la **configuración de lote** página.</span><span class="sxs-lookup"><span data-stu-id="bd759-129">In the one-way agreement tab of the **Agreement Properties**, select the **Batch Configuration** page.</span></span>  
  
4.  <span data-ttu-id="bd759-130">En el **configuración de lote** , seleccione la pestaña del lote que desea iniciar, detener o invalidar.</span><span class="sxs-lookup"><span data-stu-id="bd759-130">On the **Batch Configuration** page, select the tab for the batch that you want to start, stop, or override.</span></span>  
  
5.  <span data-ttu-id="bd759-131">Compruebe que las propiedades de los criterios de filtro, los criterios de lanzamiento y el intervalo de activación son las adecuadas.</span><span class="sxs-lookup"><span data-stu-id="bd759-131">Verify that the filter criteria, release criteria, and activation range properties are as they should be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd759-132">Si es un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de operadores, pero no el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores, puede iniciar, detener o invalidar lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-132">If you are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, but not the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group, you can start, stop, or override batches.</span></span> <span data-ttu-id="bd759-133">Sin embargo, no se puede cambiar la configuración de lotes.</span><span class="sxs-lookup"><span data-stu-id="bd759-133">But, you cannot change batch configuration settings.</span></span> <span data-ttu-id="bd759-134">Los valores son visibles para usted, pero si cambia un valor y, a continuación, seleccione **Aceptar**, obtendrá un error de permisos.</span><span class="sxs-lookup"><span data-stu-id="bd759-134">The settings are visible to you, but if you change a setting, and then select **OK**, you get a permissions error.</span></span>  
  
6.  <span data-ttu-id="bd759-135">Si no se ha activado una instancia de la orquestación por lotes, seleccione **iniciar** para activar una instancia.</span><span class="sxs-lookup"><span data-stu-id="bd759-135">If an instance of the batching orchestration has not been activated, select **Start** to activate an instance.</span></span>  
  
    > [!NOTE]
    >  - <span data-ttu-id="bd759-136">Puede indicar que una instancia de la orquestación por lotes no se ha activado si el **iniciar** botón está habilitado, y **no está activado el procesamiento por lotes** aparece justo debajo del **iniciar** control.</span><span class="sxs-lookup"><span data-stu-id="bd759-136">You can tell that an instance of the batching orchestration has not been activated if the **Start** button is enabled, and **Batching is not activated** is displayed just beneath the **Start** control.</span></span>  
    >  - <span data-ttu-id="bd759-137">Si ha seleccionado la **iniciar** botón y se ha activado una instancia de la orquestación por lotes, pero no se recopilan elementos para el lote, a continuación, compruebe que la fecha y hora en la **activación** ha transcurrido el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bd759-137">If you have clicked the **Start** button, and an instance of the batching orchestration has been activated, but no elements are being collected for the batch, then verify that the datetime in the **Activation** text box has transpired.</span></span> <span data-ttu-id="bd759-138">Si no es así, el **activación** debe establecer la fecha en la fecha actual o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="bd759-138">If not, the **Activation** date must be set to the current date or earlier.</span></span>  
  
7.  <span data-ttu-id="bd759-139">Para enviar un intercambio por lotes cuando no se cumplen los criterios de versión, seleccione **invalidar**.</span><span class="sxs-lookup"><span data-stu-id="bd759-139">To send a batched interchange when the release criteria have not been met, select **Override**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd759-140">Seleccionar **invalidar** da como resultado un intercambio por lotes que se envían, pero no afecta el estado de activación de la instancia de orquestación de procesamiento por lotes, los criterios de activación y los criterios de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="bd759-140">Selecting **Override** results in a batched interchange being sent, but does not affect the activation status of the batching orchestration instance, the activation criteria, or the release criteria.</span></span>  
  
8.  <span data-ttu-id="bd759-141">Para desactivar la instancia de la orquestación por lotes, seleccione **detener**.</span><span class="sxs-lookup"><span data-stu-id="bd759-141">To deactivate the instance of the batching orchestration, select **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd759-142">Seleccionar **detener** da como resultado un intercambio por lotes que se envían y la instancia de orquestación de procesamiento por lotes está finalizando.</span><span class="sxs-lookup"><span data-stu-id="bd759-142">Selecting **Stop** results in a batched interchange being sent, and the batching orchestration instance being terminated.</span></span>  
  
9. <span data-ttu-id="bd759-143">Seleccione **Aceptar** o **cancelar** para cerrar el **propiedades de acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="bd759-143">Select **OK** or **Cancel** to close the **Agreement Properties**.</span></span>  

## <a name="delete-batches"></a><span data-ttu-id="bd759-144">Eliminar lotes</span><span class="sxs-lookup"><span data-stu-id="bd759-144">Delete batches</span></span>  
  
1.  <span data-ttu-id="bd759-145">En  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, seleccione **partes**.</span><span class="sxs-lookup"><span data-stu-id="bd759-145">In **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, select **Parties**.</span></span>  
  
2.  <span data-ttu-id="bd759-146">En el **entidades y perfiles empresariales** página, en la **contratos** sección, haga clic en el acuerdo con la configuración del lote que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="bd759-146">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to delete.</span></span>  
  
3.  <span data-ttu-id="bd759-147">En la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo, seleccione la **configuración de lote** página.</span><span class="sxs-lookup"><span data-stu-id="bd759-147">In the one-way agreement tab of the **Agreement Properties** dialog box, select the **Batch Configuration** page.</span></span>  
  
4.  <span data-ttu-id="bd759-148">En el **configuración de lote** , seleccione la pestaña del lote que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="bd759-148">On the **Batch Configuration** page, select the tab for the batch that you want to delete.</span></span>  
  
5.  <span data-ttu-id="bd759-149">En la esquina derecha de la ficha, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bd759-149">On the right-hand corner of the tab page, select **Delete**.</span></span>  
  
6.  <span data-ttu-id="bd759-150">Seleccione **Aceptar** para cerrar el **propiedades de acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="bd759-150">Select **OK** to close the **Agreement Properties**.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="bd759-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd759-151">See Also</span></span>  
 [<span data-ttu-id="bd759-152">Configurar un lote saliente</span><span class="sxs-lookup"><span data-stu-id="bd759-152">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
 [<span data-ttu-id="bd759-153">Administrar soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="bd759-153">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)