---
title: 'Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para escribir datos en PeopleSoft Enterprise | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9c4c0714c28f426ccfaa2799bd16463124e6e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a>Tutorial: Usar el adaptador de BizTalk para PeopleSoft Enterprise para escribir datos en PeopleSoft Enterprise
El adaptador de BizTalk para PeopleSoft Enterprise se puede usar para escribir datos en un sistema PeopleSoft con información recibida de un socio comercial o de una aplicación interna. En este tutorial se describe un ejemplo de SDK que muestra esta función.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   La plataforma Java 2 debe estar instalada en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.  
  
-   El archivo JAR de PeopleSoft Java objeto adaptador, **psjoa.jar** debe copiarse en una carpeta que sea accesible para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecuta el adaptador de BizTalk para PeopleSoft Enterprise.  
  
-   Para crear e implementar el ejemplo, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debe instalarse en el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se esté ejecutando el adaptador de BizTalk para PeopleSoft Enterprise.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 En este ejemplo, se selecciona un archivo XML de una carpeta, se envía a una orquestación y, a continuación se usa el adaptador de BizTalk para PeopleSoft Enterprise para crear un registro en el sistema PeopleSoft a partir de los datos del archivo XML.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Este ejemplo se ha diseñado en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se ha creado para mostrar las funciones básicas relacionadas con el uso del adaptador de BizTalk para PeopleSoft Enterprise con una orquestación de BizTalk.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente carpeta:  
  
 \Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|**Nombre de archivo de proyecto en tiempo de ejecución**|**Descripción del archivo del proyecto en tiempo de ejecución**|  
|----------------------------------|------------------------------------------|  
|OneWaySend.btproj,<br /><br /> OneWaySend.sln|Archivos de proyectos y soluciones para la aplicación.|  
|LOCATIONService.xsd,<br /><br /> LOCATIONService_1.xsd,<br /><br /> LOCATIONService_2.xsd|Archivos de esquema para la aplicación. **Nota:** los archivos de esquema de adaptador en el proyecto se crearon originalmente mediante el **Asistente para agregar metadatos de adaptador**. Para obtener más información sobre el Asistente para agregar metadatos de adaptador, vea el tema "Cómo agregar metadatos del adaptador a un proyecto de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|PeopleSoftOneWaySend.odx|La orquestación usada por la aplicación.|  
|PeopleSoftOneWaySend.snk|Archivo de clave de nombre seguro.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
  
#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>Crear una nueva instancia del adaptador de PeopleSoft Enterprise  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Haga clic en **iniciar**, **todos los programas**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3.  Haga clic en **adaptadores** y seleccione **New**, **adaptador...** para mostrar la **propiedades del adaptador** cuadro de diálogo.  
  
4.  Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoft**.  
  
5.  Seleccione **PeopleSoft Enterprise (r)** en la lista de adaptadores disponibles en la **adaptador** lista desplegable y haga clic en **Aceptar**.  
  
#### <a name="create-a-biztalk-send-port"></a>Crear un puerto de envío de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de envío**.  
  
2.  Haga clic en **puertos de envío** y seleccione **New**, **puerto de envío unidireccional estático** para mostrar la **propiedades de puerto de envío** cuadro de diálogo.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWaySP**.  
  
4.  Seleccione el adaptador de PeopleSoft en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **propiedades de transporte**cuadro de diálogo.  
  
    > [!NOTE]
    >  Este valor es el nombre que se especificó cuando se creó el adaptador PeopleSoft Enterprise en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
5.  Escriba los siguientes valores para la **propiedades de adaptador necesarias**:  
  
    |**Propiedad**|**Valor**|  
    |------------------|---------------|  
    |Ruta de acceso de servidor de aplicaciones|Equipo y ubicación de puerto de PeopleSoft Server, por ejemplo, //PSServer:8888. **Nota:** si no especifica un número de puerto, se utiliza el puerto predeterminado 9000 por lo que en el ejemplo anterior se puede escribir un valor de //PSServer si PeopleSoft Server usa el valor del puerto predeterminado 9000.|  
    |JAVA_HOME|Ruta de acceso para el directorio principal asociado a los archivos SDK de la plataforma Java 2, por ejemplo, C:\j2sdk1.4.2_08|  
    |Contraseña|Contraseña usada al conectar con el sistema PeopleSoft.|  
    |Archivos JAR de PeopleSoft 8.x|Ubicación del archivo JAR de PeopleSoft Java objeto adaptador **psjoa.jar**, por ejemplo, C:\JARS\psjoa.jar.|  
    |Nombre de usuario.|Nombre de usuario para conectar con el sistema PeopleSoft.|  
  
6.  Haga clic en **Aceptar**.  
  
7.  Seleccione el **XMLTransmit** canalización en la lista de canalizaciones disponibles en la **canalización de envío** lista desplegable y haga clic en **Aceptar**.  
  
