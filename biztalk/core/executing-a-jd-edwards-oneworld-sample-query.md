---
title: Ejecutar una consulta de ejemplo de OneWorld JD Edwards | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e15310442d12c0b2604eb0d22b071ff6c57212
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a>Ejecutar una consulta de ejemplo de OneWorld JD Edwards
El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld (JDEOW) desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este adaptador se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].
  
 Esta es la segunda parte del trabajo práctico de JD Edwards OneWorld. En la primera parte (Práctica 1), obtuvo acceso manualmente a los datos en el sistema JD Edwards OneWorld sin ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otra tecnología de Microsoft. En esta parte (Práctica 2), creará una orquestación de BizTalk como parte de un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Configurará puertos en esta orquestación para usar el adaptador de JD Edwards OneWorld con el objetivo de obtener datos de un sistema JD Edwards OneWorld.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 
  
-   Software JD Edwards OneWorld Client  
  
-   Conectividad de red para un sistema JD Edwards OneWorld en otro servidor  
  
-   Adaptadores de Microsoft BizTalk para aplicaciones empresariales  
  
> [!NOTE]
>  Vea [instalar y configurar los adaptadores para aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) para obtener información de configuración de la clave para los adaptadores de JD Edwards, PeopleSoft y TIBCO.  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a>Práctica 2: ejecución de un consulta de ejemplo de JD Edwards OneWorld  
 En esta práctica, ejecutará una **obtener** operación en el sistema JD Edwards OneWorld. Específicamente, realizará las siguientes tareas:  
  
-   Comprobar los requisitos previos de JD Edwards OneWorld  
  
-   Configurar un puerto de envío de JD Edwards OneWorld en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Crear un proyecto de orquestación de BizTalk  
  
-   Generar e implementar el proyecto  
  
-   Probar la aplicación y ver la salida XML  
  
 Usará el adaptador de JD Edwards OneWorld para obtener acceso a los datos del sistema JD Edwards OneWorld desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Este adaptador le permite procesar objetos de JD Edwards OneWorld mediante solicitudes y respuestas ejecutadas por una orquestación. Se encuentran disponibles diversos métodos para objetos de esquema. Este laboratorio muestra cómo utilizar el **Address Book MBF** método.  
  
 Antes de ejecutar una solicitud de servicio, debe crear esquemas de solicitud y respuesta de servicio para el objeto específico de JD Edwards OneWorld. El Asistente para agregar elementos generados/agregar adaptador crea estos esquemas al interrogar directamente al objeto de metadatos de compatibilidad en JD Edwards OneWorld. Esta práctica, describen los pasos necesarios para crear esquemas para la **Address Book MBF** método y procesar una consulta.  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a>Paso 1: Comprobar los requisitos previos de JD Edwards OneWorld  
 Antes de comenzar a crear un proyecto de BizTalk para usarlo con el adaptador de JD Edwards OneWorld, debe asegurarse de que los archivos y el adaptador están configurados correctamente para obtener acceso al sistema JD Edwards OneWorld. En el equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el adaptador de JD Edwards OneWorld se comunica con el sistema JD Edwards OneWorld a través de la interfaz Java.    

1. Cuatro archivos son necesarios para el acceso a la interfaz adecuada para un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld: Connector.jar, Kernel.jar, BTSLIBinterop.jar y JDEJAccess.jar.  
  
    -   Los archivos Connector.jar y Kernel.jar están incluidos en el sistema JD Edwards OneWorld y se obtienen desde un administrador de JD Edwards OneWorld. Estos archivos se encuentran en la carpeta C:\JDEOWJars.  
  
    -   El sistema JD Edwards OneWorld genera el archivo BTSLIBinterop.jar al seguir las instrucciones incluidas en la Guía de instalación para adaptadores. Este archivo se encuentran en la carpeta C:\JDEOWJars.  
  
    -   El archivo JDEJAccess.jar forma parte del adaptador JDEOW y se incluye en la instalación del adaptador. De forma predeterminada, se encuentra en C:\Program Files\Microsoft BizTalk Adapters para Enterprise applications\j. Edwards OneWorld® \Classes carpeta.  
  
2. Confirme la Connector.jar, Kernel.jar, y BTSLIBinterop.jar archivos existen en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en la carpeta C:\JDEOWJars.  
  
