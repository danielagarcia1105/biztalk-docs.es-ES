---
title: 'Tutorial: Usar el modo de seguridad de mensajes con el adaptador WCF-NetTcp | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f6e892-34ce-4132-8867-54cc3bbfe507
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850d0ee715984c7465063addd778828c727e0233
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010613"
---
# <a name="walkthrough-using-the-message-security-mode-with-the-wcf-nettcp-adapter"></a>Tutorial: Usar el modo de seguridad de mensajes con el adaptador WCF-NetTcp
  
> [!NOTE]
>  Para obtener más información acerca de los adaptadores, vea [adaptadores de BizTalk Server](../core/adapters-in-biztalk-server.md).  
  
## <a name="introduction"></a>Introducción
  
 En este tutorial se muestra cómo configurar el adaptador de WCF-NetTcp para que use el modo de seguridad de mensaje [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)], que usa la especificación WS-Security como ayuda para proteger los mensajes que el adaptador transmite. Esta especificación describe las mejoras en el protocolo de mensajería SOAP para conseguir confidencialidad, integridad y autenticación en el nivel de mensaje SOAP. En el modo de seguridad de mensaje, es necesario especificar el certificado de servicio para operaciones como, por ejemplo, el cifrado y descifrado y la firma y verificación según las combinaciones del modo de seguridad.  
  
 El adaptador de WCF-NetTcp usa el enlace NetTcpBinding para la comunicación entre los clientes [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y los servicios remotos de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP. Permite publicar las orquestaciones y los esquemas como servicios de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y también proporciona la capacidad de que una orquestación consuma servicios WCF externos. Este adaptador usa el transporte TCP y los mensajes tienen una codificación binaria. El adaptador de WCF-NetTcp consta de un adaptador de envío y un adaptador de recepción.  
  
 En este tutorial se muestra cómo crear certificados para el modo de seguridad de mensaje con el Servicio de certificados de Active Directory. Creará certificados para el servidor y el cliente y, luego, configurará una ubicación de recepción de WCF-NetTcp para usar los certificados en modo de seguridad de mensaje. Mediante el uso de un cliente [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], enviará mensajes a dicha ubicación de recepción en estado cifrado según la sintaxis y el procesamiento de cifrado de XML.  
  
 Cuando concluya el tutorial, comprenderá cómo se realizan las tareas siguientes:  
  
-   Use el Servicio de certificados de Active Directory para crear una solicitud de certificado y completar el proceso mediante la emisión del certificado.  
  
-   En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], configure el adaptador de WCF-NetTcp para que use el modo de seguridad de mensaje.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo los pasos de este ejemplo Asegúrese de que su entorno instala los siguientes requisitos previos;  
  
-   El equipo que genera los ensamblados y ejecuta el proceso de implementación tanto el equipo que ejecuta el ejemplo requieren Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]y Microsoft BizTalk Server.  
  
-   El equipo que se usa para generar los ensamblados y ejecutar el proceso de implementación requiere Microsoft Visual Studio.  
  
-   El equipo que ejecuta el ejemplo requiere los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y las herramientas de administración de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Estas son opciones para instalar durante la instalación de Microsoft BizTalk Server.  
  
-   En los equipos que use para realizar las tareas administrativas, debe ejecutar una cuenta de usuario que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar los parámetros de aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esta cuenta de usuario también debe ser miembro del grupo de administradores local para la implementación de la aplicación, la administración de las instancias de host y otras tareas que puedan ser necesarias.  
  
-   En cualquier equipo que requiera [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] capacidad, complete el procedimiento de instalación única para la [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] ejemplos en [http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510).  
  
-   En el equipo que ejecuta el ejemplo e importa un enlace o un archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de que el host no es un host de confianza. De lo contrario, se producirá un error en la importación.  
  
-   En el equipo donde se ejecuta en el ejemplo, asegúrese de que están instalados los Servicios de certificados de Active Directory.  
  
-   Debe descargar el código del tutorial y extraerlo en el equipo.  Este tutorial es una parte de todo el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] paquete de tutoriales del adaptador. Puede descargar el archivo **WCFAdapterWalkthroughs.exe** desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Developer Center en [http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140).  
  
## <a name="create-the-certificates-for-this-walkthrough"></a>Crear los certificados para este tutorial  
  
