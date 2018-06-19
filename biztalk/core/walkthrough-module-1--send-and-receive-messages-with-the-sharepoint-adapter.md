---
title: 'Tutorial: Módulo 1: enviar y recibir mensajes con Windows SharePoint Services adaptador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8e83297233c4f8ac51ad90f488437a6c259691a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010509"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a>Tutorial: Módulo 1 – enviar y recibir mensajes con el adaptador de Windows SharePoint Services
En este tutorial se muestra cómo configurar Windows SharePoint Services y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que pueda enviar y recibir mensajes mediante el adaptador de Windows SharePoint Services y el enrutamiento basado en contenido (CBR). El enrutamiento por contenidos elimina la necesidad de suscribir mensajes para los mensajes enlazados de forma determinista a puertos específicos. Asimismo, proporciona flexibilidad adicional para los usuarios que deseen enrutar los mensajes según las propiedades del sobre o simplemente según las propiedades de configuración del puerto de recepción. Para obtener una introducción al adaptador de Windows SharePoint Services, vea [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe tener una implementación de servidor único con una instalación completa de BizTalk Server que se ejecutan en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].  
  
 Para obtener información acerca de cómo utilizar el adaptador de Windows SharePoint Services en una implementación multiservidor, vea [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).  
  
## <a name="configure-windows-sharepoint-services"></a>Configurar Windows SharePoint Services  
 En este procedimiento, se creará un sitio Web de nivel superior de SharePoint que contiene tres bibliotecas de documentos. El adaptador de Windows SharePoint Services utiliza estas bibliotecas para trasladar un mensaje a una biblioteca de destino desde una biblioteca de origen. Este mensaje también se archiva en una biblioteca de documentos. Este procedimiento resulta necesario para proporcionar el sitio de Windows Sharepoint Services al que tiene acceso el adaptador de Windows Sharepoint Services en este tutorial, así como para definir derechos de usuario que hagan posible el acceso a este sitio.  
  
#### <a name="create-a-windows-sharepoint-services-site"></a>Crear un sitio de Windows SharePoint Services  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint.**  
  
2.  En **configuración del servidor Virtual**, haga clic en **crear un sitio Web de nivel superior**.  
  
3.  En **lista de servidores virtuales**, seleccione el sitio Web que ha instalado el adaptador de Windows SharePoint Services en. Por ejemplo, `Default Web Site`.  
  
4.  En el **dirección del sitio Web** sección, en la **nombre de dirección URL** , escriba `WSSAdapterWalkthrough`.  
  
5.  En el **propietario de la colección de sitios** sección, en la **campo de nombre de usuario,** escriba un nombre de usuario. El usuario será el propietario del sitio web y no necesita permisos especiales para usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
6.  En el **propietario de la colección de sitios** sección, en la **correo electrónico** , escriba una dirección de correo electrónico.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **sitio de nivel superior correctamente creado** página, haga clic en nuevo sitio Web de nivel superior que acaba de crear. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
9. Seleccione el **equipo sitio** plantilla de la lista de plantillas y, a continuación, haga clic en **Aceptar**. De este modo se abre la página principal del sitio Web del equipo.  
  
#### <a name="create-a-source-document-library"></a>Crear una biblioteca de documentos de “origen”  
  
1.  En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.  
  
2.  En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.  
  
3.  En el **nombre y una descripción** sección, en la **campo nombre,** tipo `Source`.  
  
4.  En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.  
  
5.  En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.  
  
6.  Haga clic en **Crear**. Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.  
  
#### <a name="create-a-destination-document-library"></a>Crear una biblioteca de documentos de "destino"  
  
1.  En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.  
  
2.  En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.  
  
3.  En el **nombre y una descripción** sección, en la **campo nombre**, tipo `Destination`.  
  
4.  En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.  
  
5.  En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.  
  
6.  Haga clic en **Crear**. Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.  
  
#### <a name="create-an-archive-document-library"></a>Crear una biblioteca de documentos de "archivo"  
  
1.  En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **crear**.  
  
2.  En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.  
  
3.  En el **nombre** y sección de descripción, en la **campo nombre**, tipo `Archive`.  
  
4.  En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.  
  
5.  En el **plantilla de documento** sección, en la **plantilla de documento** lista desplegable, seleccione `None`.  
  
6.  Haga clic en **Crear**. Se creará la biblioteca de documentos y tendrá lugar una redirección a la biblioteca vacía.  
  
7.  Cierre el sitio web de `WSSAdapterWalkthrough`.  
  
8.  Cerrar la **Administración Central de SharePoint** sitio Web.  
  
#### <a name="configure-windows-security"></a>Configurar seguridad de Windows  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  En el árbol de consola, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.  
  
3.  Haga clic en el **Hosts habilitados de SharePoint** grupo, haga clic en **agregar al grupo**y, a continuación, haga clic en **agregar**.  
  