3. Confirme que existe el archivo JDEJAccess.jar en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en el C:\Program Files\Microsoft BizTalk Adapters for Enterprise applications\j. Carpeta de Edwards OneWorld\Classes.  
  
## <a name="step-2-configure-biztalk-send-ports"></a>Paso 2: Configurar puertos de envío de BizTalk  
A continuación, compruebe que el adaptador de JD Edwards OneWorld está instalado y crear el puerto de envío.  

1.  Abra **administración de BizTalk Server**, expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, Expanda **configuración de plataforma**y, a continuación, expanda **adaptadores**.  
  
    Confirmar la **JDE_OneWorld** adaptador aparece. Si no está instalado el adaptador de JD Edwards OneWorld, instale los adaptadores de Microsoft BizTalk Adapters for Enterprise Applications (vea la sección anterior "Requisitos previos"). Una vez instalados los adaptadores, haga clic en **adaptadores** y, a continuación, haga clic en **nuevo - adaptador** para instalar el adaptador de JD Edwards OneWorld. Reinicie la instancia de host para que esto surta efecto.  
  
2. Expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1**.  
  
3.  Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**. Escriba los siguientes valores para estos campos:  
  
    1.  **Nombre:**  `JDE_OneWorldPort`  
  
    2.  **Tipo:**  `JDE_OneWorld`  
  
    3.  **Controlador de envío:**  `BizTalkServerApplication`  
  
    4.  **Canalización de envío:**  `XMLTransmit`  
  
    5.  **La canalización de recepción:**  `XMLReceive`  
  
4.  Haga clic en **Configurar**y escriba los siguientes valores de propiedades:  
  
    1.  **Host:** \<escriba su nombre de host JDEOW\>  
  
    2.  **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
    3.  **Entorno JDEdwards:** \<entran en el entorno de JDEOW\>  
  
    4.  **Archivos JAR de JDEdwards:** \<escriba la ruta de acceso completa de archivos JAR\>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  **Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.  
  
    6.  **Puerto:**  `6009`  
  
    7.  **Nombre de usuario:** \<escriba su nombre de usuario de JD Edwards\>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
5.  Seleccione **Aceptar** para cerrar el **propiedades de puerto de envío**.  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a>Paso 3: Crear un proyecto de orquestación de BizTalk  
A continuación, cree un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y configurar una orquestación en el proyecto para gestionar la comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el sistema JD Edwards OneWorld. Agregará puertos de recepción y envío, generará el proyecto y, a continuación, lo implementará.  

  
1.  Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y cree un nuevo proyecto de BizTalk en la carpeta C:\LABS. En el menú **Archivo** , haga clic en **Nuevo**. Aparecerá el cuadro de diálogo **Nuevo proyecto** . En la consola de administración de **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server** Escriba `JDE_OW_Test` como nombre único del proyecto y, a continuación, haga clic en **Aceptar**.  
  
2.  En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, haga clic en **Agregar**y, a continuación, en **Agregar elementos generados**. En el panel de categorías, seleccione **agregar metadatos de adaptador**, en el panel Plantillas, seleccione **agregar metadatos de adaptador**y, a continuación, haga clic en **agregar**.  
  
3.  En el Asistente para agregar adaptador, seleccione el **JD Edwards OneWorld** adaptador, seleccione el **JDE_OneWorldPort** puerto de envío que creó en el procedimiento anterior y, a continuación, haga clic en **siguiente**.  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  En el **seleccionar servicios para importar** página abierta **JD Edwards OneWorld**. La comunicación con el sistema JDEOW se establece a través del adaptador mediante el uso del programa BrowsingAgent. El programa BrowsingAgent muestra los servicios que figuran a continuación.  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  Expanda **CALLBSFN** y desplácese hacia abajo hasta **N0100041 - Address Book MBF**. Seleccione N0100041 y, a continuación, haga clic en **finalizar**.  
  
