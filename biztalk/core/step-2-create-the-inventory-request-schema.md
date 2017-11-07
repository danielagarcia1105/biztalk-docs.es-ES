---
title: 'Paso 2: Crear el esquema de solicitud de inventario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06000a734856c7b9f22e78a2d5a78c4585021a21
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a>Paso 2: Crear el esquema de solicitud de inventario
![Paso 2 de 5](../core/media/step-2of5.gif "Step_2of5")  
  
 **Tiempo en completarse:** 7 minutos  
  
 **Objetivo:** en este paso, se define el esquema del mensaje de reposición de inventario.  El sistema del almacén envía este mensaje para solicitar la reposición del inventario.  Es uno de los dos esquemas que debe crear para este proyecto.  
  
 **Propósito:** XML no solo las estructuras e identifica información con códigos de lenguaje de marcado normalizados, pero también tiene la capacidad de utilizar los esquemas. Un esquema es un documento XML que funciona como un diccionario y que otros documentos XML utilizan como referencia. El código del esquema define la ortografía de los elementos XML y el tipo de datos que esos elementos contienen. Los esquemas proporcionan una manera fácil para que un programa procese documentos XML y garantizan que la estructura y tipo de información son correctos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md).  
  
## <a name="procedures"></a>Procedimientos  
 En [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md), creó un nuevo [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto.  Si cierra la ventana de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede utilizar el siguiente procedimiento para abrir el proyecto.  En caso contrario, puede omitir el procedimiento "Abrir el proyecto de Visual Studio".  
  
#### <a name="to-open-the-visual-studio-project"></a>Abrir el proyecto de Visual Studio  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto/solución**.  
  
3.  En el **Abrir proyecto** cuadro de diálogo, vaya a la **C:\BTSTutorials\EAISolution\EAISolution.sln** archivo de solución y, a continuación, haga clic en **abiertos**.  
  
 En el siguiente procedimiento, agregará un nuevo archivo de esquema al proyecto para el mensaje de reposición del inventario.  
  
#### <a name="to-add-a-new-schema-to-the-project"></a>Para agregar un nuevo esquema al proyecto  
  
1.  En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Plantillas instaladas**|Haga clic en **archivos de esquema**, a continuación, haga clic en **esquema**.|  
    |**Nombre**|Tipo de **Request.xsd**.|  
  
3.  Haga clic en **Agregar**. Aparecerán el árbol de esquema y el panel de XSD. Esta parte de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se denomina Editor de BizTalk. Además, aparece el nuevo esquema en el Explorador de soluciones bajo el proyecto EAISchemas.  
  
     ![Diferentes partes del proyecto de BizTalk](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
#### <a name="to-add-elements-to-the-schema"></a>Agregar elementos al esquema  
  
1.  En el árbol de esquema, haga clic en el **raíz** nodo.  
  
2.  En el panel Propiedades, cambie el valor de la **nombre de nodo** propiedad `Request`, y, a continuación, presione ENTRAR.  
  
3.  En el árbol de esquema, haga clic en el **solicitar** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.  
  
4.  Tipo `Header` como el nuevo nombre para el registro secundario y, a continuación, presione ENTRAR.  
  
5.  Repita los pasos 3 y 4 para crear un segundo nodo secundario registro para el **solicitar** nodo y asígnele el nombre `Items`.  
  
6.  En el árbol de esquema, haga clic en el **encabezado** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.  
  
7.  Tipo `ReqID` como el nuevo nombre para el elemento y, a continuación, presione ENTRAR.  
  
8.  Elemento de campo Repita el paso 6 y 7 para crear un segundo nodo secundario para el **encabezado** nodo y asígnele el nombre `OrderDate`.

9.  Elemento de campo secundario Repita el paso 6 y 7 para crear una tercera para la **encabezado** nodo y asígnele el nombre `GrandTotal`.
  
10. En el árbol de esquema, haga clic en el **elementos** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.  
  
11. Tipo `Item` como el nuevo nombre para el registro secundario y, a continuación, presione ENTRAR.  
  
12. En el árbol de esquema, haga clic en el **elemento** nodo y agregue los elementos de campo secundarios siguientes:  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     El Request.xsd finalizado debería parecerse al de la siguiente ilustración.  
  
     ![El Explorador de soluciones con el esquema de solicitud](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")  
  
 Al agregar nodos a un esquema, el Editor de BizTalk proporciona un conjunto de valores predeterminado para las propiedades.  Debe configurarlos en función de los requisitos.  
  
#### <a name="to-configure-the-elements"></a>Configurar los elementos  
  
1.  En el árbol de esquema, haga clic en **OrderDate** para seleccionarlo.  
  
2.  En el panel Propiedades, cambie **tipo de datos** a **xs: DateTime**.  
  
3.  Repita los pasos 1 y 2 para configurar las siguientes propiedades:  
  
    |Elemento|Propiedad|Valor|  
    |-------------|--------------|-----------|  
    |**GrandTotal**|**Tipo de datos**|**Xs: decimal**|  
    |**Elemento**|**Número máximo de instancias**|**Sin enlazar**|  
    |**Elemento**|**Número mínimo de instancias**|**1**|  
    |**Cantidad**|**Tipo de datos**|**xs:unsignedInt**|  
  
 Un esquema puede tener muchos elementos, pero la aplicación puede necesitar que solo se utilicen algunos de ellos para el procesamiento de los datos. Para conservar los recursos del equipo, BizTalk Server no lee automáticamente todos los elementos de esquema. Si desea que BizTalk Server lea los datos de un elemento concreto, debe identificar ese elemento con el Editor de BizTalk para promocionar sus propiedades.  
  
 La orquestación que crearemos en [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md) estará basada en el campo GrandTotal para enrutar los mensajes.  En consecuencia, debemos promocionar el campo GrandTotal.  
  
#### <a name="to-promote-an-element"></a>Promocionar un elemento  
  
1.  En el árbol de esquema, haga clic en **GrandTotal**, seleccione **promover**y, a continuación, haga clic en **promociones rápidas**.  
  
2.  Haga clic en **Aceptar** para confirmar la adición de un esquema de propiedad.  
  
3.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha definido el esquema del mensaje para la reposición del inventario de almacén.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Debe definir el esquema del mensaje de declinación de la solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)   
 [Paso 3: Crear el esquema de declinación de solicitud](../core/step-3-create-the-request-decline-schema.md)   
 [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)   
 [Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md)   
 [Crear esquemas con el Editor de BizTalk](../core/creating-schemas-using-biztalk-editor.md)   
 [Propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)
