---
title: "Cómo configurar la forma recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3868384641e4c5fa03c82c7ec4ba18e3ee9fb1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-receive-shape"></a>Cómo configurar la forma Recepción
![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")  
Forma Recepción  
  
 A **recepción** forma puede usarse para iniciar una orquestación. Si establece la **activar** propiedad **True**, el motor en tiempo de ejecución probará un mensaje entrante para ver si es del tipo adecuado y, si se ha aplicado un filtro, si es la expresión de filtro se cumplen. Si se cumplen los criterios de recepción del mensaje, el motor en tiempo de ejecución crea y ejecuta una nueva instancia de orquestación y el **recepción** forma recibe el mensaje.  
  
> [!NOTE]
>  Si el **activar** propiedad de una forma recepción está establecida en True, el **recepción** debe ser la primera acción de la orquestación.  
  
> [!NOTE]
>  Si el **activar** propiedad está establecida en False en todos los **recepción** formas, la orquestación debe llamarse otra orquestación para poder ejecutarse.  
  
> [!NOTE]
>  Si coloca un **recepción** forma dentro de un ámbito con el **activar** propiedad establecida en **True**y, a continuación, agregue una variable de clase .NET a la orquestación sin cambiar el la variable **utilizar Constructor predeterminado** propiedad **False**, la recepción de activación instrucción será fuera del ámbito en el código generado de XLANG/S, pero seguirá la superficie de diseño mostrando que está dentro del ámbito.  
  
 Cada orquestación debe tener al menos un **recepción** forma con el **activar** propiedad establecida en **True**.  
  
 Si espera recibir una respuesta indirecta o asíncrona (sin utilizar un puerto de solicitud-respuesta) al mensaje que ha enviado previamente, tendrá que correlacionar el mensaje con la instancia de orquestación que se esté ejecutando en ese momento, para que el destinatario pueda obtener la respuesta en la instancia correcta. Puede aplicar un conjunto de correlaciones de inicialización a la forma Recepción si planea realizar correlaciones ulteriores con los valores del mensaje de entrada, o un conjunto de correlaciones siguiente para efectuar la correlación mediante un conjunto de correlaciones inicializado previamente. Para obtener más información, consulte [usar correlaciones en orquestaciones](../core/using-correlations-in-orchestrations.md).  
  
### <a name="to-configure-a-receive-shape"></a>Para configurar una forma Recepción  
  
1.  Establezca un mensaje y una operación de puerto.  
  
    1.  En la ventana Vista orquestación, compruebe que la orquestación tiene un mensaje y una operación de puerto definidos para el tipo de mensaje que se va a recibir.  
  
         En la ventana Propiedades, seleccione el mensaje para recibir desde el **mensaje** lista de propiedades de lista desplegable.  
  
    2.  En la ventana Propiedades, seleccione la operación de puerto para recibir el mensaje de la **operación** lista desplegable.  
  
         : "O":  
  
         Arrastre el conector de recepción desde la **recepción** forma al socket del puerto que recibirá el mensaje.  
  
2.  Especificar que la **recepción** forma activará la orquestación.  
  
3.  En la ventana Propiedades, establezca la propiedad Activar en True.  
  
    1.  En la ventana Propiedades, haga clic en el **puntos suspensivos** (**...** ) botón para la propiedad de expresión de filtro crear un filtro para restringir los mensajes que este **recepción** forma acepta.  
  
         : "O":  
  
         Haga clic en el **recepción** forma y, a continuación, haga clic en **editar la expresión de filtro**.  
  
    2.  El **expresión de filtro** aparece el cuadro de diálogo. Use este cuadro de diálogo para crear una o varias expresiones de filtro.  
  
        > [!NOTE]
        >  Un tipo de mensaje debe definirse y asignarse a la **recepción** de forma que pueda aplicar un filtro a él.  
  
4.  Especificar conjuntos de correlaciones para restringir los mensajes la **recepción** forma acepta.  
  
    -   Para cada conjunto de correlaciones que desea que siga, marque un conjunto en la lista desplegable en el **siguiendo conjuntos de correlaciones** propiedad.  
  
    -   Para cada correlación del conjunto que desea inicializar, marque un conjunto en la lista desplegable en el **Inicializando conjuntos de correlaciones** propiedad.  
  
## <a name="filter-expression-grid-control"></a>Control de cuadrícula de expresión de filtro  
 Una expresión de filtro se genera usando este control de cuadrícula para definir los predicados que componen la expresión. Puede agregar, editar y eliminar predicados de las celdas de la cuadrícula. Este control de cuadrícula tiene cuatro columnas: propiedad, operador, valor y agrupación.  
  
-   **Propiedad.** Puede escribir una referencia a una propiedad o seleccionar una en la lista desplegable de la celda. La lista contiene las propiedades del mensaje de entrada.  
  
-   **Operador.** Puede escribir en esta celda o seleccionar un operador en la lista desplegable. Los valores que puede seleccionar son:  
  
    |Operando|Significado|  
    |-------------|-------------|  
    |==|Es igual que|  
    |!=|No es igual que|  
    |<|Es menor que|  
    |\<=|Es menor o igual que|  
    |>|Es mayor que|  
    |>=|Es mayor o igual que|  
    |Exists|Exists|  
  
-   **Valor.** Las celdas de la **valor** columna puede contener cualquier constante que se escribe en: un literal de cadena, un literal entero, o null.  
  
    > [!NOTE]
    >  Si la propiedad seleccionada es de cadena, el valor deberá consignarse entre comillas. Por ejemplo, SMTP.From = "MyServer".  
  
-   **La agrupación.** Esta columna le permite controlar la agrupación de los predicados. Las expresiones de filtro siempre se expresan en la forma disyuntiva normal (DNF) de modo que la agrupación se pueda determinar automáticamente. Y significa que el predicado se agrupará con el predicado siguiente, mientras que O supone que el predicado se separa del predicado de la siguiente fila. Los corchetes de color gris a la izquierda del control de cuadrícula aparecen cuando se agrupan predicados. Los grupos de predicados no se pueden anidar. Si no especifica un valor en esta celda, se utilizará el valor predeterminado Y.  
  
 Por ejemplo, podría crear una expresión similar a lo siguiente:  
  
 `MSMQ.MsgID = 1`  
  
 Con este filtro, el grupo de puertos de envío sólo se suscribirá a mensajes cuyo Id. de mensaje de MSMQ sea 1.  
  
 Puede crear expresiones adicionales y especificar la existencia de una relación con AND u OR entre estas expresiones y otras; por ejemplo:  
  
 `MSMQ.MsgID = 1 OR`  
  
 `SMTP.From = "MyServer"`  
  
 En este caso, el grupo de puertos de envío se suscribirá a todos los mensajes cuyo Id. de mensaje de MSMQ sea 1 o que se hayan enviado desde un servidor SMTP denominado MyServer.  
  
## <a name="hint-label"></a>Etiqueta de sugerencia  
 Este campo proporciona directrices para el usuario. El texto de la etiqueta cambia según cuál sea la columna que contiene la celda activa. El texto muestra el nombre de la columna, seguido por el texto con las directrices, como se muestra a continuación:  
  
-   **Propiedad.** Please select a property on the incoming message from the list (Seleccione una propiedad del mensaje de entrada en la lista).  
  
-   **Operador.** Select an operator to compare the Property with the Value (Seleccione un operador para comparar la propiedad con el valor).  
  
-   **Valor.** Select a message property from the list, or type in a literal value (Seleccione una propiedad de mensaje de la lista o escriba un valor literal).  
  
-   **La agrupación.** Specify how this row is to be grouped with the next row (Especifique cómo se agrupará esta fila con la siguiente). 'AND' will join the rows, and 'OR' will separate them ('Y' une las filas y 'O' las separa).  
  
## <a name="move-up-button"></a>Botón Subir  
 Haga clic en él para mover hacia arriba la fila seleccionada. (Seleccione primero la fila haciendo clic en el *flecha derecha* (**>)** situado en el lado izquierdo del control de cuadrícula.)  
  
## <a name="move-down-button"></a>Botón Bajar  
 Haga clic en él para mover hacia abajo la fila seleccionada. (Seleccione primero la fila haciendo clic en el *flecha derecha* (**>)** situado en el lado izquierdo del control de cuadrícula.)  
  
## <a name="filter-expression-created-field"></a>Campo Se ha creado una expresión de filtro  
 Este cuadro de texto de solo lectura muestra la expresión a medida que la crea.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso de filtros con la forma de mensaje de recepción](../core/using-filters-with-the-receive-message-shape.md)