6.  En el Explorador de soluciones, hay una nueva orquestación de BizTalk con dos nuevos archivos de esquema asociados. Estos archivos los crea el Asistente para agregar adaptador. Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 La orquestación acepta como entrada del adaptador de archivo un archivo XML con formato para el sistema JD Edwards OneWorld. A su vez, usa el adaptador de JD Edwards OneWorld para enviar el archivo XML al sistema JD Edwards OneWorld. El sistema JD Edwards OneWorld procesa la consulta y genera un archivo XML de salida que contiene los resultados. Este archivo XML regresa a la orquestación mediante el adaptador de JD Edwards OneWorld y el adaptador de archivo escribe el archivo XML en la ubicación de salida del disco.  
  
 Para completar la orquestación, debe crear y configurar puertos para recibir y enviar los archivos XML. Primero, configure el puerto de recepción que usará el adaptador de archivo para introducir el archivo XML que contiene la consulta en la orquestación del disco.  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a>Configurar un puerto de recepción para aceptar el archivo XML de entrada  
  
1.  Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.  
  
2.  En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
3.  En el **propiedades de puerto** escriba `JDE_File_In` para **nombre**y, a continuación, haga clic en **siguiente**.  
  
4.  En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre de tipo de puerto**:`JDE_FileIn_Port`  
  
     **Patrón de comunicación**: **Unidireccional**  
  
     **Restricciones de acceso**: **Interno: limitado a este proyecto**  
  
5.  Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **Siempre recibiré los mensajes en este puerto**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
6.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
 Por último, cree un puerto de envío/recepción para enviar al sistema JD Edwards OneWorld el archivo de entrada XML inicial que contiene la consulta. Este puerto también recibirá un archivo XML de salida que contiene los resultados de la consulta correspondiente a la llamada realizada al sistema JD Edwards OneWorld.  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a>Configurar un puerto de envío y recepción a la interfaz con JD Edwards OneWorld  
  
1.  En el archivo BizTalk Orchestration.odx, haga clic en la superficie para puerto derecha y, a continuación, haga clic en **nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
2.  En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**. En **tipos de puertos disponibles**, seleccione **JD_OW_Test.N0100041**y, a continuación, haga clic en **siguiente**.  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  Seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **enviaré una solicitud y recibiré una respuesta**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
4.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**. En la superficie del puerto, verá el puerto y los métodos disponibles.  
  
 Por último, configure el puerto de envío que usará el adaptador de archivo para enviar al disco el archivo XML que contiene los resultados de la consulta.  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a>Configurar un puerto de envío para enviar el archivo XML en el disco  
  
1.  En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
2.  En el **propiedades de puerto** escriba `JDE_FileOut` para **nombre**y, a continuación, haga clic en **siguiente**.  
  
3.  En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre de tipo de puerto**:`JDE_FileOut_Port`  
  
     **Patrón de comunicación**: **Unidireccional**  
  
     **Restricciones de acceso**: **Interno: limitado a este proyecto**  
  
4.  Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **Siempre enviaré los mensajes en este puerto**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
5.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
 En la superficie del puerto se muestran los puertos nuevos y los métodos disponibles para los servicios JD Edwards OneWorld. Más adelante, especificará el adaptador de JD Edwards OneWorld para enviar y recibir archivos provenientes del sistema JD Edwards OneWorld.  
  
 El **JDE_File_In** y **JDE_File_Out** puertos que acaba de crear necesidad de tipos de mensajes asociados.  
  
#### <a name="assign-message-types-to-the-ports"></a>Asignar a tipos de mensajes a los puertos  
  
1.  En la superficie de puerto de la izquierda, en la **JDE_File_In** de puerto, haga clic en **solicitar**. En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBF**.  
  
2.  En la superficie de puerto de la izquierda, en la **JDE_File_Out** de puerto, haga clic en **solicitar**. En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBFResponse**.  
  
 Inserte dos **enviar** y dos formas **recepción** formas en la orquestación para vincular a los puertos.  
  
#### <a name="add-send-and-receive-shapes"></a>Agregar el envío y recepción formas  
  
1.  Arrastre un componente **Recepción** desde el cuadro de herramientas y suéltelo inmediatamente debajo del inicio de la orquestación (el círculo verde). Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `Get_File` para el **nombre**y establezca **activar** a `true`. De este modo se activará la orquestación cuando se reciba un documento entrante en este puerto de recepción.  
  
2.  Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **GetFileReceive** forma. Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `SendToJDEOW` para el **nombre**.  
  
3.  Arrastre un **recepción** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **SendToJDEOWSend** forma. Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `JDEOW_Resp` para el **nombre**.  
  
4.  Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **JDEOW_RespReceive** forma. Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `FileToDisk` para el **nombre**.  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  Conectar el **JDE_FileIn** puerto a la **GetFileReceive** componente.  
  
