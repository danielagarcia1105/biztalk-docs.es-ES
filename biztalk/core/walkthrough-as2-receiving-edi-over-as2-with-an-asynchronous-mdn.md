---
title: "Tutorial (AS2): Recibir EDI a través de AS2 con un MDN asíncrono | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3962e4-0525-4194-8cf1-b90664f1a139
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0dd9e94ff74adb4419f95b386861376bb424fd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-an-asynchronous-mdn"></a>Tutorial (AS2): Recibir EDI a través de AS2 con un MDN asíncrono
Este tutorial proporciona un conjunto de procedimientos descritos paso a paso que crean una solución para la recepción de mensajes EDI a través del transporte AS2 y la devolución de MDN sincrónicos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   El equipo que ejecuta el tutorial debe tener Internet Information Services (IIS) 7 instalado.  
  
-   Si el equipo que ejecuta el tutorial tiene instalada la versión de 64 bits de Windows, debe asegurarse de que los hosts de BizTalk están marcados como de 32 bits solamente. Además debe asegurarse de que IIS tiene establecida en True la opción de habilitar aplicaciones de 32 bits para los grupos de aplicaciones. Para obtener más información, consulte [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md).  
  
## <a name="how-the-solution-receives-an-edi-interchange-and-returns-an-asynchronous-mdn"></a>Cómo recibe la solución un intercambio EDI y devuelve un MDN asíncrono  
 La solución hará lo siguiente:  
  
1.  Recibir un mensaje AS2 que contiene un intercambio EDI a través de HTTP del socio comercial y descodificar el intercambio de EDIINT/AS2.  
  
    > [!NOTE]
    >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
2.  Generar una respuesta MDN y depositarla en el cuadro de mensajes.  
  
3.  Tomar el MDN de mensaje por un puerto de envío dinámico.  
  
4.  Devolver el MDN del mensaje asíncrono al socio comercial.  
  
5.  Convertir el formato EDI del intercambio en el formato XML interno y colocarlo en el cuadro de mensajes.  
  
6.  Un puerto de envío con una canalización PassThruTransmit recoge el archivo XML del mensaje del cuadro de mensajes.  
  
