---
title: "Tutorial (X12): Recibir intercambios EDI y devolver una confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25d2b5f3-6bd1-413c-aace-e4dd71f80403
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79eb16ac77f2f1573735c36b19fa6aa68c001c76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-x12-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a>Tutorial (X12): Recepción de intercambios EDI y devolución de una confirmación
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para recibir intercambios de EDI mediante el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En esta solución, se envía un intercambio EDI desde un socio comercial, Fabrikam, a otro, Contoso.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="how-the-solution-receives-edi-interchanges"></a>Cómo recibe la solución intercambios EDI  
 La solución hará lo siguiente:  
  
> [!NOTE]
>  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
1.  Recibir un intercambio EDI de archivos sin formato del socio comercial Fabrikam.  
  
2.  Validar el intercambio EDI con su esquema, desensamblar el mensaje a XML y depositar el mensaje XML en el cuadro de mensajes.  
  
3.  Generar una confirmación 997 al intercambio EDI recibido y depositarla en el cuadro de mensajes.  
  
4.  Generar una confirmación TA1 al intercambio EDI recibido y depositarla en el cuadro de mensajes.  
  
5.  Recoger el mensaje XML mediante un puerto de envío unidireccional y ensamblar el intercambio EDI.  
  
6.  Enviar un intercambio EDI a Contoso.  
  
7.  Recoger el XML de 997 mediante un puerto de envío unidireccional y ensamblar el intercambio EDI 997.  
  
8.  Enviar un intercambio 997 a Fabrikam.  
  
9. Recoger el XML de TA1 mediante un puerto de envío unidireccional y ensamblar el intercambio EDI de TA1.  
  
10. Enviar un intercambio TA1 a Fabrikam.  
  
## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Por lo que respecta a este tutorial, se habilitará la siguiente funcionalidad:  
  
-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  
  
    > [!NOTE]
    >  La configuración que se usa para HIPAA es bastante parecida a la que se usa para la codificación X12. Para obtener instrucciones sobre cómo crear una solución similar para EDIFACT, vea [tutorial (EDIFACT): envío y recepción de intercambios EDI hacer la copia de una confirmación](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md).  
  
-   El tipo de codificación EDI y la validación extendida se realizarán en el intercambio entrante.  
  
-   Se generarán confirmaciones técnicas y funcionales para la devolución del intercambio al remitente.  
  
-   La solución usa una ubicación de recepción unidireccional con un tipo de transporte de archivo.  
  
    > [!NOTE]
    >  Puede usar un puerto de recepción bidireccional de petición-respuesta y una ubicación para recibir el mensaje; no obstante, si lo hace, no podrá usar un tipo de transporte de archivo para la ubicación de recepción. Para obtener más información, consulte [configurar un puerto para recibir mensajes de EDI y confirmaciones](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).  
  
-   Se habilitarán los informes EDI y se guardarán los conjuntos de transacciones para su visualización a partir del informe de estado de intercambio.  
  
