---
title: 'Tutorial (X12): Enviar intercambios EDI | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05533821-b9eb-44bc-af65-b6fb0b545137
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc29d8739aeff07241c1491ba7ae96dcf7260372
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-x12-sending-edi-interchanges"></a>Tutorial (X12): Envío de intercambios EDI
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para enviar intercambios de EDI mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="how-the-solution-sends-edi-interchanges"></a>Cómo la solución envía intercambios EDI  
 La solución hará lo siguiente:  
  
1.  Un puerto de recepción de archivos unidireccional recibe un mensaje EDI de Fabrikam.  
  
2.  Mediante la canalización EdiReceive, el puerto de recepción comprueba el mensaje y lo convierte en XML. El puerto de recepción coloca el mensaje de prueba en el MeassageBox.  
  
3.  Un puerto de envío unidireccional estático recoge el mensaje XML del cuadro de mensajes.  
  
4.  El puerto de envío unidireccional estático valida el mensaje EDI con el esquema de mensajes, serializa el mensaje EDI en un intercambio EDI y, a continuación, envía le mensaje EDI en la carpeta de local de Contoso del socio comercial.  
  
## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Este tutorial utiliza la siguiente funcionalidad:  
  
-   La recepción de una confirmación no se prueba en este tutorial. Para entender cómo recibir una confirmación, vea demostrado [tutorial (X12): envío y recepción de intercambios EDI hacer la copia de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)  
  
-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  
  
    > [!NOTE]
    >  La configuración que se usa para la codificación EDIFACT e HIPAA es bastante parecida a la que usa la codificación X12.  
  
-   El tipo de codificación EDI y la validación extendida se realizarán en el intercambio saliente.  
  
-   La solución usa un puerto de envío unidireccional estático con un tipo de transporte de archivo.  
  
    > [!NOTE]
    >  En lugar de un puerto de envío unidireccional estático, puede utilizar un puerto de envío bidireccional estático para enviar el intercambio y recibir la confirmación. Puede también usar un puerto de envío unidireccional dinámico para enviar el intercambio. Para obtener más información sobre el uso de un puerto de envío dinámico, vea [configurar un puerto de envío dinámico para enviar intercambios EDI y confirmaciones](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md).  
  
    > [!NOTE]
    >  Puede usar un adaptador de HTTP y transporte AS2. Para obtener más información sobre cómo hacerlo, consulte [tutorial (AS2): enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) o [tutorial (AS2): enviar EDI a través de AS2 con un MDN asíncrono](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).  
  
-   Se habilitarán los informes EDI y se guardarán los conjuntos de transacciones para su visualización a partir del informe de estado de intercambio.  
  
-   Para realizar pruebas, la solución usa una ubicación de recepción para recibir un mensaje de prueba.  
  
 La siguiente figura muestra la arquitectura para esta solución, que usa un puerto de envío unidireccional estático.  
  
 ![Enviar intercambios EDI](../core/media/6915024c-687c-4076-a730-3f7b9d2db7fb.gif "6915024c-687c-4076-a730-3f7b9d2db7fb")  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
-   Agregue los esquemas de mensaje necesarios a un proyecto de BizTalk y, a continuación, genere e implemente el proyecto, de modo que los esquemas estén disponibles para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los use a la hora de procesar el intercambio saliente.  
  
-   Cree un puerto de recepción y ubicación para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para la recepción del intercambio EDI. La ubicación de recepción está vinculada a la carpeta de archivo donde Fabrikam suelta el intercambio EDI que debe enviarse a Contoso. La ubicación de recepción usará una canalización de recepción EdiReceive.  
  
-   Cree un puerto de envío para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envíe el intercambio EDI a Contoso. En este tutorial se creará un puerto de envío unidireccional estático.  
  
-   Crear una entidad (socio comercial) para Fabrikam y Contoso.  
  
-   Crear un perfil de negocio para cada uno de los socios comerciales.  
  
-   Crear un acuerdo entre los dos perfiles configurando las propiedades de EDI para que se reciba el mensaje.  
  
-   Probar el tutorial con un intercambio de prueba EDI.  
  
    > [!NOTE]
    >  En un mensaje de prueba, puede usar el archivo SamplePO.txt usado en el tutorial de programadores de la interfaz EDI. Ese archivo se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\. Es un mensaje X12 850.  
  
### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  
  
##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
2.  Haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. Acceda a la carpeta donde está el esquema en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI y, a continuación, haga doble clic en el esquema.  
  
    > [!NOTE]
    >  Si los esquemas EDI no se han descomprimido en las carpetas \XSD_Schema\EDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta \XSD_Schema\EDI para descomprimir los esquemas en la carpeta predeterminada.  
  
    > [!NOTE]
    >  Si usa el archivo SamplePO.txt usado en el tutorial de programadores de la interfaz EDI, debe usar el esquema X12_00401_850.xsd, que se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI. No debe usar el esquema X12 850 en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema.  
  
3.  Agregue el archivo de clave de ensamblado en el proyecto y, a continuación, genere e implemente el ensamblado.  
  
##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>Procedimiento para crear un puerto de recepción unidireccional (para Fabrikam) para recibir el intercambio EDI  
  
1.  En el Explorador de Windows, cree una carpeta local para recibir el intercambio en.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
3.  Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
4.  Haga clic en **Nueva**.  
  
5.  Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
6.  Especifique una carpeta para **carpeta recepción**y escriba  **\*.txt** para la máscara de archivo.  
  
7.  Haga clic en **Aceptar**.  
  
8.  Para **canalización de recepción**, seleccione **EdiReceive**.  
  
9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
10. En el árbol de consola, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** panel, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>Procedimiento para crear un puerto de envío estático unidireccional (para Contoso) para enviar el intercambio EDI  
  
1.  En el Explorador de Windows, cree una carpeta local a la que enviar el intercambio EDI.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
4.  En el **transporte** sección, seleccione la **tipo**, por ejemplo, **archivo**.  
  
5.  Si usa un tipo de archivo, haga clic en **configurar**. En **carpeta de destino**, busque una carpeta para enviar el intercambio. Para **nombre de archivo**, escriba **%MessageID%.edi**. Haga clic en **Aceptar**.  
  
6.  En **canalización de envío**, seleccione **EdiSend**.  
  
7.  En el árbol de consola, seleccione **filtros**y escriba una expresión de filtro para el puerto de envío se usan para suscribirse al mensaje. Por ejemplo, puede utilizar la ubicación de recepción que recibirá el mensaje de prueba original como una expresión de filtro. Para ello, **propiedad**, escriba **BTS. ReceivePortName**; para **operador**, escriba  **==** ; y para **valor** escriba el nombre del puerto de recepción que ha creado en recibir el mensaje XML de Fabrikam.  
  
    > [!NOTE]
    >  Puede filtrar en otra propiedad distinta a la de su elección, por ejemplo, en BTS.MessageType.  
  
8.  Haga clic en **Aceptar**.  
  
9. Haga clic en el **puertos de envío** nodo en la consola de administración, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Para crear una entidad y un perfil de negocio para Fabrikam  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **Fabrikam_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Para crear una entidad y un perfil de negocio para Contoso  
  
1.  Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite entidad o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es de la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  
  
3.  Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  
  
4.  En el **propiedades de perfil** cuadro de diálogo la **General** escriba **Contoso_Profile** en el **nombre** cuadro de texto.  
  
    > [!NOTE]
    >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** página, especifique un nombre para el perfil.  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo entre los dos perfiles de negocio  
  
1.  Haga clic en **Fabrikam_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **X12**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha es para configurar un acuerdo unidireccional y cada acuerdo unidireccional representa una transacción completa del mensaje (incluida la transferencia del mensaje y la transferencia de la confirmación).  
  
6.  En el **General** ficha la **propiedades generales** página, en la **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **almacenar carga de mensaje para informes**.  
  