7.  El puerto de envío envía el archivo XML de intercambio EDI a una carpeta de la entidad Contoso.  
  
 La siguiente ilustración muestra la arquitectura de esta solución.  
  
 ![Recepción de AS2 con un MDN asíncrono](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")  
  
## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Los siguientes puntos se aplican a la funcionalidad de este tutorial:  
  
-   No se genera una confirmación EDI. Generar una confirmación EDI se muestra en [tutorial (X12): envío y recepción de intercambios EDI hacer la copia de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md). Enviar una confirmación EDI mediante transporte AS2 se describe en [tutorial (AS2): enviar EDI a través de AS2 con un MDN asíncrono](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).  
  
-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  
  
    > [!NOTE]
    >  La configuración que utiliza la codificación EDIFACT es bastante parecida a la que usa la codificación X12.  
  
-   El tipo de codificación EDI y la validación extendida se realizarán en el intercambio entrante.  
  
-   Se habilitarán informes AS2 y EDI y se guardarán los conjuntos de transacciones para su visualización a partir del informe de estado de intercambio.  
  
-   Esta solución no configura el almacenamiento de mensajes, el cifrado, la compresión ni la firma en la base de datos sin repudio. Para conocer los procedimientos acerca de cómo configurar estas propiedades, vea [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  
  
-   Generar e implementar un proyecto de BizTalk con el esquema de mensaje necesario, de modo que el esquema esté disponible para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo utilice a la hora de procesar el intercambio recibido.  
  
-   Habilitar el filtro ISAPI de BTS que se utiliza para la recepción del mensaje AS2.  
  
-   Crear un directorio virtual de Contoso que reciba el mensaje AS2 de Fabrikam, tal y como se configura en la ubicación de recepción.  
  
-   Crear un directorio virtual de Fabrikam que reciba el MDN de Contoso.  
  
-   Especificar que Windows SharePoint Services no administre los directorios virtuales de Contoso y Fabrikam.  
  
-   Crear un puerto de recepción HTTP unidireccional estático para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba el mensaje AS2 que contiene el documento empresarial EDI del socio comercial. Configurar la canalización de recepción para que sea la canalización AS2EDIReceive.  
  
-   Crear un puerto de envío HTTP unidireccional dinámico para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envíe el MDN que responde al mensaje AS2 recibido.  
  
    > [!NOTE]
    >  Este puerto de envío se suscribe al MDN según la propiedad EdiIntAS.IsAS2AsynchronousMDN (que se ha establecido como True mediante la canalización AS2EdiReceive) y los tokens de correlación. El puerto de envío debe ser dinámico de modo que envíe el MDN a la dirección que figura en la línea Receipt-Delivery-Notification del encabezado del mensaje.  
  
-   Crear un puerto de envío de archivo unidireccional estático para enrutar la carga EDI (en formato XML) a un carpeta local. Crear la carpeta local.  
  
-   Crear una entidad (socio comercial) para Fabrikam y Contoso.  
  
-   Crear un perfil de negocio para cada una de las entidades comerciales.  
  
-   Crear un acuerdo AS2 entre los perfiles de negocio de Fabrikam y Contoso. El acuerdo AS2 contendría las propiedades para enviar un mensaje AS2 y recibir un MDN asincrónico en respuesta.  
  
-   Crear un acuerdo X12 entre los perfiles de negocio de Fabrikam y Contoso para recibir mensajes X12.  
  
-   Probar la solución con la utilidad del remitente de HTTP que se envía como parte de los archivos del tutorial de AS2. Esta utilidad envía un mensaje AS2 de prueba que contiene un intercambio EDI a través del transporte AS2. Esta utilidad envía un mensaje AS2 de prueba que contiene el intercambio EDI mediante el transporte AS2 (X12_00401_864.edi, también enviado con el tutorial de AS2). El remitente de HTTP y el mensaje de prueba usado para este tutorial son iguales que las versiones enviadas para el tutorial.  
  
### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  
  
##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj.  
  
    > [!NOTE]
    >  Este proyecto, que se envía para el tutorial de AS2, incluye un esquema 864 para que se utilice con el mensaje de prueba.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
2.  Haga clic en el **esquemas** del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. Haga clic en el **firma** ficha en el Diseñador de proyectos, compruebe el **firmar el ensamblado** casilla de verificación y en la lista desplegable, seleccione **New** y proporcione los valores necesarios para crear un archivo de clave de nombre seguro. Guarde los cambios y cierre la ventana de propiedades del proyecto.  
  
3.  Genere e implemente Schemas.btproj.  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>Para habilitar el filtro ISAPI de BTS  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
    > [!TIP]
    >  Según el sistema operativo, la opción Herramientas administrativas puede no estar disponible en el menú Inicio. En tales casos, haga clic en **iniciar**, haga clic en **ejecutar**y escriba `inetmgr` para abrir el Administrador de Internet Information Services (IIS).  
  
2.  Seleccione la entrada de servidor Web raíz y en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en el panel Acciones haga clic en **Agregar asignación de Script**.  
  
    > [!NOTE]
    >  La configuración de la asignación de script en el nivel de servidor web hará que esta asignación se aplique a todos los sitios web secundarios. Si desea restringir la asignación a un sitio Web o una carpeta Virtual específico, seleccione el sitio de destino o la carpeta en lugar del servidor Web.  
  
3.  En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.  
  
4.  En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive. Seleccione BtsHttpReceive.dll y haga clic en **Aceptar**.  
  
5.  Escriba `BizTalk HTTP Receive` en el `Name` campo y, a continuación, haga clic en **restricciones de solicitudes**.  
  
6.  En el cuadro de diálogo restricciones de solicitudes, seleccione la **verbos** ficha y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  
  
7.  En el **acceso** ficha, seleccione **Script** y, a continuación, haga clic en **Aceptar**.  
  
8.  Haga clic en **Aceptar** y cuando se le pida que permita la extensión ISAPI, haga clic en **Sí**.  
  
##### <a name="to-configure-the-contoso-web-page"></a>Para configurar la página Web de Contoso  
  
1.  En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  
  
2.  En el **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.  
  
3.  Seleccione **grupos de aplicaciones**, en la vista características seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el **acciones** panel.  
  
4.  En el **configuración avanzada** cuadro de diálogo, seleccione **identidad** y, a continuación, haga clic en el **puntos suspensivos (...)**  botón.  
  
5.  En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.  
  
6.  Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.  
  
7.  En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** nodo y, a continuación, seleccione **Agregar aplicación**.  
  
8.  En el **Agregar aplicación** diálogo cuadro, escriba **Contoso** en el **Alias** cuadro de texto y, a continuación, haga clic en **seleccione**.  
  
9. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
10. Para el **ruta de acceso física**, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.  
  
11. Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
12. En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  
  
13. En el **autenticación** página, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>Para configurar la página Web de Fabrikam  
  
1.  En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** nodo y, a continuación, seleccione **Agregar aplicación**.  
  
2.  En el **Agregar aplicación** diálogo cuadro, escriba **Fabrikam** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
3.  En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
4.  Para el **ruta de acceso física**, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam.  
  
5.  Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
6.  En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  
  
7.  En el **autenticación** página, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>Para especificar que Windows SharePoint Services no administra su directorio virtual  
  
1.  Si Windows SharePoint Services está instalado en el equipo, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint 3.0**.  
  
    > [!NOTE]
    >  Este procedimiento es necesario si Windows SharePoint Server está instalado en el mismo equipo en el que está configurando el tutorial. En ese caso, debe especificar que Windows SharePoint Server no esté administrando su directorio virtual de ISS.  
  
2.  En el **Administración Central** página, en **Administración Central**, haga clic en **Application Management**.  
  
3.  En el **administración de aplicaciones** página, haga clic en **definir rutas administradas**.  
  
4.  En el **definir rutas administradas** página, en **agregar una nueva ruta de acceso**, en la **ruta de acceso** texto cuadro, escriba **Contoso**. En **tipo**, haga clic en **ruta excluida**y, a continuación, haga clic en **Aceptar**.  
  
5.  Repita el paso 4 para el directorio virtual de Fabrikam.  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-interchange-over-as2-from-fabrikam"></a>Para crear un puerto de recepción para recibir el intercambio EDI a través de AS2 desde Fabrikam  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
2.  Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  
  
3.  Haga clic en **Nueva**.  
  
4.  Nombre de la ubicación de recepción, seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
5.  Para **directorio Virtual más extensión ISAPI**, escriba `/Contoso/BTSHTTPReceive.dll`.  
  
6.  Seleccione el **suspender solicitudes con errores** casilla de verificación y haga clic en **Aceptar**.  
  
7.  Para **canalización de recepción**, seleccione **AS2EDIReceive**.  
  
8.  Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
9. En el **ubicaciones de recepción** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
##### <a name="to-create-a-dynamic-send-port-to-send-the-mdn-to-fabrikam"></a>Para crear un puerto de envío dinámico para enviar el MDN a Fabrikam  
  
1.  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional dinámico**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  
  
3.  Para **canalización de envío**, seleccione **AS2Send**.  
  
4.  En el árbol de consola, seleccione **filtros**. Para **propiedad**, escriba **EdiIntAS.IsAS2AsynchronousMDN**; para **operador**, escriba  **==** ; y para **Valor** , escriba **True**.  
  
5.  Haga clic en **Aceptar**.  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>Para crear un puerto de envío con el fin de enviar la carga EDI a una carpeta local  
  
1.  En el Explorador de Windows, cree una carpeta local de Contoso con el nombre **EDI_to_Contoso** para enviar la carga EDI.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** nombre al puerto de envío, por ejemplo, cuadro de diálogo **Send_Payload**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
4.  En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, busque y seleccione el **EDI_to_Contoso** carpeta que creó en el paso 1. Deje **nombre de archivo** como **%MessageID%.xml**. Haga clic en **Aceptar**.  
  
5.  Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
6.  Haga clic en **filtros** en el árbol de consola. Para **propiedad**, escriba **BTS. MessageType**. Para **operador**, escriba  **==** . Para **valor**, especifique el tipo de mensaje para el mensaje, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
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
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo AS2 entre los dos perfiles de negocio  
  
1.  Haga clic en **Fabrikam_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **AS2**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo AS2 unidireccional.  
  
6.  En el **General** ficha la **propiedades generales** página, en la **configuración de Host común** sección, seleccione **activar informes**.  
  
7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  
  
    1.  En el **identificadores** página, escriba los valores para **AS2-de** y **AS2-a**. Para **AS2-de**, escriba `Fabrikam`. Para **AS2 - To**, escriba `Contoso`.  
  
    2.  En el **validación** página, seleccione la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** casilla de verificación  
  
    3.  En el **confirmaciones (MDN)** página, realice lo siguiente:  
  
        1.  Seleccione el **solicitar MDN** casilla de verificación.  
  
        2.  Asegúrese de que el **solicitar MDN firmado** casilla de verificación está desactivada.  
  
        3.  Seleccione el **solicitar MDN asíncrono** casilla de verificación.  
  
        4.  En el **Receipt-Delivery-Option (URL)** texto cuadro, escriba `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.  
  
8.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **AS2-de** y **AS2-a**.  
  
    1.  En el **identificadores** página, escriba los valores para **AS2-de** y **AS2-a**. Para **AS2-de**, escriba `Contoso`. Para **AS2 - To**, escriba `Fabrikam`.  
  
9. Haga clic en **Aplicar**.  
  
10. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo X12 entre los dos perfiles de negocio  
  
1.  Haga clic en **Fabrikam_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
3.  Desde el **protocolo** lista desplegable, seleccione **X12**.  
  
4.  En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **Contoso**.  
  
5.  En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **Contoso_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha sirve para configurar un acuerdo X12 unidireccional.  
  
6.  En el **General** ficha la **propiedades generales** página, en la **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **almacenar carga de mensaje para informes**.  
  
7.  Realizar las tareas siguientes en el **Fabrikam -> Contoso** ficha.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Coincidirá con los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado de intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador de receptor y el identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
  
        > [!NOTE]
        >  En este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **7654321**, **ISA7** a **ZZ** , y **ISA8** a **1234567**.  
  
    2.  En el **validación** página en el **configuración de intercambio** sección, asegúrese de que **comprobar isa13 duplicados** opción está desactivada.  
  
        > [!NOTE]
        >  Borrar el **comprobar isa13 duplicados** propiedad le permite recibir varias instancias del mismo mensaje.  
  
    3.  Si está usando uno de los esquemas estándar incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], en la **configuración de Host Local** página en el **configuración del conjunto de transacciones** sección, seleccione el espacio de nombres del esquema que se va a usarse para procesar el intercambio entrante.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Activar la casilla en la columna Predeterminado.|  
        |**Target Namespace**|Seleccione `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`.|  
  
        > [!NOTE]
        >  El establecimiento de las propiedades permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determine el esquema que se va a utilizar en el procesamiento del intercambio 850 entrante. Si un intercambio tiene los valores de GS02 y ST01 que se escriben en una línea de la cuadrícula, se utilizará el espacio de nombres de destino para la misma línea con el fin de determinar el esquema que se va a utilizar.  
  
    4.  En el **sobres** página en el **configuración del conjunto de transacciones** sección, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Seleccione **predeterminado**. **Nota:** al seleccionar esta fila como valor predeterminado, los valores de **GS1**, **GS2**, **GS3**, **GS7**y **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el Mensaje.|  
        |**Tipo de transacción**|Seleccione el tipo de mensaje del mensaje de prueba, por ejemplo, **864 – Text Message**.|  
        |**Versión y lanzamiento**|Escriba **00401**.|  
        |**Espacio de nombres de destino**|Seleccione **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.|  
        |**GS1**|Compruebe que está seleccionado el tipo de mensaje del mensaje de prueba, por ejemplo, **TX - Text Message (864)**.|  
        |**GS2**|Escriba **01**.|  
        |**GS3**|Escriba **7654321**.|  
        |**GS4**|Seleccionar el formato de fecha que desee. Seleccione **SSAAMMDD**. **Nota:** tiene que seleccionar el valor en la lista desplegable, no basta con hacer clic en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente.|  
        |**GS5**|Seleccione el formato de hora que desee. Seleccione **HHMMSSdd**.|  
        |**GS7**|Seleccione **T - Transportation Data Coordinating Committee (TDCC)**.|  
        |**GS8**|Compruebe que la versión de EDI se ha especificado como **00401**.|  
  
8.  Realizar las tareas siguientes en el **Contoso -> Fabrikam** ficha.  
  
    > [!NOTE]
    >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **ISA5**, **ISA6**, **ISA7**, y **ISA8**.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        > [!NOTE]
        >  En este tutorial, establezca **ISA5** a **ZZ**, **ISA6** a **1234567**, **ISA7** a **ZZ** , y **ISA8** a **7654321**.  
  
9. Haga clic en **Aplicar**.  
  
10. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  
  
##### <a name="to-test-the-solution"></a>Para probar la solución  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el proyecto Sender.csproj en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.  
  
2.  En HttpSender.cs, asegúrese de no comentar la línea siguiente (inmediatamente debajo de la línea de comentario //Request Asynchronous MDN):  
  
    ```  
    Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
    ```  
  
3.  Asegúrese de comentar la siguiente línea (inmediatamente debajo de la línea de comentario //Request Synchronous MDN):  
  
    ```  
    Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
    ```  
  
4.  Genere este proyecto.  
  
5.  En el Explorador de Windows, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial. Abra X12_00401_864.edi en el Bloc de notas. Elimine la línea que define el encabezado Disposition-Notification-Options y, a continuación, guarde el archivo.  
  
6.  En el Explorador de Windows, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug y ejecute **Sender.exe**.  
  
    > [!NOTE]
    >  La ejecución de Sender.exe en esta instancia envía el mensaje X12_00401_864.edi al directorio virtual de Contoso (la ubicación de recepción de HTTP de BTS).  
  
7.  Abra la carpeta local de Contoso creada para enviar la carga EDI (\EDI_to_Contoso). Compruebe que haya un archivo XML en la carpeta. Abra el archivo XML y compruebe que contiene un conjunto de transacciones 864.  
  
8.  Abra la carpeta local de Fabrikam a la que se devuelve el MDN. En el Explorador de Windows, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam. Abra el archivo de mensajes en el Bloc de notas y compruebe el MDN. Compruebe que en el MDN AS2-From es Contoso y AS2-To es Fabrikam.  
  
9. Abra el mensaje de prueba X12_00401_864.edi en el Bloc de notas y compruebe que el conjunto de transacciones en el mensaje de salida en la carpeta local \EDI_to_Contoso corresponde con el conjunto de transacciones en el mensaje de entrada X12_00401_864.edi.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)