8.  Haga clic en el puerto de envío y haga clic en **iniciar** para dar de alta e iniciar el puerto de envío.  
  
#### <a name="create-a-file-receive-port"></a>Crear un puerto de recepción de archivos  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **puertos de recepción**.  
  
2.  Haga clic en la carpeta puertos de recepción y, a continuación, haga clic en **New**, **puerto de recepción unidireccional** para mostrar el cuadro de diálogo Propiedades de puerto de recepción.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWayFileRP**y haga clic en **Aceptar**.  
  
#### <a name="create-a-file-receive-location"></a>Crear una ubicación de recepción de archivos  
  
1.  Cree una carpeta para que la supervise la ubicación de recepción del archivo, por ejemplo C:\Filesource.  
  
2.  Menú contextual del nuevo puerto de recepción y, a continuación, haga clic en **New**, **ubicación de recepción** para mostrar la **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
3.  Escriba un valor para el **nombre** campo, por ejemplo **PeopleSoftOneWayFileRL**.  
  
4.  Seleccione **archivo** en la lista de adaptadores disponibles en la **tipo** lista desplegable y haga clic en el **configurar** botón para mostrar el adaptador **transporte Propiedades** cuadro de diálogo.  
  
5.  Escriba la ubicación de la carpeta que creó anteriormente para la **carpeta recepción** propiedad y haga clic en **Aceptar**.  
  
6.  Seleccione **XMLReceive** en la lista de canalizaciones disponibles en la **canalización de recepción** lista desplegable y haga clic en **Aceptar**.  
  
7.  Haga clic en la ubicación de recepción y haga clic en **habilitar**.  
  
#### <a name="modify-the-adapter-schema-target-namespace-property"></a>Modificar la propiedad del espacio de nombres de destino del esquema del adaptador  
  