4.  En el **cuadro de diálogo Seleccionar usuarios, equipos o grupos**, en **escriba los nombres de objeto para seleccionar**, escriba el nombre de la cuenta que configuró la instancia de Host de BizTalk Server para ejecutarse en y, a continuación, haga clic en **Aceptar**.  
  
5.  En el árbol de consola, expanda **servicios y aplicaciones**y, a continuación, haga clic en **Services**.  
  
6.  Haga clic en **servicio de BizTalk grupo: < BizTalk_Host_Name >** y, a continuación, haga clic en **reiniciar**.  
  
    > [!NOTE]
    >  <BizTalk_Host_Name> es el nombre del host. De forma predeterminada, es `BizTalkServerApplication`.  
  
    > [!NOTE]
    >  La suscripción no tiene ningún efecto hasta que se reinicie el servicio.  
  
7.  Cerrar **administración de equipos**.  
  
#### <a name="configure-sharepoint-security"></a>Configurar seguridad de SharePoint  
  
1.  Abra un explorador web y vaya a la dirección URL del sitio creado. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En la página principal del sitio Web del equipo, en la barra de navegación superior, haga clic en **configuración del sitio**.  
  
3.  En **administración**, haga clic en **administrar usuarios**.  
  
4.  Haga clic en **Agregar usuarios**.  
  
5.  En **paso 1: elegir usuarios**, escriba el nombre de la cuenta que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instancia de Host se ejecuta bajo.  
  
6.  En **paso 2: elegir grupos de sitio**, seleccione la **lector** y **colaborador** casillas de verificación.  
  
7.  Haga clic en **Siguiente**.  
  
8.  Desactive el **enviar el correo electrónico siguiente para informar a los usuarios ahora que han sido agregados** casilla de verificación y, a continuación, haga clic en **finalizar**.  
  
9. Cierre el sitio web de `WSSAdapterWalkthrough`.  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a>Crear y configurar los puertos de BizTalk Server  
 En este procedimiento se crearán y configurarán los puertos de recepción, las ubicaciones de recepción y los puertos de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el adaptador de Windows SharePoint Services. Estos puertos son puntos de entrada y salida de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para documentos que recibe y envía el adaptador de Windows Sharepoint Services.  
  
#### <a name="create-the-receive-port"></a>Crear el puerto de recepción  
  
1.  Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**  
  
2.  Expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**, haga clic en **depuertosderecepción**, haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional...**  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo **General**, tipo `FromSource` en el **nombre** campo.  
  
4.  Haga clic en **Aceptar**.  
  
#### <a name="create-the-receive-location"></a>Crear la ubicación de recepción  
  
1.  En el **consola de administración de BizTalk**, haga clic en el **ubicaciones de recepción** nodo, haga clic en **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
2.  En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione `FromSource`y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **propiedades de la ubicación de recepción** cuadro de diálogo **General**, tipo `SourceLocation` en el **nombre** campo.  
  
4.  En el **transporte** sección, en la **tipo** lista desplegable, seleccione `Windows``SharePoint``Services`.  
  
5.  Haga clic en **configurar** para configurar las propiedades de adaptador de Windows SharePoint Services.  
  
6.  En el **adaptador de puerto del servicio Web** propiedad, escriba el número de puerto del servidor virtual donde se instaló el servicio Web del adaptador de Windows SharePoint Services. De forma predeterminada, éste es el puerto 80.  
  
7.  Tipo de `Archive` en el **ubicación de archivado** propiedad.  
  
8.  Tipo de `10` en el **intervalo de sondeo** propiedad.  
  
9. Escriba la dirección URL para el sitio de SharePoint en el **dirección**punto propiedad de dirección Url del sitio. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
10. Tipo de `Source` para el **biblioteca de documentos de origen** propiedad.  
  
11. Haga clic en **Aceptar**.  
  
12. En el **propiedades de la ubicación de recepción** cuadro de diálogo, seleccione `BizTalkServerApplication` como el **controlador de recepción**.  
  
13. En el **canalización de recepción** lista desplegable, seleccione `PassThruReceive`.  
  
14. Haga clic en **Aceptar**.  
  
#### <a name="create-the-send-port"></a>Crear el puerto de envío  
  
1.  En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo, haga clic en **New**y, a continuación, haga clic en **puerto de envío unidireccional estático** .  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo **General**, tipo `SendToDestination` en el **nombre** campo.  
  
3.  En el **transporte** sección, seleccione `Windows SharePoint Services` para el tipo.  
  
4.  Haga clic en **configurar** para configurar las propiedades de adaptador de Windows SharePoint Services.  
  
5.  En el **adaptador de puerto del servicio Web** propiedad, escriba el número de puerto del servidor virtual donde se instaló el servicio Web del adaptador de Windows SharePoint Services. De forma predeterminada, éste es el puerto 80.  
  