6.  Conectar el **JDE_FileOut** puerto a la **FileToDiskReceive** componente.  
  
7.  Vaya a **Vista orquestación** y expanda **mensajes**. Cambie el identificador para **Message_1** a `MsgToJDEOW`y para **Message_2** a`JDEOW_Resp.`  
  
8.  Resalte el **SendToJDEOWSend** componente y establezca su **mensaje** propiedad **MsgToJDEOW**.  
  
9. Resalte el **JDEOW_RespReceive** componente y establezca su **mensaje** propiedad **JDEOW_Resp**.  
  
10. Conectar **SendToJDEOW** a la **solicitar** parte de la **JDE_OW_Port** puerto.  
  
11. Conectar **JDEOW_Resp** a la **respuesta** parte de la **JDE_OW_Port** puerto.  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
## <a name="step-4-build-and-deploy-the-project"></a>Paso 4: Compilar e implementar el proyecto  
 Ahora, el proyecto de BizTalk está completo y puede generarlo e implementarlo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  Para generar el proyecto, es necesario un archivo de clave de nombre seguro. En el símbolo del sistema, escriba lo siguiente para crear un archivo de clave de nombre seguro:  
  
     **sn -k labs.snk**  
  
3.  En el Explorador de soluciones, haga clic en el **JD_OW_Test** del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
4.  Haga clic en la pestaña **Firma** .  
  
5.  Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.  
  
6.  Busque y seleccione el archivo de clave: **labs.snk**y, a continuación, haga clic en **Abrir**.  
  
7.  Haga clic en la pestaña **Implementación** del Diseñador de proyectos.  
  
8.  Establecer el **nombre de la aplicación** a `JDE_OW_Test`.  
  
9. En el Explorador de soluciones, haga clic en el **JDE_OW_Test** del proyecto y, a continuación, haga clic en **compilar.**  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. Cuando la compilación finalice correctamente, haga clic en el **XX_JD Edwards OneWorldQuery** del proyecto y, a continuación, haga clic en **implementar**. En la ventana de salida, aparecerá:  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a>Paso 5: Probar la aplicación y ver el resultado XML  
 A continuación, probará la aplicación que acaba de crear e implementar. Creará el archivo XML que inicia el proceso de orquestación y, a continuación, configurará carpetas para recibir y enviar archivos XML en la aplicación. Una vez que haya configurado la aplicación, la ejecutará y visualizará los archivos XML que devuelve la orquestación.  
  
#### <a name="generate-the-xml-file-for-the-query"></a>Generar el archivo XML de la consulta  
  
1.  En el Explorador de soluciones, haga doble clic en **N0100041Service_N0100041.xsd** para abrir el archivo.  
  
2.  Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **propiedades**. Para **Nombre de archivo de instancia de salida** , escriba la siguiente ruta de acceso y nombre de archivo para el XML del ejemplo:  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  Haga clic en **Aceptar.** En la ventana Propiedades, seleccione  **\<esquema\>**  y establecer **referencia raíz:** a `AddressBookMasterMBF`. Esto hará que el XML generado sólo incluirá el **consulta** xml.  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **generar instancia**. Esto genera el **Sample.xml** archivo. Este archivo se colocará en la ubicación de recepción como entrada del adaptador para iniciar el proceso de orquestación.  
  
#### <a name="configure-and-start-the-biztalk-application"></a>Configurar e iniciar la aplicación de BizTalk  
  
1.  Configure carpetas para recibir los archivos entrantes y enviar los salientes. Vaya a **C:\LABS\JDE_OW_Test** y cree dos nuevas subcarpetas denominadas `FileIn` y `FileOut`.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda**administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **Aplicaciones**.  
  
3.  Haga clic en **JDE_OW_Test**y, a continuación, haga clic en **configurar**.  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  Seleccione **Orchestration_1** y haga clic en el cuadro desplegable **Host** . Seleccionar **BizTalkServerApplication**.  
  
5.  En **puertos de recepción**, haga clic en  **\<ninguno\>**. En la lista desplegable, seleccione **Nuevo puerto de recepción**.  
  
