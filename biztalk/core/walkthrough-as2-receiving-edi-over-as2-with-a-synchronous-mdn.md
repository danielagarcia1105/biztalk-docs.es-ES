---
title: 'Tutorial (AS2): Recibir EDI a través de AS2 con un MDN sincrónico | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b63395f-03f4-45e8-a68a-9bbbd8dfa344
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971620284a8058663f7c054cd6286cbd01d81d84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024018"
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn"></a>Tutorial (AS2): Recibir EDI a través de AS2 con un MDN sincrónico
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para la recepción de mensajes EDI a través del transporte AS2 y la devolución de MDN sincrónicos.  

## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  

- Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

- El equipo que ejecuta el tutorial debe tener Internet Information Services (IIS) 7 instalado.  

- Si el equipo que ejecuta el tutorial tiene instalada la versión de 64 bits de Windows, debe asegurarse de que los hosts de BizTalk están marcados como de 32 bits solamente. También debe asegurarse de IIS tiene la configuración de aplicaciones de 32 bits para los grupos de aplicaciones establecido en **True**. Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  

## <a name="how-the-solution-receives-an-edias2-message-and-returns-a-synchronous-mdn"></a>Cómo la solución recibe un mensaje EDI/AS2 y devuelve un MDN sincrónico  
 La solución realiza las operaciones siguientes:  

1. Recibe del socio comercial Fabrikam un mensaje AS2 que contiene un intercambio EDI a través de HTTP y descodifica el intercambio de EDIINT/AS2.  

   > [!NOTE]
   >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  

2. Devuelve un MDN sincrónico al socio comercial usando el puerto de recepción de solicitud-respuesta.  

3. Convierte el formato EDI del intercambio en el formato XML interno y lo coloca en el cuadro de mensajes.  

4. Un puerto de envío de archivo con una canalización PassThruTransmit recoge el archivo XML del mensaje.  

5. El puerto de envío envía el archivo XML de intercambio EDI a una carpeta en la entidad de Contoso.  

   La siguiente ilustración muestra la arquitectura de esta solución.  

   ![Recepción AS2 con un MDN sincrónico](../core/media/4ff20070-1c36-42e5-af14-832771d63b88.gif "4ff20070-1c36-42e5-af14-832771d63b88")  

## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Los siguientes puntos se aplican a la funcionalidad de este tutorial:  

-   No se genera una confirmación EDI. Generar una confirmación EDI se muestra en [tutorial (X12): devolución de una confirmación de envío y recepción de intercambios EDI](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md). Envía una confirmación EDI mediante transporte AS2 se describe en [tutorial (AS2): enviar EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md).  

-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  

    > [!NOTE]
    >  La configuración que utiliza la codificación EDIFACT es bastante parecida a la que usa la codificación X12.  

-   El tipo de codificación EDI y la validación extendida se realizarán en el intercambio entrante.  

-   Se habilitarán informes AS2 y EDI y se guardarán los conjuntos de transacciones para su visualización a partir del informe de estado de intercambio.  

-   Esta solución no configura el almacenamiento de mensajes, el cifrado, la compresión ni la firma en la base de datos sin repudio. Para conocer los procedimientos sobre cómo configurar estas propiedades, vea [configurar propiedades de AS2](../core/configuring-as2-properties.md).  

## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  

- Generar e implementar un proyecto de BizTalk con el esquema de mensaje necesario, de modo que el esquema esté disponible para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo utilice a la hora de procesar el intercambio recibido.  

- Habilitar el filtro ISAPI de BTS que se utiliza para la recepción del mensaje AS2.  

- Crear un directorio virtual de Contoso que reciba el mensaje AS2 de Fabrikam, tal y como se configura en la ubicación de recepción.  

- Especificar que Windows SharePoint Services no administre el directorio virtual de Contoso.  