1.  En esta sección solicitará certificados de servicio y cliente, emitirá los certificados y los instalará en los almacenes adecuados. Los Servicios de certificados de Active Directory se usan para crear un certificado con una cadena de certificados de confianza. Si no ha instalado los servicios de certificados de Active Directory como parte de los requisitos previos, instale los servicios de certificados de Active Directory en el equipo. Si ya están instalados, vaya al paso 2.  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **el administrador del servidor**.  
  
    2.  En el **el administrador del servidor** nodo, haga clic en **agregar**y, a continuación, haga clic en **Roles**.  
  
    3.  Se abrirá la **antes de comenzar** cuadro de diálogo para la **Asistente para agregar funciones**. Haga clic en **Siguiente**.  
  
    4.  En el **seleccionar Roles de servidor** , seleccione **servicios de certificados de Active Directory**, haga clic en **siguiente**y, a continuación, siga las que aparecen en pantalla instrucciones para completar la instalación.  
  
2.  Cree una solicitud de certificado para la autenticación del servicio. Para ello:  
  
    1.  En Internet Explorer, visite el sitio Web `http://localhost/certsrv`. En el **bienvenida** página, haga clic en **solicitar un certificado**y, a continuación, haga clic en **solicitud de certificado avanzada** en el **solicitar un certificado** página.  
  
        > [!NOTE]
        >  Cuando se usa [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] como la entidad de certificación y solicitar un certificado desde un [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] equipo, puede obtener el error **"para completar la inscripción de certificados, el sitio Web de la entidad emisora debe configurarse para usar HTTPS autenticación"**. Si se produce este error, el sitio Web de inscripción debe configurarse con un certificado de Web (SSL). Consulte estos vínculos para obtener más información sobre cómo llevar a cabo esta tarea:  
        >   
        >  [AD CS: Inscripción Web](http://technet.microsoft.com/library/cc732517.aspx)  
        >   
        >  [Instrucciones de instalación de certificado de servidor IIS](http://msdn.microsoft.com/library/ms751408.aspx)  
  
    2.  En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  
  
    3.  En el **solicitud de certificado avanzada** página, escriba `localhost` en el **nombre** cuadro de texto, seleccione **certificado de autenticación de servidor** desde el  **Tipo de certificado necesario** lista desplegable y, a continuación, haga clic en **enviar**.  
  
3.  Cree una solicitud de certificado para la autenticación del cliente. Para ello:  
  
    1.  En Internet Explorer, visite el sitio Web `http://localhost/certsrv`. En el **bienvenida** página, haga clic en **solicitar un certificado**y, a continuación, haga clic en **solicitud de certificado avanzada** en el **solicitar un certificado** página.  
  
    2.  En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.  
  
    3.  En el **solicitud de certificado avanzada** página, escriba `contoso` en el **nombre** cuadro de texto, seleccione **certificado de autenticación de cliente** desde el  **Tipo de certificado necesario** lista desplegable y, a continuación, haga clic en **enviar**.  
  
    > [!NOTE]
    >  El certificado de autenticación de cliente se utiliza si se ejecuta BizTalk Server en el equipo que no sea el controlador de dominio. Esto se configurará en el cuadro de diálogo de propiedades del adaptador.  
  
4.  Emita los certificados utilizando la consola de administración de la entidad emisora de certificados como se indica a continuación:  
  
    1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **entidad de certificación**.  
  
    2.  En el **entidad de certificación** management console, expanda el nombre de la entidad de certificación y, a continuación, haga doble clic en **peticiones pendientes**.  
  
    3.  En el panel derecho de la **entidad de certificación** consola de administración, haga clic en la solicitud para el certificado de autenticación de servicio, seleccione **todas las tareas**y, a continuación, haga clic en **problema** .  
  
    4.  En el panel derecho de la **entidad de certificación** consola de administración, haga clic en la solicitud para el certificado de autenticación de cliente, seleccione **todas las tareas**y, a continuación, haga clic en **problema** .  
  
    5.  Cerrar la **entidad de certificación** consola de administración.  
  
5.  Instale los certificados emitidos en el equipo. Para ello:  
  
    1.  En Internet Explorer, visite el sitio Web `http://localhost/certsrv`.  
  
    2.  En el **bienvenida** página, haga clic en **ver el estado de una solicitud de certificado pendiente**.  
  
    3.  En el **ver el estado de una solicitud de certificado pendiente** página, haga clic en el certificado de autenticación de servidor.  
  
    4.  En el **certificado emitido** página, haga clic en **instalar este certificado**.  
  
    5.  En Internet Explorer, visite el sitio Web `http://localhost/certsrv`.  
  
    6.  En el **bienvenida** página, haga clic en **ver el estado de una solicitud de certificado pendiente**.  
  
    7.  En el **ver el estado de una solicitud de certificado pendiente** página, haga clic en el certificado de autenticación de cliente.  
  
    8.  En el **certificado emitido** página, haga clic en **instalar este certificado**.  
  
6.  Asegúrese de que los certificados emitidos están instalados correctamente. Para ello:  
  
    1.  Abra Microsoft Management Console (MMC). Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo `mmc`y, a continuación, haga clic en **Aceptar**.  
  
    2.  En MMC, en el **archivo** menú, haga clic en **agregar o quitar complemento**.  
  
    3.  En el cuadro de diálogo **Agregar o quitar complemento** , haga clic en **Agregar**.  
  
    4.  En el **Add Standalone Snap-in** cuadro de diálogo, seleccione **certificados** desde el **un complemento independiente disponible** lista y, a continuación, haga clic en **agregar**.  
  
    5.  En el **complemento certificado** cuadro de diálogo, seleccione la **mi cuenta de usuario** opción y, a continuación, haga clic en **finalizar**.  
  
    6.  Cierre todos los cuadros de diálogo abiertos.  
  
    7.  En la consola de MMC, en la ventana raíz de consola, expanda **certificados - usuario actual**, expanda **Personal**, expanda **certificados**y, a continuación, asegúrese de que los certificados que usted instalado en el paso anterior se muestran.  
  
## <a name="create-the-biztalk-application-for-this-walkthrough"></a>Crear la aplicación de BizTalk para este tutorial  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, haga clic en **aplicaciones**, seleccione **New**y, a continuación, haga clic en **aplicación** .  
  
3.  En el **propiedades de la aplicación** cuadro de diálogo, en la **General** , escriba `WcfMessageSecurity`y, a continuación, haga clic en **Aceptar**.  
  
4.  Cree una ubicación de recepción mediante el adaptador de WCF-NetTcp para la aplicación de BizTalk de la manera siguiente:  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WcfMessageSecurity**, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en  **Unidireccional puerto de recepción.**  
  
    2.  En el **propiedades de puerto de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WcfMessageSecurity.OrderRequest.Receive`y, a continuación, haga clic en **Aceptar**. El nombre de este puerto de recepción es totalmente arbitrario pero tiene sentido lógico.  
  
    3.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción**, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**. El cliente [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] enviará un mensaje de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] a esta ubicación de recepción. Seleccione el **WcfMessageSecurity.OrderRequest.Receive** puerto de recepción y, a continuación, haga clic en **Aceptar**.  
  
    4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** cuadro de texto, escriba `WcfMessageSecurity.OrderRequest.Receive.NetTcp`. El nombre de esta ubicación de recepción es totalmente arbitrario pero tiene sentido lógico.  
  
    5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **WCF-NetTcp** en la lista desplegable lista y, a continuación, haga clic en **configurar**.  
  
    6.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **General** ficha la **dirección (URI)** cuadro de texto, escriba `net.tcp://localhost/WcfMessageSecurity`.  
  
    7.  En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo la **seguridad** ficha, seleccione **mensaje** desde el **modo de seguridad** desplegable enumerar y, a continuación, seleccione **certificado** desde el **tipo de credencial de cliente de mensaje** lista desplegable. Esto configura el adaptador de WCF-NetTcp para que use el modo de seguridad de mensaje.  
  
    8.  Configure el certificado del servicio para usarlo con el modo de seguridad de mensaje. En el **propiedades de transporte de WCF-NetTcp** cuadro de diálogo, en la **certificado de servicio** sección, haga clic en **examinar**. En el **certificado de servicio seleccione** cuadro de diálogo, seleccione el certificado de autenticación de servidor instalado en el procedimiento anterior y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo y guardar los cambios.  
  
    9. Cierre todos los cuadros de diálogo abiertos.  
  
        > [!NOTE]
        >  Para autenticar los certificados de cliente con los adaptadores de recepción de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], la cadena de certificados de CA para certificados de cliente debe instalarse en el almacén de certificados de las entidades emisoras raíz de confianza del equipo en el que se ejecutan las instancias de host para los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]. Dado que este tutorial presupone que el servicio de certificados se encuentra instalado en el mismo equipo que el cliente [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] y los adaptadores de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], no es necesario instalar la cadena de certificados de CA en el equipo.  
  