6.  Para **nombre**, tipo `JDE_FileIn_Port`y, a continuación, haga clic en **Aceptar**. Aparecerá un cuadro de mensaje que indica que debe designar una ubicación de recepción. Haga clic en **Aceptar**y, a continuación, en **Nuevo**.  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  Escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre**: JDE_`FileInLoc`  
  
     **Tipo**: **Archivo**  
  
     **Controlador de recepción**: **BizTalkServerApplication**  
  
     **Canalización de recepción**: **XMLReceive**  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  Haga clic en **configurar**, tipo `C:\LABS\JDE_OW_Test\FileIn` para **carpeta recepción**y, a continuación, haga clic en **Aceptar** tres veces.  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. Haga clic en  **\<ninguno\>**  para **JDE_OW_Port** en la lista desplegable.  
  
10. Seleccione **nuevo puerto de envío** y, a continuación, seleccione o escriba los valores para las propiedades siguientes:  
  
     **Nombre**:`JDE_OW_Port`  
  
     **Tipo de**: **JDE_OneWorld**  
  
     **Controlador de envío**: **BizTalkServerApplication**  
  
     **Canalizaciones**: **XMLTransmit** y **XMLReceive**  
  
11. Haga clic en **Configurar**y escriba los siguientes valores de propiedades:  
  
     **Host:** \<escriba su nombre de host JDEOW\>  
  
     **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
     **Entorno JDEdwards:** \<entran en el entorno de JDEOW\>  
  
     **Archivos JAR de JDEdwards:**<enter full path of JAR files>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     **Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.  
  
     **Puerto:**  `6009`  
  
     **Nombre de usuario:**<enter your JD Edwards User Name>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.  
  
13. En el Applicationwindow configurar, haga clic en  **\<ninguno\>**  para **JDE_FileOut** en la lista desplegable.  
  
14. Seleccione **Nuevo puerto de envío** y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre**:`FileOutPort`  
  
     **Tipo**: **Archivo**  
  
     **Controlador de envío**: **BizTalkServerApplication**  
  
     **Canalización de envío**: **XMLTransmit**  
  
15. Haga clic en **configurar** y tipo`C:\Labs\JDE_OW_Test\FileOut` para **carpeta de destino.** . Mantenga **%MessageID%.xml** en **Nombre de archivo** because this results in a unique file en each message.  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. Haga clic en **Aceptar** tres veces para cerrar los cuadros de diálogo.  
  
17. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic con el **JDE_OW_Test** aplicación y, a continuación, haga clic en **iniciar**.  
  
#### <a name="test-the-orchestration"></a>Probar la orquestación  
  
1.  En el **C:\Labs\JDE_OW_Test** directorio el **Sample.xml** archivo aparecerá como:  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  Editar la **Sample.xml** archivo para quitar todo excepto la **cActionCode** y **mnAddressBookNumber** elementos.  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  Para el **cActionCode** elemento inserte la letra `i`.  
  
4.  Para **mnAddressBookNumber** insertar el número `500`.  
  
5.  Guarde los cambios y copie el archivo en el **C:\Labs\JDE_OW_Test\FileIn** carpeta. Se trata de la ubicación de recepción que inicia el proceso de orquestación.  
  
6.  En unos segundos, debe aparecer un archivo XML en el **C:\Labs\JDE_OW_Test\FileOut** carpeta. Este archivo debe incluir todos los registros cuya dirección sea 500.  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     Estos datos de registro devuelto deben coincidir con los datos devueltos por la consulta en el sistema JD Edwards OneWorld en la práctica 1. Al comparar los registros obtenidos en la práctica 1, podrá comprobar que el **obtener** método ha funcionado correctamente.  
  
## <a name="summary"></a>Resumen  
 En esta práctica, primero comprobó que los requisitos previos estaban correctamente configurados para obtener acceso al sistema JD Edwards OneWorld. A continuación, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk que contiene una orquestación. Configuró la orquestación de BizTalk para usar el adaptador de JD Edwards OneWorld a fin de de obtener datos de un sistema JD Edwards OneWorld. Para configurar la orquestación, creó puertos de envío, recepción y envío/recepción. Enlazó estos puertos al adaptador de JD Edwards OneWorld y asignó mensajes a los puertos correspondientes.  
  
 Una vez completado el proyecto de BizTalk, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generarlo e implementarlo. A continuación, configuró la nueva aplicación y la ejecutó para obtener datos del sistema JD Edwards OneWorld. Para comprobar que la aplicación funcionó correctamente, comparó el archivo XML de salida con el archivo que recibió del sistema JD Edwards OneWorld en la Práctica 1.