- Crear un puerto de recepción HTTP bidireccional estático para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el mensaje AS2 que contiene el intercambio EDI del socio comercial y enviar la respuesta MDN. Configurar la canalización de recepción para que sea la canalización AS2EDIReceive y la canalización de envío para que sea la canalización AS2Send.  

- Crear un puerto de envío de archivo unidireccional estático para enrutar la carga EDI (en formato XML) a un carpeta local. Crear la carpeta local.  

- Crear una entidad (socio comercial) para Fabrikam y Contoso.  

- Crear un perfil de negocio para cada una de las entidades comerciales.  

- Crear un acuerdo AS2 entre los perfiles de negocio de Fabrikam y Contoso. El acuerdo AS2 contendría las propiedades para enviar un mensaje AS2 y recibir un MDN sincrónico en respuesta.  

- Crear un acuerdo X12 entre los perfiles de negocio de Fabrikam y Contoso para recibir mensajes X12.  

- Probar la solución con la utilidad del remitente de HTTP que se envía como parte de los archivos del tutorial de AS2. Esta utilidad envía un mensaje AS2 de prueba que contiene un intercambio EDI a través del transporte AS2 (X12_00401_864-Sync.edi, que también se incluye con el tutorial de AS2). Debe modificar el remitente de HTTP y el mensaje de prueba de las versiones que se encuentran en el tutorial. Estos cambios se describen en las correspondientes secciones a continuación.  

### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  

##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj.  

   > [!NOTE]
   >  Este proyecto, que se envía para el tutorial de AS2, incluye un esquema 864 para que se utilice con el mensaje de prueba.  

   > [!NOTE]
   >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  

2. Haga clic en el **esquemas** del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. Haga clic en el **firma** ficha del Diseñador de proyectos, compruebe el **firmar el ensamblado** casilla de verificación y en la lista desplegable, seleccione **New** y proporcione los valores necesarios para crear un archivo de clave de nombre seguro. Guarde los cambios y cierre la ventana de propiedades del proyecto.  

3. Genere e implemente Schemas.btproj.  

##### <a name="to-enable-the-bts-isapi-filter"></a>Para habilitar el filtro ISAPI de BTS  

1. Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  

   > [!TIP]
   >  Según el sistema operativo, la opción Herramientas administrativas puede no estar disponible en el menú Inicio. En tales casos, haga clic en **iniciar**, haga clic en **ejecutar**y escriba `inetmgr` para abrir el Administrador de Internet Information Services (IIS).  

2. Seleccione la entrada de servidor Web raíz y, en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en el **acciones** panel, haga clic **Agregar asignación de Script**.  

   > [!NOTE]
   >  La configuración de la asignación de script en el nivel de servidor web hará que esta asignación se aplique a todos los sitios web secundarios. Si desea restringir la asignación a un sitio Web o una carpeta Virtual específica, seleccione el sitio de destino o la carpeta en lugar del servidor Web.  

3. En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.  

4. En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive. Seleccione BtsHttpReceive.dll y haga clic en **Aceptar**.  

5. Escriba `BizTalk HTTP Receive` en el **nombre** campo y, a continuación, haga clic en **restricciones de solicitudes**.  

6. En el **restricciones de solicitudes** cuadro de diálogo, seleccione el **verbos** pestaña y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  

7. En el **acceso** ficha, seleccione **Script** y, a continuación, haga clic en **Aceptar**.  

8. Haga clic en **Aceptar** y cuando se le solicite que permita la extensión ISAPI, haga clic en **Sí**.  

##### <a name="to-configure-the-contoso-web-page"></a>Para configurar la página Web de Contoso  

1. En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  

2. En el **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable. Haga clic en **Aceptar**.  

   > [!NOTE]
   >  El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.  

3. Seleccione **grupos de aplicaciones**, en la vista características seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el **acciones** panel.  

4. En el **configuración avanzada** cuadro de diálogo, seleccione **identidad** y, a continuación, haga clic en el **puntos suspensivos (...)**  botón.  