5.  Cree un puerto de envío de archivos para la aplicación de BizTalk. Se trata de la ubicación donde la orquestación que representa el Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] enviará el mensaje de salida de la solicitud de pedido.  
  
    1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **WcfMessageSecurity**, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **estático Puerto de envío unidireccional.**  
  
    2.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **General** ficha la **nombre** cuadro de texto, escriba `WcfMessageSecurity.OrderRequest.Send.FILE`.  
  
    3.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **archivo** en la lista desplegable y, a continuación, Haga clic en **configurar**.  
  
    4.  En el **propiedades de transporte de archivo** cuadro de diálogo la **General** , escriba `C:\WCFMessageSecurity\OrderRequestOut` en el **carpeta de destino** cuadro de texto y, a continuación, haga clic en **Aceptar** .  
  
    5.  En el **propiedades de puerto de envío** cuadro de diálogo, en la **filtros** ficha, seleccione **BTS. ReceivePortName** para el **propiedad** , escriba `WcfMessageSecurity.OrderRequest.Receive` para el **valor** campo y, a continuación, haga clic en **Aceptar**. Esta expresión de filtro enruta entrante [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensajes desde el cliente en el **WcfMessageSecurity.OrderRequest.Receive** puerto de recepción para este puerto de envío.  
  
## <a name="test-the-wcf-client-against-the-biztalk-application"></a>Probar al cliente WCF en la aplicación de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **WcfMessageSecurity**y, a continuación, haga clic en **iniciar**. En el **iniciar** cuadro de diálogo, haga clic en **iniciar**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **configuración de plataforma**, expanda **instancias de Host**, haga clic en **BizTalkServerApplication** u otro procede de la instancia de host y, a continuación, haga clic en **reiniciar**.  
  
3.  Cree una carpeta denominada **C:\WCFMessageSecurity** para la carpeta de trabajo para este tutorial. Extraiga los archivos del tutorial en esta carpeta.  
  
4.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **WcfMessageSecurity.sln** un archivo en el **C:\WCFMessageSecurity** carpeta.  
  
5.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, expanda **WcfClient**y, a continuación, abra **Program.cs** para revisar.  
  
    -   El cliente envía un mensaje a la ubicación de recepción WCF-NetTcp que creó en el procedimiento anterior.  
  
    -   El cliente crea un canal con el **NetTcpBinding**y, a continuación, configura el enlace para usar certificados para el tipo de credencial de cliente.  
  
    -   El cliente configura el comportamiento del extremo para que use el certificado de autenticación del cliente que instaló en el procedimiento anterior para la autenticación del cliente.  
  
    -   La clase **programa**, implementa el **IClientMessageInspector** y **IEndpointBehavior** interfaces para mostrar la salida [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] mensajes desde este cliente en un símbolo del sistema.  
  
6.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en el **WcfMessageSecurity** solución y, a continuación, haga clic en **volver a generar**.  
  
7.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **depurar** menú, haga clic en **iniciar sin depurar** para ejecutar WcfClient para enviar un mensaje de WCF-NetTcp ubicaciones de recepción. Se abrirá un símbolo del sistema para mostrar el resultado de la ejecución.  
  
    1.  En el símbolo del sistema, revise el mensaje de solicitud de pedido. Preste atención a la **OrderId** campo y la estructura del mensaje.  
  
    2.  En el símbolo del sistema, vaya a la `C:\WCFMessageSecurity\OrderRequestOut` carpeta y, a continuación, asegúrese de que el mensaje de solicitud de pedido enviado por el [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] aparece de cliente.  
  
    3.  Cierre el símbolo del sistema.