1.  Inicie [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y abra OneWaySend.sln. Haga clic en **archivo**, **abiertos**, **proyecto o solución...** para mostrar la **Abrir proyecto** cuadro de diálogo.  
  
2.  Busque el archivo OneWaySend.sln, haga clic en este archivo para seleccionarlo y haga clic en **abrir** para abrir la solución que contiene el proyecto de ejemplo.  
  
3.  Haga clic en el **vista** menú y seleccione **el Explorador de soluciones** para mostrar el Explorador de soluciones.  
  
4.  Haga doble clic en el archivo LOCATIONService_1.xsd en el Explorador de soluciones para abrirlo.  
  
5.  Haga clic en el **esquema** nodo de LOCATIONService_1.xsd y seleccione la **propiedades** opción de menú para mostrar las propiedades para el esquema.  
  
6.  Editar la **Target Namespace** propiedad que se va a utilizar los valores adecuados para el nombre del adaptador, por ejemplo la **Target Namespace** propiedad debe indicar lo siguiente:  
  
    ```  
    http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
    ```  
  
     Donde *PeopleSoft* es el nombre del adaptador de PeopleSoft, tal como se ve en la consola de administración de BizTalk.  
  
    > [!IMPORTANT]
    >  Si el valor configurado para **Target Namespace** no coincide con el espacio de nombres especificado en la instancia de documento de entrada, a continuación, se producirá un error de enrutamiento cuando la instancia de documento de entrada que es procesada por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>Generar una instancia de documento desde el esquema de adaptador  
  
1.  Haga doble clic en **LOCATIONService_1.xsd** en el Explorador de soluciones para abrir el archivo en el Editor de esquemas.  
  
2.  Haga clic en el  **\<esquema >** nodo en el Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades para el nodo.  
  
3.  Seleccione **CreateEx** en la lista de nodos disponibles en la **referencia raíz** cuadro de lista desplegable. Esto debe hacerse para que cuando se genera una instancia de documento de ejemplo se generará en el **CreateEx** nodo del esquema.  
  
4.  Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **propiedades**.  
  
5.  En la ventana Propiedades, haga clic en el **nombre de archivo de instancia de salida** opción bajo el **General** sección.  
  
6.  Haga clic en el botón de puntos suspensivos (...) para mostrar el **Seleccionar archivo de salida** cuadro de diálogo.  
  
7.  Especifique una carpeta y el nombre de la instancia de archivo de salida, por ejemplo **C:\instance.xml** y haga clic en **guardar**.  
  
    > [!NOTE]
    >  No especifique aquí la ubicación de la carpeta que se especificó para la ubicación de recepción de archivos.  
  
8.  Haga clic en LOCATIONService_1.xsd en el Explorador de soluciones y haga clic en **generar instancia** para generar una instancia de documento en la ubicación especificada.  
  
9. Haga clic en el  **\<esquema >** nodo en el Editor de esquemas y haga clic en **propiedades** para mostrar las propiedades para el nodo.  
  
10. Seleccione (**predeterminado)** en la lista de nodos disponibles en la **referencia raíz** cuadro de lista desplegable.  
  
#### <a name="modify-the-generated-document-instance"></a>Modificar la instancia de documento generada  
  
1.  Abra la instancia de documento generada en un editor de texto, como por ejemplo el Bloc de notas, y edite el contenido de la instancia de documento para asegurarse de que los datos de estos campos generen un registro único en el sistema PeopleSoft, por ejemplo, en el archivo XML a continuación se describen los campos de un registro que definen una ubicación:  
  
    ```  
    <ns0:CreateEx xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>9991</ns0:LOCATION>  
      <ns0:interactiveMode>true</ns0:interactiveMode>  
       <ns0:properties>  
        <ns0:LOCATION_TBL_sequence>  
          <ns0:LOCATION_TBL>  
            <ns0:COUNTRY>USA</ns0:COUNTRY>  
            <ns0:DESCR>Adapter Test</ns0:DESCR>  
            <ns0:EFFDT>2006-05-31</ns0:EFFDT>  
            <ns0:EFF_STATUS>A</ns0:EFF_STATUS>  
            <ns0:SETID>SHARE</ns0:SETID>  
          </ns0:LOCATION_TBL>  
        </ns0:LOCATION_TBL_sequence>  
      </ns0:properties>  
    </ns0:CreateEx>  
    ```  
  
    > [!NOTE]
    >  En el ejemplo anterior, *PeopleSoft* es un marcador de posición para el nombre real del adaptador tal como se ve en la consola de administración de BizTalk.  
  
2.  Guarde la instancia de documento modificada.  
  
#### <a name="build-and-deploy-the-project"></a>Generar e implementar el proyecto  
  
1.  Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **propiedades** para iniciar el Diseñador de proyectos.  
  
2.  Haga clic en el **implementación** ficha.  
  
3.  Escriba los valores adecuados para el **Server** propiedad y el **base de datos de configuración** propiedad bajo **grupo de BizTalk**.  
  
4.  Haga clic en el proyecto OneWaySend en el Explorador de soluciones y haga clic en **implementar** para crear el proyecto e implementar el ensamblado en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de configuración.  
  
#### <a name="bind-and-enlist-the-orchestration"></a>Enlazar y dar de alta la orquestación  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y haga clic en **orquestaciones**.  
  
2.  Haga clic en el **actualizar** botón en la barra de herramientas MMC o presione la **F5** clave de su teclado para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vista de la consola de administración.  
  
3.  Haga doble clic en la orquestación para mostrar el **propiedades de orquestación** cuadro de diálogo.  
  
4.  Haga clic en **enlaces** en el panel izquierdo del cuadro de diálogo para mostrar las opciones de enlaces para la orquestación.  
  
5.  Especifique los valores adecuados para las opciones de enlace, por ejemplo:  
  
    |**Parámetro**|**Valor**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |FileReceivePort|PeopleSoftOneWayFileRP|  
    |PeopleSoftOneWaySendPort|PeopleSoftOneWaySP|  
  
6.  Haga clic en Aceptar.  
  
#### <a name="start-the-orchestration"></a>Iniciar la orquestación  
  
-   En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en la orquestación y haga clic en **iniciar** dar de alta e iniciar la orquestación.  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>Soltar una instancia de documento en la carpeta supervisada por la ubicación del archivo de recepción  
  
-   Copie la instancia de documento que creó anteriormente en la carpeta que la ubicación de recepción de archivos está configurada para supervisar.  
  
#### <a name="verify-that-the-peoplesoft-system-is-updated"></a>Comprobar que se actualiza el sistema PeopleSoft  
  
-   Use la interfaz web de PeopleSoft para comprobar que se creó el registro a partir de los datos del archivo XML.  
  
 Si la instancia de documento se procesa correctamente, se produce la siguiente secuencia de eventos:  
  
1.  El adaptador de archivo recupera el archivo de la carpeta y lo publica en el cuadro de mensaje como un mensaje de BizTalk.  
  
2.  La orquestación se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk activará una instancia de la orquestación y enviará el mensaje a la instancia de orquestación.  
  
3.  La instancia de la orquestación procesa el mensaje mediante la lógica especificada en la orquestación y vuelve a publicar el mensaje en el cuadro de mensaje.  
  
4.  El puerto de envío de PeopleSoft se suscribe a este mensaje publicado, por lo que el motor de mensajería de BizTalk envía el mensaje al puerto de envío de PeopleSoft.  
  
5.  El puerto de envío entrega el mensaje al adaptador de BizTalk para PeopleSoft Enterprise.  
  
6.  BizTalk Adapter para PeopleSoft Enterprise invoca el método CreateEx para crear un registro mediante los datos del archivo XML.  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales: Usar el adaptador de BizTalk para PeopleSoft Enterprise](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)