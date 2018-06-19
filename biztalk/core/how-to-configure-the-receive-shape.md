---
title: Cómo configurar la forma recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e74220ab71c0efcc09e1736511e8388de71f387
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "25969514"
---
# <a name="how-to-configure-the-receive-shape"></a><span data-ttu-id="ec5fd-102">Cómo configurar la forma Recepción</span><span class="sxs-lookup"><span data-stu-id="ec5fd-102">How to Configure the Receive Shape</span></span>
<span data-ttu-id="ec5fd-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span><span class="sxs-lookup"><span data-stu-id="ec5fd-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span></span>  
<span data-ttu-id="ec5fd-104">Forma Recepción</span><span class="sxs-lookup"><span data-stu-id="ec5fd-104">Receive shape</span></span>  
  
 <span data-ttu-id="ec5fd-105">A **recepción** forma puede usarse para iniciar una orquestación.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-105">A **Receive** shape can be used to start an orchestration.</span></span> <span data-ttu-id="ec5fd-106">Si establece la **activar** propiedad **True**, el motor en tiempo de ejecución probará un mensaje entrante para ver si es del tipo adecuado y, si se ha aplicado un filtro, si es la expresión de filtro se cumplen.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-106">If you set the **Activate** property to **True**, the runtime engine will test an incoming message to see whether it is of the right type and, if a filter has been applied, whether the filter expression is satisfied.</span></span> <span data-ttu-id="ec5fd-107">Si se cumplen los criterios de recepción del mensaje, el motor en tiempo de ejecución crea y ejecuta una nueva instancia de orquestación y el **recepción** forma recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-107">If the criteria for receipt of the message are met, the runtime engine creates and runs a new orchestration instance, and the **Receive** shape receives the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5fd-108">Si el **activar** propiedad de una forma recepción está establecida en True, el **recepción** debe ser la primera acción de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-108">If the **Activate** property of a Receive shape is set to True, the **Receive** must be the first action in the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5fd-109">Si el **activar** propiedad está establecida en False en todos los **recepción** formas, la orquestación debe llamarse otra orquestación para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-109">If the **Activate** property is set to False on all **Receive** shapes, your orchestration must be called by another orchestration in order to run.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5fd-110">Si coloca un **recepción** forma dentro de un ámbito con el **activar** propiedad establecida en **True**y, a continuación, agregue una variable de clase .NET a la orquestación sin cambiar el la variable **utilizar Constructor predeterminado** propiedad **False**, la recepción de activación instrucción será fuera del ámbito en el código generado de XLANG/S, pero seguirá la superficie de diseño mostrando que está dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-110">If you put a **Receive** shape inside a scope with the **Activate** property set to **True**, and then add a .NET Class variable to your orchestration without changing the variable's **Use Default Constructor** property to **False**, the activate receive statement will be outside of the scope in the generated XLANG/S code, but the design surface will continue to show it as being inside the scope.</span></span>  
  
 <span data-ttu-id="ec5fd-111">Cada orquestación debe tener al menos un **recepción** forma con el **activar** propiedad establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-111">Each orchestration must have at least one **Receive** shape with the **Activate** property set to **True**.</span></span>  
  
 <span data-ttu-id="ec5fd-112">Si espera recibir una respuesta indirecta o asíncrona (sin utilizar un puerto de solicitud-respuesta) al mensaje que ha enviado previamente, tendrá que correlacionar el mensaje con la instancia de orquestación que se esté ejecutando en ese momento, para que el destinatario pueda obtener la respuesta en la instancia correcta.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-112">If you expect to receive an indirect or asynchronous response (not on a request-response port) to a message that you have previously sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="ec5fd-113">Puede aplicar un conjunto de correlaciones de inicialización a la forma Recepción si planea realizar correlaciones ulteriores con los valores del mensaje de entrada, o un conjunto de correlaciones siguiente para efectuar la correlación mediante un conjunto de correlaciones inicializado previamente.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-113">You can apply an initializing correlation set to the Receive shape if you plan to do subsequent correlation on values in the incoming message, or a following correlation set for correlating using a previously initialized correlation set.</span></span> <span data-ttu-id="ec5fd-114">Para obtener más información, consulte [usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-114">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-receive-shape"></a><span data-ttu-id="ec5fd-115">Para configurar una forma Recepción</span><span class="sxs-lookup"><span data-stu-id="ec5fd-115">To configure a Receive shape</span></span>  
  
1.  <span data-ttu-id="ec5fd-116">Establezca un mensaje y una operación de puerto.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-116">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="ec5fd-117">En la ventana Vista orquestación, compruebe que la orquestación tiene un mensaje y una operación de puerto definidos para el tipo de mensaje que se va a recibir.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-117">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the message type being received.</span></span>  
  
         <span data-ttu-id="ec5fd-118">En la ventana Propiedades, seleccione el mensaje para recibir desde el **mensaje** lista de propiedades de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-118">In the Properties window, select the message to receive from the **Message** property drop-down list.</span></span>  
  
    2.  <span data-ttu-id="ec5fd-119">En la ventana Propiedades, seleccione la operación de puerto para recibir el mensaje de la **operación** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-119">In the Properties window, select the port operation to receive the message from the **Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="ec5fd-120">: "O":</span><span class="sxs-lookup"><span data-stu-id="ec5fd-120">—Or—</span></span>  
  
         <span data-ttu-id="ec5fd-121">Arrastre el conector de recepción desde la **recepción** forma al socket del puerto que recibirá el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-121">Drag the receive connector from the **Receive** shape to the port socket that will receive the message.</span></span>  
  
2.  <span data-ttu-id="ec5fd-122">Especificar que la **recepción** forma activará la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-122">Specify that the **Receive** shape will activate the orchestration.</span></span>  
  
3.  <span data-ttu-id="ec5fd-123">En la ventana Propiedades, establezca la propiedad Activar en True.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-123">In the Properties window, set the Activate property to True.</span></span>  
  
    1.  <span data-ttu-id="ec5fd-124">En la ventana Propiedades, haga clic en el **puntos suspensivos** (**...** ) botón para la propiedad de expresión de filtro crear un filtro para restringir los mensajes que este **recepción** forma acepta.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-124">In the Properties window, click the **Ellipsis** (**...**) button for the Filter Expression property to create a filter to restrict the messages that this **Receive** shape accepts.</span></span>  
  
         <span data-ttu-id="ec5fd-125">: "O":</span><span class="sxs-lookup"><span data-stu-id="ec5fd-125">—Or—</span></span>  
  
         <span data-ttu-id="ec5fd-126">Haga clic en el **recepción** forma y, a continuación, haga clic en **editar la expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-126">Right-click the **Receive** shape and then click **Edit Filter Expression**.</span></span>  
  
    2.  <span data-ttu-id="ec5fd-127">El **expresión de filtro** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-127">The **Filter Expression** dialog box appears.</span></span> <span data-ttu-id="ec5fd-128">Use este cuadro de diálogo para crear una o varias expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-128">Use this dialog box to create one or more filter expressions.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ec5fd-129">Un tipo de mensaje debe definirse y asignarse a la **recepción** de forma que pueda aplicar un filtro a él.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-129">A message type must be defined and assigned to the **Receive** shape before you can apply a filter to it.</span></span>  
  
4.  <span data-ttu-id="ec5fd-130">Especificar conjuntos de correlaciones para restringir los mensajes la **recepción** forma acepta.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-130">Specify correlation sets to restrict the messages the **Receive** shape accepts.</span></span>  
  
    -   <span data-ttu-id="ec5fd-131">Para cada conjunto de correlaciones que desea que siga, marque un conjunto en la lista desplegable en el **siguiendo conjuntos de correlaciones** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-131">For each correlation set you want to follow, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    -   <span data-ttu-id="ec5fd-132">Para cada correlación del conjunto que desea inicializar, marque un conjunto en la lista desplegable en el **Inicializando conjuntos de correlaciones** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-132">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="filter-expression-grid-control"></a><span data-ttu-id="ec5fd-133">Control de cuadrícula de expresión de filtro</span><span class="sxs-lookup"><span data-stu-id="ec5fd-133">Filter Expression grid control</span></span>  
 <span data-ttu-id="ec5fd-134">Una expresión de filtro se genera usando este control de cuadrícula para definir los predicados que componen la expresión.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-134">You build a filter expression by using this grid control to define the predicates that make up the expression.</span></span> <span data-ttu-id="ec5fd-135">Puede agregar, editar y eliminar predicados de las celdas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-135">You can add, edit, and delete predicates from the cells of the grid.</span></span> <span data-ttu-id="ec5fd-136">Este control de cuadrícula tiene cuatro columnas: propiedad, operador, valor y agrupación.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-136">This grid control has four columns: Property, Operator, Value, and Grouping.</span></span>  
  
-   <span data-ttu-id="ec5fd-137">**propiedad.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-137">**Property.**</span></span> <span data-ttu-id="ec5fd-138">Puede escribir una referencia a una propiedad o seleccionar una en la lista desplegable de la celda.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-138">You can type a property reference, or select one from the cell's drop-down list.</span></span> <span data-ttu-id="ec5fd-139">La lista contiene las propiedades del mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-139">The list contains properties on the incoming message.</span></span>  
  
-   <span data-ttu-id="ec5fd-140">**operador.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-140">**Operator.**</span></span> <span data-ttu-id="ec5fd-141">Puede escribir en esta celda o seleccionar un operador en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-141">You can type in this cell, or select an operator from the drop-down list.</span></span> <span data-ttu-id="ec5fd-142">Los valores que puede seleccionar son:</span><span class="sxs-lookup"><span data-stu-id="ec5fd-142">Possible selections are:</span></span>  
  
    |<span data-ttu-id="ec5fd-143">Operando</span><span class="sxs-lookup"><span data-stu-id="ec5fd-143">Operand</span></span>|<span data-ttu-id="ec5fd-144">Significado</span><span class="sxs-lookup"><span data-stu-id="ec5fd-144">Meaning</span></span>|  
    |-------------|-------------|  
    |==|<span data-ttu-id="ec5fd-145">Es igual que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-145">Is equal to</span></span>|  
    |<span data-ttu-id="ec5fd-146">!=</span><span class="sxs-lookup"><span data-stu-id="ec5fd-146">!=</span></span>|<span data-ttu-id="ec5fd-147">No es igual que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-147">Is not equal to</span></span>|  
    |<|<span data-ttu-id="ec5fd-148">Es menor que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-148">Is less than</span></span>|  
    |\<=|<span data-ttu-id="ec5fd-149">Es menor o igual que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-149">Is less than or equal to</span></span>|  
    |>|<span data-ttu-id="ec5fd-150">Es mayor que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-150">Is greater than</span></span>|  
    |\>=|<span data-ttu-id="ec5fd-151">Es mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="ec5fd-151">Is greater than or equal to</span></span>|  
    |<span data-ttu-id="ec5fd-152">Exists</span><span class="sxs-lookup"><span data-stu-id="ec5fd-152">Exists</span></span>|<span data-ttu-id="ec5fd-153">Exists</span><span class="sxs-lookup"><span data-stu-id="ec5fd-153">Exists</span></span>|  
  
-   <span data-ttu-id="ec5fd-154">**Valor.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-154">**Value.**</span></span> <span data-ttu-id="ec5fd-155">Las celdas de la **valor** columna puede contener cualquier constante que se escribe en: un literal de cadena, un literal entero, o null.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-155">Cells in the **Value** column can hold any constant that you type in: a string-literal, an integer-literal, or null.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec5fd-156">Si la propiedad seleccionada es de cadena, el valor deberá consignarse entre comillas.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-156">If the property selected is of type string, the value needs to be in quotes.</span></span> <span data-ttu-id="ec5fd-157">Por ejemplo, SMTP.From = "MyServer".</span><span class="sxs-lookup"><span data-stu-id="ec5fd-157">For example, SMTP.From = "MyServer".</span></span>  
  
-   <span data-ttu-id="ec5fd-158">**La agrupación.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-158">**Grouping.**</span></span> <span data-ttu-id="ec5fd-159">Esta columna le permite controlar la agrupación de los predicados.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-159">Use this column to control predicate grouping.</span></span> <span data-ttu-id="ec5fd-160">Las expresiones de filtro siempre se expresan en la forma disyuntiva normal (DNF) de modo que la agrupación se pueda determinar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-160">Filter expressions are always expressed in Disjunctive Normal Form (DNF) so grouping can be determined automatically.</span></span> <span data-ttu-id="ec5fd-161">Y significa que el predicado se agrupará con el predicado siguiente, mientras que O supone que el predicado se separa del predicado de la siguiente fila.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-161">AND means the predicate is to be grouped with the predicate following it, while OR means the predicate is separate from the predicate in the next row.</span></span> <span data-ttu-id="ec5fd-162">Los corchetes de color gris a la izquierda del control de cuadrícula aparecen cuando se agrupan predicados.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-162">Gray brackets to the left of the grid control appear when predicates are grouped together.</span></span> <span data-ttu-id="ec5fd-163">Los grupos de predicados no se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-163">Predicate groups cannot be nested.</span></span> <span data-ttu-id="ec5fd-164">Si no especifica un valor en esta celda, se utilizará el valor predeterminado Y.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-164">If you do not specify a value in this cell, the value of the cell defaults to AND.</span></span>  
  
 <span data-ttu-id="ec5fd-165">Por ejemplo, podría crear una expresión similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5fd-165">For example, you might create an expression like the following:</span></span>  
  
 `MSMQ.MsgID = 1`  
  
 <span data-ttu-id="ec5fd-166">Con este filtro, el grupo de puertos de envío sólo se suscribirá a mensajes cuyo Id. de mensaje de MSMQ sea 1.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-166">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="ec5fd-167">Puede crear expresiones adicionales y especificar la existencia de una relación con AND u OR entre estas expresiones y otras; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ec5fd-167">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 `MSMQ.MsgID = 1 OR`  
  
 `SMTP.From = "MyServer"`  
  
 <span data-ttu-id="ec5fd-168">En este caso, el grupo de puertos de envío se suscribirá a todos los mensajes cuyo Id. de mensaje de MSMQ sea 1 o que se hayan enviado desde un servidor SMTP denominado MyServer.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-168">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
## <a name="hint-label"></a><span data-ttu-id="ec5fd-169">Etiqueta de sugerencia</span><span class="sxs-lookup"><span data-stu-id="ec5fd-169">Hint label</span></span>  
 <span data-ttu-id="ec5fd-170">Este campo proporciona directrices para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-170">This field provides user guidance.</span></span> <span data-ttu-id="ec5fd-171">El texto de la etiqueta cambia según cuál sea la columna que contiene la celda activa.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-171">The label text changes depending on which column contains the active cell.</span></span> <span data-ttu-id="ec5fd-172">El texto muestra el nombre de la columna, seguido por el texto con las directrices, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="ec5fd-172">The text displays the column name followed by guidance text as follows:</span></span>  
  
-   <span data-ttu-id="ec5fd-173">**propiedad.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-173">**Property.**</span></span> <span data-ttu-id="ec5fd-174">Please select a property on the incoming message from the list (Seleccione una propiedad del mensaje de entrada en la lista).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-174">Please select a property on the incoming message from the list.</span></span>  
  
-   <span data-ttu-id="ec5fd-175">**operador.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-175">**Operator.**</span></span> <span data-ttu-id="ec5fd-176">Select an operator to compare the Property with the Value (Seleccione un operador para comparar la propiedad con el valor).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-176">Select an operator to compare the Property with the Value.</span></span>  
  
-   <span data-ttu-id="ec5fd-177">**Valor.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-177">**Value.**</span></span> <span data-ttu-id="ec5fd-178">Select a message property from the list, or type in a literal value (Seleccione una propiedad de mensaje de la lista o escriba un valor literal).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-178">Select a message property from the list, or type in a literal value.</span></span>  
  
-   <span data-ttu-id="ec5fd-179">**La agrupación.**</span><span class="sxs-lookup"><span data-stu-id="ec5fd-179">**Grouping.**</span></span> <span data-ttu-id="ec5fd-180">Specify how this row is to be grouped with the next row (Especifique cómo se agrupará esta fila con la siguiente).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-180">Specify how this row is to be grouped with the next row.</span></span> <span data-ttu-id="ec5fd-181">'AND' will join the rows, and 'OR' will separate them ('Y' une las filas y 'O' las separa).</span><span class="sxs-lookup"><span data-stu-id="ec5fd-181">'AND' will join the rows, and 'OR' will separate them.</span></span>  
  
## <a name="move-up-button"></a><span data-ttu-id="ec5fd-182">Botón Subir</span><span class="sxs-lookup"><span data-stu-id="ec5fd-182">Move Up button</span></span>  
 <span data-ttu-id="ec5fd-183">Haga clic en él para mover hacia arriba la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-183">Click this to move a selected row up.</span></span> <span data-ttu-id="ec5fd-184">(Seleccione primero la fila haciendo clic en el *flecha derecha* (**>)** situado en el lado izquierdo del control de cuadrícula.)</span><span class="sxs-lookup"><span data-stu-id="ec5fd-184">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="move-down-button"></a><span data-ttu-id="ec5fd-185">Botón Bajar</span><span class="sxs-lookup"><span data-stu-id="ec5fd-185">Move Down button</span></span>  
 <span data-ttu-id="ec5fd-186">Haga clic en él para mover hacia abajo la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-186">Click this to move a selected row down.</span></span> <span data-ttu-id="ec5fd-187">(Seleccione primero la fila haciendo clic en el *flecha derecha* (**>)** situado en el lado izquierdo del control de cuadrícula.)</span><span class="sxs-lookup"><span data-stu-id="ec5fd-187">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="filter-expression-created-field"></a><span data-ttu-id="ec5fd-188">Campo Se ha creado una expresión de filtro</span><span class="sxs-lookup"><span data-stu-id="ec5fd-188">Filter Expression Created field</span></span>  
 <span data-ttu-id="ec5fd-189">Este cuadro de texto de solo lectura muestra la expresión a medida que la crea.</span><span class="sxs-lookup"><span data-stu-id="ec5fd-189">This read-only text box shows the expression as you are building it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec5fd-190">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ec5fd-190">In This Section</span></span>  
 [<span data-ttu-id="ec5fd-191">Uso de filtros con la forma Recibir mensaje</span><span class="sxs-lookup"><span data-stu-id="ec5fd-191">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)