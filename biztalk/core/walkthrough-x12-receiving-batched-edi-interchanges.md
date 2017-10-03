---
title: "Tutorial (X12): Recepción por lotes de intercambios EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f6e6e96-39ec-469d-a845-1bfdce6cc0bf
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94d1aa31a271f0ed88be42066abdae25be3f3e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-x12-receiving-batched-edi-interchanges"></a>Tutorial (X12): Recibir intercambios EDI por lotes
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para recibir lotes de EDI mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta solución muestra dos formas de recibir un intercambio EDI por lotes:  
  
-   Dividiendo el lote en los conjuntos de transacciones que lo componen.  
  
-   Conservando el intercambio procesando el intercambio como un único documento sin dividir los conjuntos de transacciones.  
  
 Estos tutoriales demuestran cómo configurar los lotes de división y conservación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="how-the-solution-splits-received-edi-batches"></a>Cómo la solución divide los lotes de EDI recibidos  
 Cuando configura la solución para dividir el intercambio por lotes en conjuntos de transacciones que lo componen, la solución realizará lo siguiente:  
  
1.  La ubicación de recepción recibe un intercambio EDI por lotes que contiene varios conjuntos de transacciones de una entidad.  
  
    > [!NOTE]
    >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
2.  La canalización de recepción divide el intercambio recibido en los conjuntos de transacciones que lo compone y convierte los conjuntos de transacciones en formato XML interno.  
  
3.  La canalización de recepción promociona todo el intercambio y los encabezados de grupo al contexto de cada división del conjunto de transacciones del intercambio. También promociona determinados encabezados de grupo y de intercambio específicos, como ISA6, GS1 y GS2, de forma que estos campos pueden usarse para el enrutamiento.   
  
4.  La canalización de recepción coloca cada archivo XML de conjunto de transacciones en el cuadro de mensajes.  
  
    > [!NOTE]
    >  En esta solución, el lote contiene varias instancias del mismo tipo de mensaje.  
  
5.  El puerto de envío recoge cada transacción mediante la suscripción a una propiedad de contexto apropiada.  
  