5. En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.  

6. Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.  

7. En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** nodo y, a continuación, seleccione **Agregar aplicación**.  

8. En el **Agregar aplicación** diálogo cuadro, escriba **Contoso** en el **Alias** cuadro de texto y, a continuación, haga clic en **seleccione**.  

9. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  

10. Para el **ruta de acceso física**, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.  

11. Haga clic en **configuración de pruebas** y compruebe que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  

12. En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  

13. En el **autenticación** página, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  

##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>Para especificar que Windows SharePoint Services no administra su directorio virtual  

1.  Si Windows SharePoint Services está instalado en el equipo, haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  

    > [!NOTE]
    >  Este procedimiento es necesario si Windows SharePoint Server está instalado en el mismo equipo en el que está configurando el tutorial. En ese caso, debe especificar que Windows SharePoint Server no esté administrando su directorio virtual de ISS.  

2.  En el **Administración Central** página, en **Administración Central**, haga clic en **Application Management**.  

3.  En el **Application Management** página, haga clic en **definir rutas administradas**.  

4.  En el **definir rutas administradas** página, en **agregar una nueva ruta de acceso**y en el **ruta** texto, escriba **Contoso**. En **tipo**, haga clic en **ruta excluida**y, a continuación, haga clic en **Aceptar**.  

##### <a name="to-create-a-receive-port-to-receive-the-edi-over-as2-message-and-return-an-mdn"></a>Para crear un puerto de recepción para recibir el mensaje EDI a través de AS2 y devolver un MDN  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en  **Puerto de recepción de solicitud-respuesta**.  

2. Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  

3. Haga clic en **Nueva**.  

4. Nombre de la ubicación de recepción, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  

5. Para **directorio Virtual más extensión ISAPI**, escriba `/Contoso/BTSHTTPReceive.dll`.  

6. Seleccione el **suspender solicitudes con errores** casilla de verificación y haga clic en **Aceptar**.  

7. Para **canalización de recepción**, seleccione **AS2EDIReceive**.  

8. Para **canalización de envío**, seleccione **AS2Send**.  

9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  

10. En el **ubicaciones de recepción** panel de la consola de administración de BizTalk Server, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  

##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar la carga EDI a una carpeta local  

1. En el Explorador de Windows, cree una carpeta local denominada **EDI_to_Contoso** para enviar la carga EDI.  

2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

3. En el **propiedades de puerto de envío** nombre al puerto de envío, por ejemplo, cuadro de diálogo **Send_Payload**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

4. En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, busque y seleccione el **EDI_to_Contoso** carpeta que creó en el paso 1. Deje **nombre de archivo** como **%MessageID%.xml**. Haga clic en **Aceptar**.  

5. Para el **canalización de envío** lista desplegable, acepte el valor predeterminado **PassThruTransmit**.  

6. Haga clic en **filtros** en el árbol de consola. Para **propiedad**, escriba **BTS. MessageType**. Para **operador**, escriba **==**. Para **valor**, escriba el tipo de mensaje del mensaje, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.  

7. Haga clic en **Aceptar**.  

8. En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Para crear una entidad y un perfil de negocio para Fabrikam  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Fabrikam_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Para crear una entidad y un perfil de negocio para Contoso  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **Contoso_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo AS2 entre los dos perfiles de negocio  

1.  Haga clic en **Fabrikam_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

2.  En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

3.  Desde el **protocolo** lista desplegable, seleccione **AS2**.  

4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  

5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  

     Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo AS2 unidireccional.  

6.  En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**.  

