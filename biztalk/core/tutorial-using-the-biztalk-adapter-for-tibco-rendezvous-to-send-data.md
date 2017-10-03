---
title: 'Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para enviar datos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63540402ca8e060d26c8398af010a81eaad0a6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a>Tutorial: Uso del adaptador de BizTalk para TIBCO Rendezvous para enviar datos
Puede usar BizTalk Adapter para TIBCO Rendezvous para enviar datos a un sistema TIBCO. En este tutorial se describe un ejemplo de SDK que ilustra este proceso.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en en servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se ejecuta el adaptador para crear e implementar el ejemplo.  
  
-   En el ejemplo se utiliza una DLL que contiene las propiedades del contexto del mensaje: Microsoft.BizTalk.Adapters.TibRV.Properties.dll. Puede necesitar actualizar la referencia de la solución a esta biblioteca. Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo toma un archivo XML de una carpeta de archivos, envía el archivo a una orquestación y, luego, usa BizTalk Adapter para TIBCO Rendezvous para crear un registro en el sistema TIBCO.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo, diseñado en [!INCLUDE[vs2010](../includes/vs2010-md.md)], ilustra la funcionalidad básica del uso de BizTalk Adapter para TIBCO Rendezvous con una orquestación de BizTalk.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 La ubicación predeterminada para el ejemplo es  
  
 C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend  
  
 En la tabla siguiente se enumeran y describen los archivos del ejemplo.  
  
|**Nombre de archivo de proyecto en tiempo de ejecución**|**Descripción del archivo del proyecto en tiempo de ejecución**|  
|----------------------------------|------------------------------------------|  
|OneWaySend.btproj<br /><br /> OneWaySend.sln|Archivos de proyectos y soluciones para la aplicación.|  
|Schema.xsd<br /><br /> PropertySchema.xsd|Esquema y archivos de esquema de propiedades para la aplicación.|  
|Orchestration.odx|La orquestación usada por la aplicación.|  
|TIBCORendezvousOneWaySend.snk|Archivo de clave de nombre seguro.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a>Crear una nueva instancia del Adaptador de BizTalk para TIBCO Rendezvous  
  
1.  Inicie la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en **iniciar**, **programas**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Adaptadores**.  
  
3.  Haga clic en **adaptadores** y seleccione **New**, **adaptador...** para mostrar la **propiedades del adaptador** cuadro de diálogo.  
  
4.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCO Rendezvous**.  
  
5.  Seleccione **TIBCO Rendezvous(r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.  
  
#### <a name="create-a-biztalk-send-port"></a>Crear un puerto de envío de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  
  
2.  Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático...** para mostrar la **propiedades de puerto de envío** cuadro de diálogo.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWaySP**.  
  
4.  Seleccione el adaptador de TIBCO Rendezvous en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte** cuadro de diálogo.  
  
    > [!NOTE]
    >  Este valor es el nombre que se especificó cuando se creó el adaptador TIBCO Enterprise Message System en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
5.  Escriba valores para la **propiedades de remitente certificado**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Nombre de archivo de contabilidad|Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.|  
    |Nombre reutilizable|Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados. El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.|  
  
6.  Escriba valores para la **credenciales**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Contraseña|La contraseña para el servidor TIBCO Rendezvous.|  
    |Nombre de usuario.|El nombre de usuario para el servidor TIBCO Rendezvous.|  
  
7.  Escriba valores para la **RendezvousTransport**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Demonio|Parámetro del demonio del transporte de Rendezvous.|  
    |Red|Parámetro de red del transporte de Rendezvous.|  
    |ssNoVersion|Parámetro de servicio del transporte de Rendezvous.|  
  
     Para obtener más información acerca de las propiedades, vea [cómo establecer propiedades de transporte de TIBCO Rendezvous](../core/how-to-set-tibco-rendezvous-transport-properties.md).  
  
8.  Haga clic en **Aceptar**.  
  
9. Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.  
  
10. Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  
  
#### <a name="create-a-file-receive-port"></a>Crear un puerto de recepción de archivos  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.  
  
2.  Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional...**  para mostrar el cuadro de diálogo Propiedades de puerto de recepción.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRP**y haga clic en **Aceptar**.  
  
#### <a name="create-a-file-receive-location"></a>Crear una ubicación de recepción de archivos  
  
1.  Cree una carpeta para la ubicación de recepción de archivos que se debe supervisar, por ejemplo, C:\Filesource.  
  
2.  Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción...** para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **TIBCORndOneWayFileRL**.  
  
4.  Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  
  
5.  Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta recepción** propiedad y haga clic en **Aceptar**.  
  
6.  Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  
  
7.  Haga clic en la ubicación de recepción y haga clic en **habilitar**.  
  
#### <a name="generate-a-document-instance-from-the-schema"></a>Generar una instancia de documento a partir del esquema  
  
1.  Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **propiedades**.  
  
2.  En la ventana Propiedades, haga clic en el **nombre de archivo de instancia de salida** opción bajo el **General** sección.  
  
3.  Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.  
  
4.  Especifique una carpeta y el nombre de la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.  
  
    > [!NOTE]
    >  No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.  
  
5.  Haga clic en Schema.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.  
  
#### <a name="modify-the-generated-document-instance"></a>Modificar la instancia de documento generada  
  
1.  Abra la instancia de documento generada en un editor de texto, tal como el Bloc de notas, y edite el contenido de la instancia de documento para garantizar que los datos van a generar un registro único en el sistema TIBCO. Por ejemplo, el código siguiente muestra la primera parte del archivo de datos:  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  Guarde la instancia de documento modificada.  
  
#### <a name="build-and-deploy-the-project"></a>Generar e implementar el proyecto  
  
1.  Haga clic en el **OneWaySend** del proyecto en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
2.  Haga clic en el **implementación** ficha.  
  
3.  Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.  
  
4.  Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.  
  
#### <a name="bind-and-enlist-the-orchestration"></a>Enlazar y dar de alta la orquestación  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.  
  
2.  Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.  
  
3.  Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.  
  
4.  Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.  
  
5.  Especifique los valores adecuados para las opciones de enlace, por ejemplo:  
  
    |**Parámetro**|**Valor**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |FileReceivePort|TIBCORndOneWayFileRP|  
    |TibcoRendezvousSend|TIBCORndOneWaySP|  
  
6.  Haga clic en Aceptar.  
  
#### <a name="start-the-orchestration"></a>Iniciar la orquestación  
  
-   En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción  
  
-   Copie la instancia de documento que se creó anteriormente en la carpeta de recepción de archivos que la aplicación supervisa.  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a>Comprobar que el sistema TICBO está actualizado  
  
-   Use la interfaz web de TIBCO para comprobar que el registro se creó a partir de los datos del archivo XML.  
  
 Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:  
  
1.  El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.  
  
2.  La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.  
  
3.  La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.  
  
4.  El puerto de envío de TIBCO se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de TIBCO.  
  
5.  El puerto de envío entrega el mensaje a BizTalk Adapter para TIBCO Rendezvous.  
  
6.  BizTalk Adapter para TIBCO Rendezvous envía el mensaje al sistema TIBCO.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Usar el adaptador de BizTalk para TIBCO Rendezvous para recibir datos](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md)   
 [Tutoriales: Usar el adaptador de Microsoft BizTalk para TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)