6.  Escriba en `Destination` para el **carpeta de destino** propiedad.  
  
7.  Escriba en `PurchaseOrder1-%MessageID%.xml` para el **Filename** propiedad.  
  
8.  Establecer el **sobrescribir** propiedad `Yes`.  
  
9. Escriba la dirección URL para el sitio de SharePoint en el **dirección Url del sitio de SharePoint** propiedad. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
10. Establecer el **integración con Microsoft Office** propiedad `No`.  
  
11. Haga clic en **Aceptar**.  
  
12. En el **cuadro de diálogo de propiedades de puerto de envío**, en la **controlador de envío** lista desplegable, seleccione `BizTalkServerApplication`.  
  
13. En el **canalización de envío** lista desplegable, seleccione `PassThruTransmit`.  
  
14. Haga clic en el **filtros** ficha.  
  
15. Seleccione `WSS.InListName` en el **propiedad** campo.  
  
16. Seleccione `==` en el **operador** campo.  
  
17. Tipo de `Source` en el **valor** campo.  
  
18. Haga clic en **Aceptar**.  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a>Habilite e inicie la ubicación de recepción y el puerto de envío  
 Con estos procedimientos, se habilita la ubicación de recepción y se inicia el puerto de recepción. Este procedimiento debe completarse para permitir que el adaptador de Windows Sharepoint Services envíe y reciba mensajes a través de la ubicación de recepción y del puerto de envío especificados.  
  
#### <a name="enable-the-receive-location"></a>Habilitar la ubicación de recepción  
  
1.  En el **consola de administración de BizTalk**, haga clic en el **ubicaciones de recepción** nodo.  
  
2.  Haga clic en `SourceLocation`y, a continuación, haga clic en **habilitar**.  
  
#### <a name="start-the-send-port"></a>Iniciar el puerto de envío.  
  
1.  En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo.  
  
2.  Haga clic en `SendToDestination`y, a continuación, haga clic en **iniciar**.  
  
3.  Cerrar la **consola de administración de BizTalk**.  
  
## <a name="sending-a-message-through-the-system"></a>Enviar un mensaje a través del sistema  
 Con este procedimiento, creará un documento XML y lo cargará en el sitio Web de Windows SharePoint Services. El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino. En este procedimiento se demuestra cómo un documento se transfiere de un sitio web de Sharepoint, a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a un sitio web de Sharepoint Services mediante el adaptador de Windows Sharepoint Services.  
  
#### <a name="create-a-working-directory"></a>Crear un directorio de trabajo  
  
-   Cree un directorio en su equipo llamado **WSSAdapterWalkthrough**. Por ejemplo, `C:\WSSAdapterWalkthrough`.  
  
#### <a name="create-an-xml-file"></a>Crear un archivo XML.  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **el Bloc de notas.**  
  
2.  Escriba lo siguiente:  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  Guarde el archivo en el directorio de trabajo como `PurchaseOrder1.xml`. Por ejemplo, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`.  
  
#### <a name="upload-the-xml-file"></a>Cargar el archivo XML  
  
1.  Abra un explorador Web y desplácese a la dirección URL del sitio creado en la última tarea. Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.  
  
2.  En el lado izquierdo, bajo **documentos**, haga clic en **origen**.  
  
3.  Haga clic en **cargar documento**.  
  
4.  En el **nombre** cuadro, escriba o busque el archivo XML que creó anteriormente. Por ejemplo, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`y, a continuación, haga clic en **guardar y cerrar**. Debería poder ver el archivo en la lista.  
  
5.  Actualice la ventana del explorador. El archivo `PurchaseOrder1.xml` ya no aparece en esta biblioteca.  
  
    > [!NOTE]
    >  Es posible que tenga que actualizar el explorador varias veces ya que el intervalo de sondeo está establecido en 10 segundos.  
  
6.  En la barra de navegación superior, haga clic en **documentos y listas**.  
  
7.  En **las bibliotecas de documentos**, haga clic en **destino**.  
  
8.  En la biblioteca de documentos de destino, ahora verá el mensaje incluido en la lista. También encontrará una copia archivada en la biblioteca de documentos de archivo.  
  
    > [!NOTE]
    >  Si no aparece el mensaje en la biblioteca de documentos de destino, vea "Solucionar problemas del adaptador de Windows SharePoint Services" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="summary"></a>Resumen  
 En este tutorial ha visto cómo configurar Windows SharePoint Services y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar y recibir mensajes mediante el adaptador de Windows SharePoint Services y el enrutamiento basado en contenido (CBR).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha completado este tutorial, realice la [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) tutorial, que se expande en el trabajo que ha realizado en este tutorial y muestra también cómo integrar Office con el adaptador de Windows SharePoint Services.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Tutoriales del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-walkthroughs.md)