-   Para realizar pruebas, la solución usa tres puertos de envío para enviar el intercambio EDI y las confirmaciones creadas a carpetas locales.  
  
 La siguiente ilustración muestra la arquitectura de esta solución:  
  
 ![Recibir intercambios EDI](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
-   Agregue los esquemas de mensaje necesarios a un proyecto de BizTalk y, a continuación, genere e implemente el proyecto, de modo que los esquemas estén disponibles para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los use a la hora de procesar el intercambio recibido.  
  
-   Cree un puerto de recepción unidireccional para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el intercambio EDI del socio comercial y genere una confirmación. La ubicación de recepción está vinculada a la carpeta de archivo donde Fabrikam suelta el intercambio EDI que debe enviarse a Contoso.  
  
    > [!NOTE]
    >  Puede usar el puerto de recepción de solicitud-respuesta y la ubicación para recibir el mensaje de petición-respuesta bidireccional, pero si lo hace, no podrá usar un tipo de transporte de archivo para la ubicación de recepción.  
  
-   Cree un puerto de envío que envíe el intercambio EDI a una carpeta local de Contoso, otro que envíe la confirmación 997 a una carpeta local de Fabrikam y otro que envíe la confirmación TA1 a una carpeta local de Fabrikam.  
  
-   Crear una entidad (socio comercial) para Fabrikam y Contoso.  
  
-   Crear un perfil de negocio para cada uno de los socios comerciales.  
  
-   Cree un acuerdo entre los dos perfiles configurando las propiedades EDI para el mensaje que se va a recibir y la confirmación que se va a enviar.  
  
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
  
1.  En el Explorador de Windows, cree una carpeta local en la que recibir el intercambio.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
3.  Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
4.  Haga clic en **Nueva**.  
  
5.  Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
6.  Busque una carpeta para **carpeta recepción** cuadro de texto. Esta carpeta la creó en el paso 1 de este procedimiento. Escriba una máscara de archivo, como  **\*.edi** o  **\*.txt**.  
  
7.  Haga clic en **Aceptar**.  
  
8.  Para **canalización de recepción**, seleccione **EdiReceive**.  
  
9. Haga clic en **Aceptar** en el **propiedades de la ubicación de recepción** cuadro de diálogo. Haga clic en **Aceptar** en el **propiedades de puerto de recepción** cuadro de diálogo.  
  
10. En el árbol de consola, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** panel, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>Procedimiento para crear un puerto de envío estático unidireccional (para Contoso) para enviar el intercambio EDI  
  
1.  En el Explorador de Windows, cree una carpeta local a la que enviar el intercambio de prueba.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
4.  En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  Para **carpeta de destino**, vaya a la carpeta para recibir el intercambio. Esta carpeta la creó en el paso 1 de este procedimiento. Para **máscara de archivo**, especifique el formato de intercambio, como  **\*.edi** o  **\*.xml**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En **canalización de envío**, seleccione **EdiSend**.  
  
8.  En el árbol de consola, seleccione **filtros**. Especifique un filtro al que suscribir el intercambio EDI. Por ejemplo, para **propiedad**, escriba **BTS. MessageType**; para **operador**, escriba  **==** ; y para **valor** especifique el esquema para el intercambio, por ejemplo, http:// schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850.  
  
    > [!NOTE]
    >  La configuración de filtro anterior asegura que esos intercambios, no las confirmaciones, se enviarán a la carpeta asociada a este puerto de envío.  
  
9. Haga clic en **Aceptar**.  
  
10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-997n-acknowledgment"></a>Para crear un puerto de envío estático unidireccional para enviar la confirmación 997  
  
1.  En el Explorador de Windows, cree una carpeta local a la que enviar la confirmación 997.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
4.  En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  Para **carpeta de destino**, busque una carpeta para recibir la confirmación 997. Esta carpeta la creó en el paso 1 de este procedimiento. Para **máscara de archivo**, especifique el formato de intercambio, como  **\*.edi** o  **\*.txt**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En **canalización de envío**, seleccione **EdiSend**.  
  
8.  En el árbol de consola, seleccione **filtros**. Especifique un filtro al que suscribir la confirmación 997. Por ejemplo, para **propiedad**, escriba **BTS. MessageType**; para **operador**, escriba  **==** ; y para **valor** especifique el esquema para la confirmación, por ejemplo, `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.  
  
9. Haga clic en **Aceptar**.  
  
10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-ta1-acknowledgment"></a>Para crear un puerto de envío estático unidireccional para enviar la confirmación TA1  
  
1.  En el Explorador de Windows, cree una carpeta local a la que enviar la confirmación TA1.  
  
2.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
4.  En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  Para **carpeta de destino**, busque una carpeta para recibir la confirmación TA1. Esta carpeta la creó en el paso 1 de este procedimiento. Para **máscara de archivo**, especifique el formato de intercambio, como  **\*.edi** o  **\*.txt**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En **canalización de envío**, seleccione **EdiSend**.  
  
8.  En el árbol de consola, seleccione **filtros**. Especifique un filtro al que suscribir la confirmación TA1. Por ejemplo, para **propiedad**, escriba **BTS. MessageType**; para **operador**, escriba  **==** ; y para **valor** especifique el esquema para la confirmación, por ejemplo, http:// schemas.microsoft.com/Edi/X12#X12_TA1_Root.  
  
9. Haga clic en **Aceptar**.  
  
10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
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
  
    2.  En el **confirmación** página en el **configuración de intercambio** sección, verificación **TA1 esperado** y **997 esperado**.  
  
    3.  En el **validación** página en el **configuración de intercambio** sección, asegúrese de que **comprobar isa13 duplicados** opción está desactivada.  
  
        > [!NOTE]
        >  Borrar el **comprobar isa13 duplicados** propiedad le permite recibir varias instancias del mismo mensaje.  
  
    4.  En el **juego de caracteres y separadores** página en el **configuración de intercambio** sección, seleccione la **CR LF** opción.  
  
    5.  En el **configuración de Host Local** página en el **configuración de intercambio** sección, desactive el **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** opción.  
  
        > [!NOTE]
        >  Si usaba puerto para recibir el intercambio y devolver la confirmación de recepción bidireccional, se comprobaría si **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta**.  
  
    6.  En el **puertos de envío** página en el **la configuración de intercambio** sección, asociar los puertos de envío que va a recibir el intercambio de Fabrikam y los puertos de envío que va a recibir el confirmaciones de Contoso. En el **puertos de envío** cuadrícula, en la **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío creado para recibir el intercambio EDI de Fabrikam. Repita el paso para el puerto de envío creado para recibir la confirmación de TA1 y para el puerto de envío creado para recibir la confirmación de 997.  
  
    7.  En el **validación** página en el **configuración del conjunto de transacciones** sección, deje **validación de tipo EDI** activada y compruebe **validaciónextendida**.  
  
    8.  Si está usando uno de los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la **configuración de Host Local** página en el **configuración del conjunto de transacciones** sección, seleccione el espacio de nombres del esquema que se va a usarse para procesar el intercambio entrante. Si está usando un esquema personalizado, especifique valores en el **espacio de nombres de destino personalizar** cuadrícula, por lo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede determinar el espacio de nombres utilizando transacciones de grupo y establece los valores de encabezado.  
  
    9. En el **sobres** página en el **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Seleccione **predeterminado**. **Nota:** al seleccionar esta fila como valor predeterminado, los valores de **GS1**, **GS2**, **GS3**, **GS7**y **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el Mensaje.|  
        |**Tipo de transacción**|Seleccione el tipo de mensaje del mensaje de prueba, **850 - pedido de compra**.|  
        |**Versión y lanzamiento**|Especifique la versión EDI, **00401**.|  
        |**Espacio de nombres de destino**|Seleccione **http://schemas.microsoft.com/Edi/X12**.|  
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
  
    > [!NOTE]
    >  Aunque la confirmación es parte de la misma transacción de mensaje, las propiedades relacionadas con el modo en que debe generarse la confirmación se configuran en el **Contoso -> Fabrikam** ficha. Esto es necesario porque las propiedades de contexto de confirmación para el remitente y receptor calificadores se establecen en el efecto contrario de los valores especificados en la **Contoso -> Fabrikam** ficha. Por ejemplo, si remitente y receptor identificadores se establecen en ellos y nosotros en el **Fabrikam -> Contoso** propiedades de contexto de la ficha, el remitente y receptor se establecerá en nosotros y ellos en la confirmación. Normalmente, la otra ficha de acuerdo unidireccional también tendrá los identificadores de remitente y receptor configurados respectivamente en NOSOTROS y ELLOS. Por lo tanto, el mensaje de confirmación se resolverá en dicho acuerdo y se seleccionará la configuración de propiedades. Por lo tanto, si desea tener confirmación para usar diferentes separadores de elementos o si desea tener confirmación para usar CR LF, especifique las propiedades en el **Contoso -> Fabrikam** ficha.  
    >   
    >  Conceptualmente, las propiedades para la confirmación se seleccionarán desde cualquier ficha de acuerdo unidireccional que tenga los mismos calificadores de remitente y receptor que están configurados en las propiedades de contexto de la confirmación. No obstante, para facilitar su uso en la práctica, normalmente debe configurar esto en la otra ficha de acuerdo unidireccional del acuerdo que creó en el cual debe haberse resuelto el intercambio.  
  
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
  
2.  Abra la carpeta asociada al puerto de envío para los intercambios y compruebe que ésta contiene el intercambio EDI.  
  
3.  Abra la carpeta asociada al puerto de envío para la confirmación 997 y compruebe que ésta contiene una confirmación 997.  
  
4.  Abra la carpeta asociada al puerto de envío para la confirmación TA1 y compruebe que ésta contiene una confirmación TA1.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)