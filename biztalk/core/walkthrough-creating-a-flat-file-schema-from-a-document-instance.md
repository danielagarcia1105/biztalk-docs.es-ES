---
title: 'Tutorial: Crear un esquema de archivo sin formato desde una instancia de documento | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e1453f-0380-4505-97a9-9d3526db0923
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa79ea6784df39bb2f06b32b289837093a04919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983429"
---
# <a name="walkthrough-creating-a-flat-file-schema-from-a-document-instance"></a>Tutorial: Crear un esquema de archivo sin formato desde una instancia de documento
Este tutorial muestra cómo crear un esquema de archivo sin formato a partir de una instancia de documento mediante el Asistente para esquemas de archivos sin formato de BizTalk tomando como base el pedido de muestra siguiente. Para obtener una introducción al Asistente para esquema de planos archivos BizTalk, consulte [cómo usar BizTalk esquema Asistente para archivos planos](../core/how-to-use-biztalk-flat-file-schema-wizard.md).  

 ![Pedido de compra de ejemplo](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")  

 Todas las líneas del pedido terminan con un avance de línea de retorno de carro (CRLF), marcado en verde. El pedido comienza con una etiqueta de pedido (PO) de color rojo, seguida de una fecha. Dos campos posicionales fijos de repetición contienen información de cliente y se muestran en púrpura. Después del campo de comentario, hay un campo de repetición a partir de una etiqueta ITEMS que contiene varios registros delimitados por comas (,) y los valores de datos separados por barras verticales (&#124;), que se muestran en azul.  

## <a name="prerequisites"></a>Requisitos previos  
 Antes de seguir este tutorial, asegúrese de que el software siguiente se encuentre instalado y configurado en el servidor:  

- Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el **herramientas de desarrollo** instalado

  Para preparar la instancia de documento para el tutorial, copie lo siguiente en un editor de texto y guárdelo como un archivo de texto. Asegúrese de copiar todas las líneas fuentes de distribución y retornos de carro.  

```
PO1999-10-20
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952
US        Robert Smith        8 Oak Avenue        Old Town       PA 95819
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric
```


## <a name="start-the-wizard"></a>Iniciar el asistente  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **el Explorador de soluciones**.  

2. Para agregar el nuevo esquema de archivo sin formato, haga clic en el proyecto y seleccione **agregar**. Haga clic en **nuevo elemento**.  

3. En el **Agregar nuevo elemento** ventana, haga lo siguiente:  

   1.  En el **categorías** sección, seleccione **archivos de esquema**.  

   2.  En el **plantillas** sección, seleccione **Asistente para esquemas de archivo sin formato**.  

   3.  En el **nombre** , introduzca **PurchaseOrder.xsd** para el nuevo esquema.  

   4.  Haga clic en **Agregar**.  

4. Cuando se abre el Asistente para esquemas de archivos sin formato de BizTalk, aparece la página de bienvenida.   
   Para omitir esta pantalla al ejecutar el Asistente en el futuro, seleccione el **no volver a mostrar esta página de introducción** cuadro. Para continuar, haga clic en **Siguiente** .  

## <a name="selecting-purchase-order-instance"></a>Selección de instancia de pedido de compra  

-   En el **información de esquema de archivo sin formato** pantalla, seleccione la instancia y escriba la siguiente información. Cuando haya terminado, haga clic en **siguiente** para continuar.  

    -   **Archivo de instancia:** haga clic en el **examinar** botón para buscar el archivo sin formato desde el que se generará el esquema. Vaya a la carpeta que contiene el archivo de texto que creó en la sección de requisitos previos del tutorial: crear una instancia sin formato archivo esquema desde un documento.  

    -   **Nombre del registro:** tipo **PO** ya que será el nombre de raíz de esquema.  

    -   **Espacio de nombres de destino:** tipo **http://Flat_File_Project.PurchaseOrder** para el espacio de nombres de destino de esquema.  

    -   **Página de códigos:** seleccione **UTF-8 (65001)** en la lista de selección desplegable.  

    -   **Contar posiciones en bytes:** Active esta casilla si desea contar los campos de datos posicionales por bytes. De forma predeterminada, los campos de datos posicionales se cuentan en caracteres. En este tutorial, deje el **contar posiciones en bytes** casilla desactivada.  

## <a name="select-purchase-order-data"></a>Seleccionar datos del pedido  

-   En el **seleccionar datos del documento** se muestra la pantalla, el contenido del archivo plano. Seleccione los datos necesarios para crear el esquema y, a continuación, haga clic en **siguiente**.  

    > [!NOTE]
    >  Si desea usar la instancia de todo el documento, puede presionar **CTRL+a** para seleccionar todo.  

    > [!NOTE]
    >  Comprobar **ajustar líneas largas** cuadro si desea ver el contenido de la instancia de todo el documento ajustado en el cuadro de edición en todo el asistente.  

    > [!NOTE]
    >  Si crea el esquema a partir de una instancia de intercambio, seleccione únicamente la parte que representa la estructura del documento individual.  

## <a name="delimit-purchase-order-record"></a>Delimitar el registro de pedido de compra  

-   Como todas las líneas del pedido terminan con un retorno de carro de avance de línea (CRLF), seleccione **por símbolo delimitador**y, a continuación, haga clic en **siguiente** en **Seleccionar formato de registro** pantalla.  

## <a name="specify-purchase-order-record-property"></a>Especifique la propiedad de registros de pedido de compra  

- En el **registro delimitado** pantalla, escriba lo siguiente para definir el primer nivel del esquema y cuando haya terminado, haga clic en **siguiente**.  

  - **Delimitador secundario:** seleccione **{CR} {LF}**.  

    > [!NOTE]
    >  **Delimitador secundario** propiedad es un cuadro editable con lista de selección desplegable contiene un conjunto de valores predeterminados. El **delimitador secundario** puede especificarse como un carácter o como un valor hexadecimal. Por ejemplo,  **\\{** o **{0x0D0A}**.  

  - **Carácter de escape:** un carácter de escape es un carácter individual que suprime cualquier significado especial del carácter que le sigue. Consulte [caracteres de Escape](../core/escape-characters.md) para obtener más información. Déjelo en blanco para este tutorial.  

    > [!NOTE]
    >  Cuando se usa **\\**, **{,** y **}** para **delimitador secundario** o **carácter de Escape**, un debe utilizarse la barra diagonal inversa. Por ejemplo,  **\\ \\,** y  **\\{**.  

  - Comprobar **registro tiene un identificador de etiquetas** cuadro y escriba **PO** en **etiqueta**. En un archivo de varios registros, **PO** se usará para identificar cada registro individual. Para continuar, haga clic en **Siguiente** .  

    ![Pantalla de registro delimitado](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")  

## <a name="define-the-element-in-the-purchase-order-record"></a>Definir el elemento en el registro de pedido de compra  

1.  El Asistente ha identificado cuatro elementos en el registro del pedido; ahora, tendrá que definir la propiedad del elemento. En la primera fila, lleve a cabo lo que se indica a continuación:  

    1.  Tipo **fecha** para el **nombre del elemento**.  

    2.  Seleccione **elemento de campo** para **tipo de elemento**.  

    3.  Seleccione **fecha** en la lista de selección desplegable para **tipo de datos**.  

2.  Repita los pasos del a al c para los siguientes elementos. Cuando haya terminado, haga clic en **siguiente**.  

    |Nombre de elemento|Tipo de elemento|Tipo de datos|  
    |------------------|------------------|---------------|  
    |**cliente**|**Repitiendo registro**||  
    ||**Pasar por alto**||  
    |**elementos**|**Registro**||  

     ![Pantalla elementos secundarios](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")  

    > [!NOTE]
    >  Puede seleccionar varias filas y, a continuación, cambiar su **tipo de elemento** a un tipo único mediante el mouse y la tecla MAYÚS o CTRL.  

    > [!NOTE]
    >  Tras hacer clic en **siguiente** en el **elementos secundarios** pantalla, no podrá hacer clic en **volver** para redefinir o efectuar cambios en los elementos secundarios. Es posible que tenga que cerrar el Asistente e iniciarlo nuevamente para definir el esquema de archivo sin formato.  

3.  Después de completar los pasos de este procedimiento, el primer nivel del esquema se genera tal y como se muestra en la siguiente captura de pantalla. Se definen tres elementos únicos y el usuario seguirá efectuando una definición adicional de los registros secundarios para los elementos del registro del pedido. Haga clic en **Siguiente**.  

     ![Pantalla de ejemplo de esquema](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")  

## <a name="define-the-customer-record"></a>Definir el registro de cliente  

1.  Dado que hemos definido la **cliente** elemento como el **repitiendo registro** tipo y el **elementos** elemento como el **registro** escriba BizTalk Asistente para esquemas de archivo sin formato continúa ahora definiendo estos dos elementos. En el **vista esquema** pantalla, seleccione **cliente**y, a continuación, haga clic en **siguiente** para continuar.  

2.  Para trabajar con el registro del cliente, tendrá que seleccionar los datos que representan ese elemento. Ya que se trata de un registro de repetición, cualquiera de las líneas puede utilizarse para definir el registro. Seleccione la primera línea de los datos del cliente y haga clic en **siguiente** para continuar.  

3.  En el **Seleccionar formato de registro** , seleccione **por posiciones relativas**y, a continuación, haga clic en **siguiente**.  

4.  El Asistente proporciona una herramienta visual para mostrar y calcular la distancia entre los campos. En el **registro posicional** , utilice el botón primario del mouse para hacer clic en el marcador de posición 10 a representar donde comienza el campo de nombre. Haga clic en los marcadores de posición siguientes para representar el resto de los campos de datos:  

    |Nombre de campo|Marcador de posición|  
    |----------------|---------------------|  
    |street|30|  
    |city|50|  
    |state|65|  
    |postalcode|68|  

     Para continuar, haga clic en **Siguiente** .  

     ![Pantalla de registro posicional](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")  

5.  En el **elementos secundarios** página, especifique las propiedades de los elementos secundarios. Seleccione la primera fila y escriba **país** como el **nombre del elemento**. En las otras columnas, deje los valores predeterminados. Escriba los siguientes valores para las demás propiedades para el **nombre del elemento**:  

    |Nombre de elemento|Valor|  
    |------------------|-----------|  
    |**customer_Child2**|**fullName**|  
    |**customer_Child3**|**Calle**|  
    |**customer_Child4**|**Ciudad**|  
    |**customer_Child5**|**state**|  
    |**customer_Child6**|**código postal**|  

     Para continuar, haga clic en **Siguiente** .  

     ![Pantalla elementos secundarios](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")  

6.  Los elementos secundarios del registro del cliente se crean tal y como se muestra en la siguiente captura de pantalla. Haga clic en **siguiente** para definir los elementos secundarios del registro items.  

     ![Pantalla de ejemplo de esquema](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")  

#### <a name="define-the-items-record"></a>Definir el registro de elementos  

1. En el **vista esquema** página, seleccione **elementos**y, a continuación, haga clic en **siguiente**.  

2. En el **seleccionar datos del documento** página, seleccione toda la línea comienza con ITEMS y, a continuación, haga clic en **siguiente** para definir sus elementos secundarios.  

3. En el **Seleccionar formato de registro** , seleccione **por símbolo delimitador**y, a continuación, haga clic en **siguiente**.  

4. En el registro de elementos, las comas se utilizan para delimitar los elementos individuales. Por lo tanto, en el **registro delimitado** , escriba lo siguiente para definir el registro de elementos. Cuando haya terminado, haga clic en **siguiente**.  

   -   Seleccione **,** desde **delimitador secundario** lista de selección desplegable.  

   -   Deje el **carácter de Escape** cuadro de texto en blanco.  

   -   Seleccione **registro tiene un identificador de etiquetas** y tipo **elementos** en **etiqueta**.  

        En un registro de varios elementos, **elementos** se usa para identificar cada registro individual.  

5. Con los valores de la **registro delimitado** página, el asistente identifica dos elementos secundarios. Dado que uno de ellos es un registro de repetición, seleccione el primer elemento y escriba **elemento** para el nombre de elemento y, a continuación, seleccione **registro repetido** en la lista desplegable de la lista de selección de **tipo de elemento** . Deje el resto de los valores predeterminados de las columnas. Seleccione la segunda fila y seleccione el **omitir** desde **tipo de elemento** lista. Al hacer clic en **siguiente**, se crea el siguiente nivel para el registro de elementos en el esquema. Continuará definiendo la última parte del esquema de pedido.  

6. Seleccione **elemento** y, a continuación, haga clic en **siguiente** para continuar en la **vista esquema** página.  

7. En el **seleccionar datos del documento** , seleccione **ITEM872-AA&#124;Lawnmower&#124;1&#124;148.95&#124;confirmar trata electric**. Para continuar, haga clic en **Siguiente** .  

8. En el **Seleccionar formato de registro** , seleccione el **por símbolo delimitador** opción porque el elemento individual está delimitado por una barra vertical (&#124;).  

9. En el **registro delimitado** , escriba lo siguiente para definir el registro del elemento. Cuando haya terminado, haga clic en **siguiente**.  

    -   Seleccione **&#124;** desde el **delimitador secundario** lista de selección desplegable.  

    -   Deje el **carácter de Escape** cuadro de texto en blanco.  

10. En el **elementos secundarios** página, el asistente ha identificado cinco elementos secundarios. Seleccione la primera fila y escriba **productCode** para **nombre del elemento**. Deje los valores predeterminados en el resto de las columnas. Para el resto de la **propiedades de nombre de elemento**, escriba lo siguiente:  

    |Nombre de elemento|Valor|  
    |------------------|-----------|  
    |**item_Child2**|**Descripción**|  
    |**item_Child3**|**Cantidad**|  
    |**item_Child4**|**precio por unidad**|  
    |**item_Child5**|**Notas de la**|  

     Para continuar, haga clic en **Siguiente** .  

11. Ha definido todos los nodos del esquema de pedido. En el **vista esquema** página, haga clic en **finalizar**.  

12. Ahora, podrá ver el esquema de pedido final. También puede refinar el esquema mediante el Editor de esquemas de BizTalk. Consulte la tabla de nombres de propiedad de archivo sin formato y las tablas de propiedades en **propiedades del nodo esquema**. Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="summary"></a>Resumen  
 En este tutorial, ha aprendido a utilizar el Asistente para esquemas de archivos sin formato de BizTalk para crear un esquema de archivo sin formato a partir de una instancia de documento.  

## <a name="next-steps"></a>Pasos siguientes  

### <a name="validate-po-instance"></a>Validar instancia de pedido de compra  
 Para asegurarse de que el esquema PurchaseOrder.xsd puede analizar correctamente la instancia de pedido, lleve a cabo lo que se indica a continuación:  

1.  En el Explorador de soluciones, haga clic en el **PurchaseOrder.xsd** y, a continuación, seleccione **propiedades**.  

2.  En el **páginas de propiedades**, asegúrese de que el **nombre de archivo de instancia de entrada** campo apunta a la ubicación de la instancia de pedido de compra que creó en la sección de requisitos previos del tutorial: crear un archivo plano Esquema de una instancia de documento. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  

3.  En el Explorador de soluciones, haga clic en **PurchaseOrder.xsd**y, a continuación, seleccione **Validar instancia**. Se abrirá el componente de validación.  

4.  Una vez completada la validación, se proporcionará un vínculo para ver el resultado XML basado en el resultado del análisis de la instancia de pedido mediante el esquema PurchaseOrder.xsd. Para ver el resultado XML, presione Ctrl y haga clic en el vínculo.  

### <a name="create-pipelines-for-the-schema"></a>Creación de canalizaciones para el esquema  
 Ahora, puede crear una canalización de envío o de recepción basada en el esquema PurchaseOrder.xsd para que se utilice con la aplicación de BizTalk.  

 Para crear una nueva canalización, consulte [cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md). Para configurar los componentes de canalización de archivo sin formato, consulte [cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) y [cómo configurar el componente de canalización de desensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md).  

## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para esquemas de archivo sin formato de BizTalk](../core/how-to-use-biztalk-flat-file-schema-wizard.md)   
 [Creación de esquemas con el Asistente para esquemas de archivo sin formato de BizTalk](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)