7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  

    1.  En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Fabrikam`. Para **AS2 - To**, escriba `Contoso`.  

8.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  

    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **AS2_From** y **AS2-para**.  

    1.  En el **identificadores** , escriba valores para **AS2-desde** y **AS2-para**. Para **AS2-desde**, escriba `Contoso`. Para **AS2 - To**, escriba `Fabrikam`.  

9. Haga clic en **Aplicar**.  

10. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo X12 entre los dos perfiles de negocio  

1. Haga clic en **Fabrikam_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

2. En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

3. Desde el **protocolo** lista desplegable, seleccione **X12**.  

4. En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  

5. En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  

    Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo X12 unidireccional.  

6. En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **carga de mensaje de Store para el informe**.  

7. Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  

   1. En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Lo hará coincidir los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado del intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador e identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
      > 
      > [!NOTE]
      >  En este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **7654321**, **ISA7** a **ZZ** , y **ISA8** a **1234567**.  

   2. En el **validación** página bajo la **configuración de intercambio** sección, asegúrese de que **comprobación de duplicado ISA13** opción está desactivada.  

      > [!NOTE]
      >  Borrar el **comprobación de duplicado ISA13** propiedad le permite recibir varias instancias del mismo mensaje.  

   3. Si está usando uno de los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en el **configuración de Host Local** página bajo la **configuración del conjunto de transacciones** , seleccione el espacio de nombres del esquema que se va a usarse para procesar el intercambio entrante.  


      |       Use       |                           Para                            |
      |----------------------|-----------------------------------------------------------------|
      |     **Default**      |                Activar la casilla en la columna Predeterminado.                |
      | **Target Namespace** | Seleccione **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**. |

      > [!NOTE]
      >  El establecimiento de las propiedades permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determine el esquema que se va a utilizar en el procesamiento del intercambio 850 entrante. Si un intercambio tiene los valores de GS02 y ST01 que se escriben en una línea de la cuadrícula, se utilizará el espacio de nombres de destino para la misma línea con el fin de determinar el esquema que se va a utilizar.  

8. Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  

   > [!NOTE]
   >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **ISA5**, **ISA6**, **ISA7**, y **ISA8**.  

   1.  En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

       > [!NOTE]
       >  En este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **1234567**, **ISA7** a **ZZ** , y **ISA8** a **7654321**.  

9. Haga clic en **Aplicar**.  

10. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  

##### <a name="to-test-the-solution"></a>Para probar la solución  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto Sender.csproj en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.  

2. En HttpSender.cs, convierta en comentario la siguiente línea (inmediatamente debajo de la línea de comentario //Solicitar MDN asíncrono):  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
   ```  

3. Cancele la conversión de comentario de la línea siguiente (inmediatamente debajo de la línea de comentario //Solicitar MDN asíncrono):  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
   ```  

4. Genere este proyecto.  

5. En el Explorador de Windows, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial. Abra X12_00401_864-Sync.edi en el Bloc de notas. Elimine la línea que define el encabezado Disposition-Notification-Options y, a continuación, guarde el archivo.  

6. Abra una ventana de comandos. Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug. Ejecute **Sender.exe**.  

   > [!NOTE]
   >  La ejecución de Sender.exe en esta instancia envía el mensaje X12_00401_864-sync.edi al directorio virtual de Contoso (la ubicación de recepción de HTTP de BTS).  

7. Compruebe que se muestra un MDN en la ventana de comandos. Compruebe que en el MDN AS2-From es Contoso y AS2-To es Fabrikam.  

   > [!NOTE]
   >  Sender.exe muestra el MDN en la ventana de comandos.  

8. Abra la carpeta local de Contoso que ha creado para enviar la carga EDI (**\EDI_to_Contoso**). Compruebe que haya un archivo XML en la carpeta. Abra el archivo XML y compruebe que contiene un conjunto de transacciones 864.  

9. Abra el mensaje de prueba X12_00401_864-Sync.edi en el Bloc de notas y compruebe que el conjunto de transacciones en el mensaje de salida en el **\EDI_to_Contoso** carpeta local se corresponde con el conjunto de transacciones de la entrada X12_00401_864-Sync.edi. Mensaje.  

## <a name="see-also"></a>Vea también  
 [Desarrollo y configuración de soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)