6.  La canalización de envío genera cada conjunto de transacciones en un intercambio EDI y, a continuación, envía el intercambio al destino.  
  
    > [!NOTE]
    >  Para obtener más información acerca de cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] divide los conjuntos de transacciones en un lote, consulte [dividir un intercambio de EDI por lotes](../core/splitting-a-batched-edi-interchange.md).  
  
 La siguiente figura muestra el flujo de mensajes y arquitectura de la solución cuando se configura para dividir los conjuntos de transacciones en el intercambio por lotes.  
  
 ![Intercambios EDI por lotes de división](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")  
  
## <a name="how-the-solution-preserves-received-edi-batches"></a>Cómo la solución conserva los lotes de EDI recibidos  
 Cuando configura la solución para conservar el intercambio por lotes, la solución realizará lo siguiente:  
  
1.  La ubicación de recepción recibe un intercambio EDI por lotes que contiene varios conjuntos de transacciones de la entidad.  
  
2.  El proceso de canalización procesa el intercambio sin dividir los conjuntos de transacciones, convierte los dos conjuntos de transacciones en una unidad al formato XML interno.  
  
3.  La canalización de recepción promociona las mismas propiedades como si el intercambio no fuese un lote, con la excepción de que se aplicará una etiqueta reservada al XML que genera la canalización. Esta etiqueta es \<X12InterchangeXml > para un intercambio EDI con codificación X12 o \<EdifactInterchangeXml > para un intercambio EDI con codificación EDIFACT. La canalización de recepción EDI también se aplica a la propiedad de contexto `ReuseEnvelope` para identificar el intercambio como conservado.  
  
    > [!NOTE]
    >  La canalización de envío EDI usa el \<X12InterchangeXml > o \<EdifactInterchangeXml > etiqueta para identificar el mensaje como un lote conservado. La propiedad de contexto `ReuseEnvelope` permite crear un puerto de envío que se suscribe a todos los intercambios por lotes que se hayan conservado.  
  
4.  La canalización de recepción coloca el archivo XML del mensaje en el cuadro de mensajes.  
  
5.  El puerto de envío recoge el intercambio mediante la suscripción a una propiedad de contexto apropiada.  
  
6.  La canalización de envío genera los dos conjuntos de transacciones en el archivo XML en un intercambio EDI por lotes y, a continuación, envía el intercambio al destino.  
  
    > [!NOTE]
    >  Para obtener más información acerca de cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa un lote conservado, vea [conserva un recibido intercambio EDI por lotes](../core/preserving-a-received-batched-edi-interchange.md).  
  
## <a name="functionality-in-this-solution"></a>Funcionalidad en esta solución  
 Por lo que respecta a este tutorial, se habilitará la siguiente funcionalidad:  
  
-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  
  
    > [!NOTE]
    >  La configuración que se usa para la codificación EDIFACT e HIPAA es bastante parecida a la que usa la codificación X12.  
  
-   Las confirmaciones funcionales o técnicas no se devolverán en respuesta al intercambio que se recibió originalmente o a cualquier intercambio por lotes que se enviase.  
  
    > [!NOTE]
    >  Para obtener información acerca de cómo generar confirmaciones EDI, vea [tutorial (X12): envío y recepción de intercambios EDI hacer la copia de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).  
  
-   Esta solución usa un puerto unidireccional y un puerto de envío unidireccional estático. Estos puertos se configurarán con el tipo de transporte de archivo.  
  
-   Se habilitarán los informes EDI.  
  
-   Los conjuntos de transacciones se guardarán para su visualización desde el informe de estado de intercambio.  
  
-   Para realizar pruebas, la solución utiliza un puerto de envío para enviar los intercambios divididos o lotes conservados a una carpeta local.  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
-   Agregar los esquemas de mensaje necesarios a un proyecto de BizTalk y, a continuación, genere e implemente el proyecto, de modo que los esquemas estén disponibles para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los utilice a la hora de procesar los mensajes.  
  
-   Cree un puerto de recepción para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el mensaje EDI de entrada por lotes .txt con codificación X12 desde una entidad.  
  
-   Cree un puerto de envío para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cree un intercambio de los conjuntos de transacciones recibidas en el lote (si se divide el lote) o generar un intercambio único a partir de los conjuntos de transacciones en el lote recibido (si se conserva el lote). El puerto de envío, a continuación, envía el intercambio o los intercambios a la entidad de destino. Este puerto de envío será un puerto de envío unidireccional estático.  
  
-   Cree una entidad (socio comercial) para la Entidad A y la Entidad B.  
  
-   Crear un perfil de negocio para cada uno de los socios comerciales.  
  
-   Cree un acuerdo entre los dos perfiles configurando las propiedades de EDI para que se reciba el mensaje dividiendo o conservando el intercambio.  
  
-   Coloque un intercambio EDI por lotes en una carpeta local asociada a la ubicación de recepción. A continuación, podrá comprobar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha colocado los intercambios separados del lote recibido (si se divide el lote) o el único intercambio por lotes conservado (si se conserva el lote) en la carpeta asociada al puerto de envío.  
  
    > [!NOTE]
    >  Si ha realizado los pasos en el tutorial de envío de intercambios por lotes, puede utilizar la salida de esa solución como la salida para esta solución. La salida de esta solución es un lote de dos mensajes 850. Para obtener más información, consulte [tutorial (X12): enviar intercambios de EDI por lotes](../core/walkthrough-x12-sending-batched-edi-interchanges.md).  
  
 En esta sección se describen los procedimientos para configurar el tutorial.  
  
##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
2.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. Mover a  **\<unidad >: \Program 2009\XSD_Schema\EDI\X12\00401 de BizTalk Server**y, a continuación, haga doble clic en el esquema correspondiente al mensaje de prueba.  
  
    > [!NOTE]
    >  Si los esquemas EDI no se han descomprimido en las carpetas XSD_SchemaEDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta XSD_SchemaEDI para descomprimir los esquemas en la carpeta predeterminada.  
  
    > [!NOTE]
    >  En un mensaje de prueba, puede utilizar el intercambio por lotes que ha generado la solución en el tutorial de envío de intercambios por lotes. La salida de esa solución es un lote de dos instancias del mensaje de ejemplo 850 que se utiliza en el tutorial para programadores de la interfaz EDI. Si lo hace, debe usar el esquema x12_00401_850.xsd ubicado en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI interfaz Developer TutorialInbound_EDI.  
  
3.  Defina el archivo de clave de ensamblado y, a continuación, genere e implemente el ensamblado.  
  
##### <a name="to-create-a-one-way-receive-port-to-receive-the-batched-edi-messages"></a>Procedimiento para crear un puerto de recepción unidireccional para recibir los mensajes EDI procesados por lotes  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción.**  
  
2.  Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
3.  Haga clic en **Nueva**.  
  
4.  Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  Especifique una carpeta para **carpeta recepción**y una máscara para **máscara de archivo**, como  **\*.txt**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Para **canalización de recepción**, seleccione **EdiReceive**.  
  
8.  Haga clic en **Aceptar**.  
  
9. En el árbol de consola, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** panel, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a>Para crear un puerto de envío estático unidireccional para enviar el intercambio EDI por lotes  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático.**  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
3.  En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4.  Especifique una carpeta para **carpeta de destino**y una máscara para **máscara de archivo**, como  **\*.txt**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  En **canalización de envío**, seleccione **EdiSend**.  
  
7.  En el árbol de consola, seleccione **filtros**. En el **filtros** página, escriba una expresión de filtro que se suscribirá a los mensajes en el lote. Por ejemplo, seleccione **BTS. ReceivePortName** para **propiedad**,  **==**  para **operador**y el nombre del puerto de recepción que acaba de crear para **Valor**.  
  
8.  Haga clic en **Aceptar**.  
  
9. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a>Para crear una entidad y un perfil de negocio para la Entidad A  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **PartyA_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a>Para crear una entidad y un perfil de negocio para la Entidad B  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **PartyB_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo entre los dos perfiles de negocio  
  
1.  Haga clic en **PartyA_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **X12**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **PartyB**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **PartyB_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha es para configurar un acuerdo unidireccional y cada acuerdo unidireccional representa una transacción completa del mensaje (incluida la transferencia del mensaje y la transferencia de la confirmación).  
  
6.  En el **General** ficha la **propiedades generales** página, en la **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **almacenar carga de mensaje para informes**.  
  
7.  Realizar las tareas siguientes en el **entidad -> PartyB** ficha.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Coincidirá con los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado de intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador de receptor y el identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
  
        > [!NOTE]
        >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **THEM**, **ISA7** a **ZZ**, y **ISA8** a **US**.  
  
    2.  En el **validación** página en el **configuración de intercambio** sección, asegúrese de que **comprobar isa13 duplicados** opción está desactivada.  
  
        > [!NOTE]
        >  Borrar el **comprobar isa13 duplicados** propiedad le permite recibir varias instancias del mismo mensaje.  
  
    3.  En el **juego de caracteres y separadores** página en el **configuración de intercambio** sección, seleccione la **CR LF** opción.  
  
    4.  En el **configuración de Host Local** página en el **configuración de intercambio** sección, en la **opción de procesamiento de mensaje de entrada** cuadro, seleccione la **división Intercambio en conjuntos de transacciones: suspender conjuntos de transacciones en caso de Error** opción.  
  
        > [!NOTE]
        >  Para empezar, en esta solución dividiremos el intercambio seleccionando esta opción. Más tarde, como parte de [para probar el tutorial](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc) procedimiento a continuación, configuraremos la solución para conservar el intercambio.  
  
    5.  En el **puertos de envío** página en el **configuración de intercambio** sección, asocie el puerto de envío que creó anteriormente. En el **puertos de envío** cuadrícula, en la **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío.  
  
    6.  En el **sobres** página en el **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Seleccione **predeterminado**. **Nota:** al seleccionar esta fila como valor predeterminado, los valores de **GS1**, **GS2**, **GS3**, **GS7**y **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el Mensaje.|  
        |**Tipo de transacción**|Seleccione el tipo de mensaje del mensaje de prueba, **850 - pedido de compra**.|  
        |**Versión y lanzamiento**|Especifique la versión EDI, **00401**.|  
        |**Espacio de nombres de destino**|Seleccione **http://schemas.microsoft.com/Edi/X12**.|  
        |**GS1**|Compruebe que está seleccionado el tipo de mensaje del mensaje de prueba, **PO - Purchase Order (850)**.|  
        |**GS2**|Escriba un valor para el remitente de la aplicación, por ejemplo, **Purchasing**.|  
        |**GS3**|Escriba un valor para el receptor de la aplicación, por ejemplo, **OrderControl**.|  
        |**GS4**|Seleccionar el formato de fecha que desee. **Nota:** tiene que seleccionar el valor en la lista desplegable, no basta con hacer clic en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente.|  
        |**GS5**|Seleccione el formato de hora que desee.|  
        |**GS7**|Seleccione **X - Accredited Standards Committee X12**.|  
        |**GS8**|Compruebe que se ha especificado la versión de EDI, **00401**.|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Para establecer los valores de GS01, GS02, GS03, GS04, GS05, GS07 y GS08 de las confirmaciones salientes basados en los valores especificados para **tipo de transacción**, **versión**, y **destino espacio de nombres**. La canalización de envío intenta hacer coincidir el tipo de conjunto de transacciones, la versión X12 y el espacio de nombres de destino con los valores correspondientes del encabezado del mensaje. Si es correcta, usa los valores de GS asociados a la **tipo de transacción**, **versión**, y **espacio de nombres de destino** valores.  
  
8.  Realizar las tareas siguientes en el **PartyB -> entidad** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **ISA5**, **ISA6**, **ISA7**, y **ISA8**.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **US**, **ISA7** a **ZZ**, y **ISA8** a **THEM**.  
  
9. Haga clic en **Aplicar**.  
  
10. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  
  
####  <a name="BKMK_Proc"></a>Para probar el tutorial  
  
1.  En el Explorador de Windows, abra la carpeta local asociada a la ubicación de recepción y coloca un intercambio EDI por lotes de prueba en una carpeta.  
  
    > [!NOTE]
    >  En un mensaje de prueba, puede utilizar la salida de intercambio por lotes que ha generado la solución en el tutorial de envío de intercambios por lotes. Este mensaje de ejemplo contendría dos conjuntos de transacciones.  
  
2.  Abra la carpeta que haya asociado al puerto de envío que haya creado anteriormente. Compruebe que la carpeta contiene dos nuevos archivos y que cada archivo es un intercambio 850 que contiene uno de los conjuntos de transacciones en el mensaje por lotes de prueba.  
  
3.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo, haga clic en cualquiera de los dos perfiles empresariales que forman parte del acuerdo creado anteriormente. En el **contratos** sección, haga clic en el acuerdo y haga clic en **propiedades**.  
  
4.  En el **propiedades del acuerdo de** cuadro de diálogo la **configuración de Host Local** página en el **configuración de intercambio** sección, en el **mensaje de entrada Opción de procesamiento** , seleccione **conservar intercambio: suspender intercambio en caso de Error** o **conservar intercambio: suspender conjuntos de transacciones en caso de Error** y haga clic en **Aceptar**.  
  
5.  Haga clic en **instancias de Host** en el **configuración de plataforma** nodo, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.  
  
6.  En el Explorador de Windows, abra la carpeta local asociada a la ubicación de recepción y vuelva a colocar el mismo intercambio EDI por lotes de prueba en la carpeta.  
  
7.  En el Explorador de Windows, abra la carpeta que haya asociado al puerto de envío que haya creado anteriormente. Compruebe que la carpeta contiene ahora solo un nuevo archivo y que éste es un intercambio que contiene los dos conjuntos de transacciones 850 que estaban en el mensaje por lotes de prueba.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)   
 [Dividir un intercambio EDI por lotes](../core/splitting-a-batched-edi-interchange.md)   
 [Dividir subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md)   
 [Conservar un recibido el intercambio EDI por lotes](../core/preserving-a-received-batched-edi-interchange.md)   
 [Tutorial (X12): Enviar intercambios EDI por lotes](../core/walkthrough-x12-sending-batched-edi-interchanges.md)   
 [Tutorial (X12): Recibir intercambios EDI y devolución de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)   
 [Tutorial (X12): Enviar intercambios EDI](../core/walkthrough-x12-sending-edi-interchanges.md)