---
title: Configuración de sobres (configuración de conjunto de transacciones de X12) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 519062fa4647cdc2c7c39dda19373ff888eaf601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234340"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a><span data-ttu-id="796af-102">Configuración de sobres (configuración del conjunto de transacciones X12)</span><span class="sxs-lookup"><span data-stu-id="796af-102">Configuring Envelopes (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="796af-103">En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos GS y ST para un intercambio codificado en X12 que envía a la entidad.</span><span class="sxs-lookup"><span data-stu-id="796af-103">In the **Envelops** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS and ST segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="796af-104">El segmento GS identifica y especifica un grupo funcional para un intercambio con codificación X12.</span><span class="sxs-lookup"><span data-stu-id="796af-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span> <span data-ttu-id="796af-105">El segmento ST es el encabezado de mensaje para el intercambio con codificación X12.</span><span class="sxs-lookup"><span data-stu-id="796af-105">An ST segment is the message header for an X12-encoded interchange.</span></span>  
  
 <span data-ttu-id="796af-106">En esta página, asociar valores de la **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, y **GS8** elementos de datos con valores de la **tipo de transacción**, **versión**, y **destino espacio de nombres** elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="796af-106">In this page, you associate values of the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements with values of the **Transaction Type**, **Version/Release**, and **Target namespace** data elements.</span></span> <span data-ttu-id="796af-107">Cuando BizTalk determina que un mensaje XML de BizTalk contiene los valores establecidos para la **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos en una fila de la cuadrícula BizTalk rellenará el **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, y **GS8** elementos de datos en la envolvente de la salida del intercambio con los valores de la misma fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="796af-107">When BizTalk determines that a BizTalk XML message has the values set for the **Transaction Type**, **Version/Release**, and **Target namespace** elements in a row of the grid, BizTalk will populate the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements in the envelope of the outgoing interchange with the values from the same row of the grid.</span></span> <span data-ttu-id="796af-108">Los valores de la **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="796af-108">The values of the **Transaction Type**, **Version/Release**, and **Target namespace** elements must be unique.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="796af-109">Si especifica una configuración para algunos de los campos de la cuadrícula y luego la elimina, deberá eliminar la fila completa para evitar errores en la validación de la página.</span><span class="sxs-lookup"><span data-stu-id="796af-109">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="796af-110">Este tema se aplica también a valores de configuración relacionados con HIPAA.</span><span class="sxs-lookup"><span data-stu-id="796af-110">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="796af-111">Todas las propiedades están deshabilitadas en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** comprobar cuadro de entidad A. Sin embargo, todas las propiedades están habilitadas en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.</span><span class="sxs-lookup"><span data-stu-id="796af-111">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="796af-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="796af-112">Prerequisites</span></span>  
 <span data-ttu-id="796af-113">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="796af-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-and-st-segments"></a><span data-ttu-id="796af-114">Para definir los segmentos GS y ST</span><span class="sxs-lookup"><span data-stu-id="796af-114">To define the GS and ST segments</span></span>  
  