7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Coincidirá con los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado de intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador de receptor y el identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
  
        > [!NOTE]
        >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **THEM**, **ISA7** a **ZZ**, y **ISA8** a **US**.  
  
    2.  En el **validación** página en el **configuración de intercambio** sección, asegúrese de que **comprobar isa13 duplicados** opción está desactivada.  
  
        > [!NOTE]
        >  Borrar el **comprobar isa13 duplicados** propiedad le permite recibir varias instancias del mismo mensaje.  
  
    3.  En el **juego de caracteres y separadores** página en el **configuración de intercambio** sección, seleccione la **CR LF** opción.  
  
    4.  En el **puertos de envío** página en el **la configuración de intercambio** sección, asocie el puerto de envío que va a recibir el intercambio EDI de Fabrikam. En el **puertos de envío** cuadrícula, en la **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío creado para recibir el intercambio EDI de Fabrikam.  
  
    5.  En el **validación** página en el **configuración del conjunto de transacciones** sección, deje **validación de tipo EDI** activada y compruebe **validaciónextendida**.  
  
    6.  Si está usando uno de los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la **configuración de Host Local** página en el **configuración del conjunto de transacciones** sección, seleccione el espacio de nombres del esquema que se va a usarse para procesar el intercambio entrante.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Activar la casilla en la columna Predeterminado.|  
        |**Para ST1**|Seleccione **850 - pedido de compra**.|  
        |**GS2**|Escriba **THEM**.|  
        |**Target Namespace**|Seleccione **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.|  
  
        > [!NOTE]
        >  El establecimiento de las propiedades permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determine el esquema que se va a utilizar en el procesamiento del intercambio 850 entrante. Si un intercambio tiene los valores de GS02 y ST01 que se escriben en una línea de la cuadrícula, se utilizará el espacio de nombres de destino para la misma línea con el fin de determinar el esquema que se va a utilizar.  
  
    7.  En el **sobres** página en el **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Seleccione la casilla de la **predeterminado** columna. **Nota:** al seleccionar esta fila como valor predeterminado, los valores de **GS1**, **GS2**, **GS3**, **GS7**y **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el Mensaje.|  
        |**Tipo de transacción**|Seleccione el tipo de mensaje del mensaje de prueba, **850 - pedido de compra**.|  
        |**Versión y lanzamiento**|Especifique la versión EDI, **00401**.|  
        |**Espacio de nombres de destino**|Seleccione **http://schemas.microsoft.com/BizTalk/Edi/X12/2006**.|  
        |**GS1**|Compruebe que está seleccionado el tipo de mensaje del mensaje de prueba, **PO - Purchase Order (850)**.|  
        |**GS2**|Escribir un valor para el remitente de aplicación.|  
        |**GS3**|Escribir un valor para Receptor de aplicación.|  
        |**GS4**|Seleccionar el formato de fecha que desee. **Nota:** tiene que seleccionar el valor en la lista desplegable, no basta con hacer clic en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente.|  
        |**GS5**|Seleccione el formato de hora que desee.|  
        |**GS7**|Seleccione **X - Accredited Standards Committee X12**.|  
        |**GS8**|Compruebe que se ha especificado la versión de EDI, **00401**.|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Para establecer los valores de GS01, GS02, GS03, GS04, GS05, GS07 y GS08 de las confirmaciones salientes basados en los valores especificados para **tipo de transacción**, **versión**, y **destino espacio de nombres**. La canalización de envío intenta hacer coincidir el tipo de conjunto de transacciones, la versión X12 y el espacio de nombres de destino con los valores correspondientes del encabezado del mensaje. Si es correcta, usa los valores de GS asociados a la **tipo de transacción**, **versión**, y **espacio de nombres de destino** valores.  
  
8.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **ISA5**, **ISA6**, **ISA7**, y **ISA8**.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **US**, **ISA7** a **ZZ**, y **ISA8** a **THEM**.  
  
9. Haga clic en **Aplicar**.  
  
10. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  
  
##### <a name="to-test-the-walkthrough"></a>Para probar el tutorial  
  
1.  En el Explorador de Windows, coloque el intercambio EDI de prueba en su carpeta de recepción local.  
  
    > [!NOTE]
    >  En un mensaje de prueba, puede usar el archivo SamplePO.txt usado en el tutorial de programadores de la interfaz EDI. Ese archivo se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial. Es un mensaje X12 850. Si usa este mensaje, debe haber implementado el esquema X12_00401_850.xsd que se incluye en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI. No debe usar el esquema X12 850 en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema.  
  
2.  En el Explorador de Windows, abra la carpeta de destino especificada para el puerto de envío. Compruebe que la carpeta contenga el intercambio EDI de salida que tiene encabezados ISA, GS y ST que coincidan con los valores que ha especificado en las propiedades de acuerdo.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)