1.  <span data-ttu-id="796af-115">Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="796af-115">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="796af-116">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="796af-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="796af-117">En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **sobres**.</span><span class="sxs-lookup"><span data-stu-id="796af-117">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="796af-118">En una fila de la cuadrícula, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="796af-118">In a row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="796af-119">Para el **tipo de transacción** , a continuación, seleccione un valor para el conjunto de transacciones código de identificador de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="796af-119">For the **Transaction Type** field, select a value for the transaction set identifier code from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="796af-120">Para **versión**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 12 caracteres.</span><span class="sxs-lookup"><span data-stu-id="796af-120">For **Version/Release**, enter an alphanumeric value with a minimum of one character and a maximum of 12 characters.</span></span>  
  
    -   <span data-ttu-id="796af-121">Para **espacio de nombres de destino** elementos, seleccione un valor de la lista desplegable o escriba un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="796af-121">For **Target namespace** elements, select a value from the drop-down list, or enter a namespace.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="796af-122">Estos serán los valores que BizTalk Server compare con los valores asociados con el intercambio que se crea.</span><span class="sxs-lookup"><span data-stu-id="796af-122">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="796af-123">En la misma fila de la cuadrícula, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="796af-123">In the same row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="796af-124">Para **GS1**, seleccione un valor para el código funcional en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="796af-124">For **GS1**, select a value for the functional code from the drop-down list.</span></span> <span data-ttu-id="796af-125">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="796af-125">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="796af-126">Para **GS2**, escriba un valor alfanumérico para el remitente de aplicación con un mínimo de dos caracteres y un máximo de 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="796af-126">For **GS2**, enter an alphanumeric value for the application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="796af-127">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="796af-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="796af-128">Para **GS3**, escriba un valor alfanumérico para el receptor de aplicación con un mínimo de dos caracteres y un máximo de 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="796af-128">For **GS3**, enter an alphanumeric value for the application receiver with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="796af-129">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="796af-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="796af-130">Para **GS4**, seleccione **SSAAMMDD** o **AAMMDD**.</span><span class="sxs-lookup"><span data-stu-id="796af-130">For **GS4**, select **CCYYMMDD** or **YYMMDD**.</span></span> <span data-ttu-id="796af-131">Este campo es opcional</span><span class="sxs-lookup"><span data-stu-id="796af-131">This is an optional field</span></span>  
  
    -   <span data-ttu-id="796af-132">Para **GS5**, seleccione **HHMM**, **HHMMSS**, o **HHMMSSdd**.</span><span class="sxs-lookup"><span data-stu-id="796af-132">For **GS5**, select **HHMM**, **HHMMSS**, or **HHMMSSdd**.</span></span> <span data-ttu-id="796af-133">Este campo es opcional</span><span class="sxs-lookup"><span data-stu-id="796af-133">This is an optional field</span></span>  
  
    -   <span data-ttu-id="796af-134">Para **GS7**, seleccione un valor para la Agencia responsable de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="796af-134">For **GS7**, select a value for the responsible agency from the drop-down list.</span></span> <span data-ttu-id="796af-135">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="796af-135">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="796af-136">Para **GS8**, escriba un valor alfanumérico para el documento identificado con un carácter como mínimo y un máximo de 12 caracteres.</span><span class="sxs-lookup"><span data-stu-id="796af-136">For **GS8**, enter an alphanumeric value for the document identified with a minimum of one character and a maximum of 12 characters.</span></span> <span data-ttu-id="796af-137">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="796af-137">This is an optional field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="796af-138">Estos serán los valores que BizTalk Server especificará en los campos GS del intercambio que está construyendo si el **tipo de transacción**, **versión**, y **el espacio de nombres de destino**elementos en la misma fila son una coincidencia para los que estén asociados con el intercambio.</span><span class="sxs-lookup"><span data-stu-id="796af-138">These will be the values that BizTalk Server will enter in the GS fields of the interchange it is building if the **Transaction Type**, **Version/Release**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="796af-139">Repita los pasos 3 y 4 para especificar las filas adicionales en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="796af-139">Repeat steps 3 and 4 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="796af-140">Para una fila en la cuadrícula, haga clic en **predeterminado** para establecerla como la fila predeterminada.</span><span class="sxs-lookup"><span data-stu-id="796af-140">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="796af-141">Si un mensaje no tiene una coincidencia con el **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos en cualquier fila, BizTalk Server rellenará el mensaje con los valores de la **GS1**, **GS2**, **GS3**, **GS5**, **GS7**y **GS8** elementos en la fila predeterminada.</span><span class="sxs-lookup"><span data-stu-id="796af-141">If a message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **GS1**, **GS2**, **GS3**, **GS5**, **GS7**, and **GS8** elements in the default row.</span></span> <span data-ttu-id="796af-142">Estos valores se utilizarán incluso si el mensaje no tiene una coincidencia con el **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos de la fila predeterminada.</span><span class="sxs-lookup"><span data-stu-id="796af-142">These values will be used even if the message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="796af-143">Si no tiene valor predeterminado está seleccionados, los documentos entrantes que no coinciden con la **tipo de transacción**, **versión**, y **espacio de nombres de destino** se suspenderán los elementos de todas las filas .</span><span class="sxs-lookup"><span data-stu-id="796af-143">If no default is selected, incoming documents that do not match the **Transaction Type**, **Version/Release**, and **Target namespace** elements of any rows will be suspended.</span></span>  
  
7.  <span data-ttu-id="796af-144">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="796af-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796af-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="796af-145">See Also</span></span>  
 [<span data-ttu-id="796af-146">Configurar transacción configurar (X12)</span><span class="sxs-lookup"><span data-stu-id="796af-146">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)