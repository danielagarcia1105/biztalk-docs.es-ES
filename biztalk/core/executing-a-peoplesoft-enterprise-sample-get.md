---
title: Ejecutar un comando Get de ejemplo de PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb54f14c-3fce-44d6-91bb-cb1ca38a20da
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2233e1d98ff3fde5e27f54e8877fb4b73a96b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="executing-a-peoplesoft-enterprise-sample-get"></a>Ejecutar un método Get de ejemplo de PeopleSoft Enterprise
Se puede obtener acceso al sistema PeopleSoft desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de PeopleSoft. Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
 Esta es la segunda parte del trabajo práctico de PeopleSoft. En la primera parte (Práctica 1), obtuvo acceso manualmente a los datos y los modificó en el sistema PeopleSoft sin ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otra tecnología de Microsoft. En esta parte (Práctica 2), creará una orquestación de BizTalk como parte de un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Configurará puertos en esta orquestación para usar el adaptador de PeopleSoft a fin de obtener datos de un sistema PeopleSoft.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   Adaptadores de Microsoft BizTalk para aplicaciones empresariales  
  
-   Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   Sun Systems Java Development Kit (JDK) versión 1.4 o superior  
  
> [!NOTE]
>  Para obtener más información acerca de cómo instalar y configurar los adaptadores de Microsoft BizTalk para aplicaciones empresariales, vea [http://go.microsoft.com/fwlink/?LinkId=56392](http://go.microsoft.com/fwlink/?LinkId=56392)(puede estar en inglés). En este documento se incluye información de configuración clave para los adaptadores de JD Edwards, PeopleSoft, Oracle, Tibco y Siebel LOB.  
  
## <a name="lab-2---executing-a-peoplesoft-sample-get"></a>Práctica 2: ejecución de un método Get de ejemplo de PeopleSoft  
 En esta práctica, ejecutará una operación **Get** sobre el sistema PeopleSoft. Específicamente, realizará las siguientes tareas:  
  
-   Comprobar los requisitos previos de PeopleSoft  
  
-   Configurar un puerto de envío de PeopleSoft en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Crear un proyecto de orquestación de BizTalk  
  
-   Generar e implementar el proyecto  
  
-   Probar la aplicación y ver la salida XML  
  
## <a name="procedures-for-lab-2--executing-a-peoplesoft-sample-get"></a>Procedimientos para la práctica 2: ejecución de un método Get de ejemplo de PeopleSoft  
 Son necesarios dos archivos para obtener un acceso de interfaz adecuado a un sistema PeopleSoft: PSJOA.JAR y GET_CI_INFO.PC. En el equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el adaptador de PeopleSoft se comunica con el sistema PeopleSoft mediante el uso de la interfaz de PeopleSoft Java. Esta interfaz se suministra en el archivo PSJOA.JAR. Una copia de este archivo colocada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procede normalmente del administrador del sistema PeopleSoft al que se está obteniendo acceso. En esta práctica existe una copia de PSJOA.JAR en la carpeta C:\PSJars\Ver841\ de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La ubicación de este archivo se especifica en las propiedades de configuración del adaptador de PeopleSoft.  
  
 En el propio sistema PeopleSoft debe instalarse una interfaz de componente (CI) personalizada. Esto permite al adaptador examinar objetos de PeopleSoft durante la configuración del adaptador. Se llama a la interfaz de componente personalizada (desde el paso Agregar elementos generados) para obtener una lista de objetos de PeopleSoft accesibles. Estos objetos determinan las funciones expuestas de PeopleSoft disponibles para el sistema cliente.  
  
 Específicamente, el componente personalizado, GET_CI_INFO, debe instalarse en el sistema de PeopleSoft durante la configuración inicial. Este archivo puede modificarse para limitar lo que expone GET_CI_INFO (de forma predeterminada, expone todas las interfaces de componentes del sistema PeopleSoft). Su origen se encuentra en el archivo de texto GET_CI_INFO.PC en la siguiente ubicación predeterminada:  
  
 **C:\Program Files\Microsoft BizTalk Adapters para Enterprise \Config**  
  
 En la Guía de instalación que acompaña a los adaptadores, así como en [http://go.microsoft.com/fwlink/?LinkId=56392](http://go.microsoft.com/fwlink/?LinkId=56392)(puede estar en inglés), se proporcionan instrucciones generales sobre la instalación de la interfaz del componente GET_CI_INFO en PeopleSoft. Estas instrucciones son para administradores de PeopleSoft con experiencia.  
  
### <a name="verifying-the-peoplesoft-prerequisites"></a>Comprobar los requisitos previos de PeopleSoft  
 Antes de comenzar a crear un proyecto de BizTalk para su uso con el adaptador de PeopleSoft, debe asegurarse de que todo se configura correctamente para obtener acceso a PeopleSoft.  
  
##### <a name="to-verify-the-peoplesoft-prerequisites"></a>Para comprobar los requisitos previos de PeopleSoft  
  
1.  Asegúrese de que el archivo PSJOA.JAR existe en el equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la carpeta C:\psjars\ver841. (Este archivo puede existir en una ubicación diferente en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En la siguiente configuración dada, se presupone que el archivo se encuentra en esta ubicación).  
  
2.  Asegúrese de que el archivo get_ci_info.pc existe en la carpeta C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config.  
  
3.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
4.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **Configuración de plataforma**y, a continuación, expanda **adaptadores**. Asegúrese de que el adaptador de PeopleSoft está instalado y se encuentra en la lista.  
  
     Si no está instalado el adaptador de PeopleSoft, instale los adaptadores de Microsoft BizTalk para aplicaciones empresariales (vea la sección anterior "Requisitos previos"). Una vez instalados los adaptadores, haga clic con el botón secundario en **Adaptadores** y, a continuación, haga clic en **Nuevo - Adaptador** para instalar el adaptador de PeopleSoft. Deberá reiniciar la instancia del host para que esto surta efecto.  
  
### <a name="creating-a-send-port-for-peoplesoft"></a>Crear un puerto de envío para PeopleSoft  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe tener un puerto de envío que se usará para la comunicación con el sistema PeopleSoft. Este puerto de envío terminará enlazado a los puertos lógicos de la orquestación.  
  
##### <a name="to-create-the-peoplesoft-send-port"></a>Para crear el puerto de envío de PeopleSoft  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **Aplicaciones**y, a continuación, expanda **BizTalk.EnterpriseApplication.**  
  
2.  Haga clic con el botón derecho en **Puertos de envío**, haga clic en **Nuevo**y seleccione **Puerto de envío de petición-respuesta estático**. En el cuadro de diálogo **Propiedades de puerto de envío** , especifique los siguientes valores para las propiedades:  
  
    1.  **Nombre:**  `PeopleSoftSamplePort`  
  
    2.  **Tipo:**  `PeopleSoft`  
  
    3.  **Controlador de envío:**  `BizTalkServerApplication`  
  
    4.  **Canalización de envío:**  `XMLTransmit`  
  
    5.  **La canalización de recepción:**  `XMLReceive`  
  
3.  Haga clic en **Configurar**y escriba los siguientes valores de propiedades:  
  
    1.  **Ruta de acceso al servidor de aplicaciones**: **//Servername:9000**  
  
         nombreDelServidor es el servidor de la aplicación. Se trata del nombre de servidor específico o de la dirección IP y número de puerto para este sistema PeopleSoft.  
  
    2.  **JAVA_HOME**: **C:\J2SDK1.4.2_08**  
  
         Esta ruta de acceso es específica de la instalación de Java SDK en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    3.  **Contraseña**: \<escriba su contraseña de PeopleSoft >  
  
    4.  **Archivos JAR de PeopleSoft 8.x**: **C:\PSJARS\VER841\PSJOA.JAR**  
  
    5.  **Nombre de usuario:** \<escriba el PeopleSoft UserID >  
  
     ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
4.  Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.  
  
### <a name="creating-a-biztalk-orchestration-project"></a>Creación de un proyecto de orquestación de BizTalk  
 Ahora va a crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y configurar una orquestación en el proyecto para gestionar la comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el sistema PeopleSoft. Agregará puertos de recepción y envío, generará el proyecto y, a continuación, lo implementará.  
  
##### <a name="to-create-the-biztalk-orchestration-project-in-visual-studio"></a>Procedimiento para crear el proyecto de orquestación de BizTalk en Visual Studio  
  
1.  Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y cree un nuevo proyecto de BizTalk en la carpeta C:\LABS. En el menú **Archivo** , haga clic en **Nuevo**. Aparecerá el cuadro de diálogo **Nuevo proyecto** . En la consola de administración de **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server** . Escriba `PS_Test` como nombre único del proyecto y haga clic en **Aceptar**.  
  
2.  En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, haga clic en **Agregar**y, a continuación, en **Agregar elementos generados**. Seleccione **Agregar metadatos de adaptador** del panel **Categorías** , seleccione **Agregar metadatos de adaptador** en el lado **Plantillas** y, a continuación, haga clic en **Agregar**.  
  
3.  En el Asistente para agregar adaptador, seleccione el adaptador **PeopleSoft Enterprise** , seleccione el puerto de envío **PeopleSoftSamplePort** que creó en el procedimiento anterior y, a continuación, haga clic en **Siguiente**.  
  
     ![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")  
  
4.  En la página **Seleccionar servicios para importar** , expanda **PeopleSoft**y expanda **CI**.  
  
     El adaptador interroga al sistema PeopleSoft mediante el Agente de exploración. Al expandir **CI**, se inicia el proceso BrowsingAgent.exe (puede verlo en ejecución en el Administrador de tareas) y devuelve los servicios que se muestran en la figura siguiente.  
  
     ![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")  
  
    > [!NOTE]
    >  Los servicios de PeopleSoft obtenidos y mostrados desde el sistema PeopleSoft pueden ser ligeramente diferentes de los servicios que se muestran aquí.  
  
5.  Desplácese hacia abajo, seleccione **UBICACIÓN**y, a continuación, haga clic en **Finalizar**.  
  
     ![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")  
  
6.  En el Explorador de soluciones, hay una nueva orquestación de BizTalk y dos nuevos archivos de esquema asociados. Estos archivos los crea el Asistente para agregar adaptador. Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.  
  
     ![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")  
  
 Esta orquestación acepta como entrada un archivo XML con formato para el método **Get** de PeopleSoft y envía el archivo XML al sistema PeopleSoft. El método **Get** recupera información de ubicación del sistema PeopleSoft y lo devuelve a la orquestación de BizTalk. La orquestación usa puertos para facilitar esta comunicación con el adaptador y el sistema PeopleSoft. Los puertos que va a configurar aquí son para recibir y enviar archivos XML. El archivo XML saliente indica al sistema PeopleSoft que esto es una operación **Get** . El archivo XML de entrada devuelve la información de ubicación a la orquestación.  
  
 Para completar la orquestación, debe crear y configurar puertos para recibir y enviar los archivos XML. En primer lugar, configure un nuevo puerto de recepción para aceptar el archivo de entrada XML inicial que contiene el método **Get** para iniciar la orquestación.  
  
##### <a name="to-configure-a-receive-port"></a>Para configurar un puerto de recepción  
  
1.  En el archivo BizTalk Orchestration.odx que abrió en el paso anterior, haga clic con el botón secundario en la superficie del puerto de la izquierda y, a continuación, haga clic en **Nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
2.  En el equipo de **Propiedades de puerto** , escriba `FileIn` en **Nombre**y, a continuación, haga clic en **Siguiente**.  
  
3.  En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre de tipo de puerto**:`FileInPort`  
  
     **Patrón de comunicación**: **Unidireccional**  
  
     **Restricciones de acceso**: **Interno: limitado a este proyecto**  
  
4.  Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **Siempre recibiré los mensajes en este puerto**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
5.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**. Va a usar el adaptador de archivo para aceptar este archivo como entrada desde el disco.  
  
 A continuación, cree un puerto de envío para aceptar el archivo XML que contiene los resultados de ubicación desde la llamada al método **Get** de PeopleSoft. La orquestación usa el adaptador de archivo para escribir dicho archivo XML a través de este puerto de envío.  
  
##### <a name="to-configure-a-send-port"></a>Para configurar un puerto de envío  
  
1.  En el archivo BizTalk Orchestration.odx, haga clic con el botón secundario en la superficie del puerto de la izquierda y haga clic en **Nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configurar puertos** , haga clic en **Siguiente**.  
  
2.  En el equipo de **Propiedades de puerto** , escriba `FileOut` en **Nombre**y, a continuación, haga clic en **Siguiente**.  
  
3.  En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre de tipo de puerto**:`FileOutPort`  
  
     **Patrón de comunicación**: **Unidireccional**  
  
     **Restricciones de acceso**: **Interno: limitado a este proyecto**  
  
4.  Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **Siempre enviaré los mensajes en este puerto**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
5.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
 Por último, cree un puerto de envío o recepción para enviar al sistema PeopleSoft el archivo de entrada XML inicial que contiene el método **Get** . Este puerto también recibirá un archivo XML que contiene la información de ubicación resultante de la llamada al método **Get** en el sistema PeopleSoft.  
  
##### <a name="to-configure-a-sendreceive-port"></a>Para configurar un puerto de envío o recepción  
  
1.  En el archivo BizTalk Orchestration.odx, haga clic con el botón secundario en la superficie del puerto de la derecha y haga clic en **Nuevo puerto configurado**. De esta forma, se inicia el Asistente para configuración de puertos. En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.  
  
2.  En el equipo de **Propiedades de puerto** , escriba `PeopleSoft_Port` en **Nombre**y, a continuación, haga clic en **Siguiente**.  
  
3.  En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**. Para **Tipos de puertos disponibles**, seleccione **PS_Test.LOCATION**y haga clic en **Siguiente**.  
  
     ![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")  
  
4.  Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:  
  
     **Dirección de puerto de comunicación**: **Enviaré una solicitud y recibiré una respuesta.**  
  
     **Enlace de puerto**: **Especificar más tarde**  
  
5.  Haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
 Mostrados en la superficie del puerto son el nuevo puerto y los métodos disponibles para el servicio Ubicación de PeopleSoft. Más adelante especificará el adaptador de PeopleSoft para enviar y recibir archivos desde el sistema PeopleSoft.  
  
 Ahora, inserte dos formas **Enviar** y dos formas **Recibir** en la orquestación para vincular con los puertos que acaba de crear.  
  
##### <a name="to-add-send-and-receive-shapes"></a>Procedimiento para agregar formas de envío y recepción  
  
1.  Arrastre un componente **Recepción** desde el cuadro de herramientas y suéltelo inmediatamente debajo del inicio de la orquestación (el círculo verde). Haga clic en la forma **Recibir** y, en la ventana Propiedades, escriba `FromDisk` para **Nombre**y defina **Activar** en `true`. De este modo se activará la orquestación cuando se reciba un documento entrante en este puerto de recepción.  
  
2.  Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **FromDiskReceive** forma. Haga clic en la nueva forma **Enviar** y, en la ventana Propiedades, escriba `ToPS` para **Nombre**.  
  
3.  Arrastre un **recepción** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **To_PS *** enviar** forma. Haga clic en la forma **Recibir** y, en la ventana Propiedades, escriba `FromPS` para **Nombre**.  
  
4.  Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **From_PSReceive** forma. Haga clic en la nueva forma **Enviar** y, en la ventana Propiedades, escriba `ToDisk` para **Nombre**.  
  
 Para poder conectar estas formas a puertos lógicos, debe definir los tipos de mensajes que desea procesar. El adaptador necesita tanto un mensaje de entrada (método**Request** ) como un mensaje de salida (método**Response** ). Los mensajes para cada uno de los métodos son diferentes.  
  
 En esta orquestación, solo usa los mensajes **Get-Request** y **Get-Response** . Si la orquestación estuviera actualizando datos, por ejemplo mediante el método **UpdateEx** , requeriría diferentes mensajes de solicitud y respuesta.  
  
##### <a name="to-define-and-assign-messages-to-ports"></a>Para definir y asignar mensajes a puertos  
  
1.  En la superficie del puerto de la izquierda, haga clic en **Solicitud** en el puerto **FileIn** . En la ventana Propiedades, expanda **Tipo de mensaje**y **Mensaje de varias partes**, y haga clic en **PS_Test.Get**.  
  
2.  En la superficie del puerto de la izquierda, haga clic en **Solicitud** en el puerto **FileOut** . En la ventana Propiedades, expanda **Tipo de mensaje**y **Mensaje de varias partes**, y haga clic en **PS_Test.GetResponse**.  
  
     ![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")  
  
3.  Seleccione el puerto **FileIn** y arrastre su flecha de envío de salida a la flecha de recepción opuesta de entrada en la forma **FromDisk** .  
  
4.  Seleccione el puerto **FileOut** y arrastre su flecha de recepción opuesta de entrada a la flecha de envío de salida en la forma **ToDisk** .  
  
5.  Cambie el nombre de los mensajes genéricos existentes por nombres más descriptivos para adherirse a los principios de buen diseño de aplicaciones. En el Explorador de soluciones, haga clic en la pestaña **Vista orquestación** . En **mensajes**, cambie el identificador para **Message_1** a **PS_Msg**. Cambie el identificador para **Message_2** a **PS_Resp**.  
  
     ![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")  
  
     ![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")  
  
6.  Resalte la forma de envío **To_PS** y establezca su propiedad **Mensaje** en **PS_Msg**.  
  
7.  Resalte la forma de recepción **From_PS** y establezca su propiedad **Mensaje** en **PS_Resp**.  
  
8.  Conecte la forma de envío **To_PS** a la parte **Solicitud** del método **Get** en el puerto **PeopleSoft_Port** .  
  
9. Conecte la forma de envío **From_PS** a la parte **Respuesta** del método **Get** en el puerto **PeopleSoft_Port** .  
  
     ![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")  
  
### <a name="building-and-deploying-the-project"></a>Generación e implementación del proyecto  
 Ahora, el proyecto de BizTalk está completo y puede generarlo e implementarlo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
##### <a name="to-build-and-deploy-the-project"></a>Procedimiento para generar e implementar el proyecto  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]** , seleccione **Visual Studio Tools**y, a continuación, haga clic en  **[!INCLUDE[vs2010](../includes/vs2010-md.md)] Símbolo**.  
  
2.  Para generar el proyecto, necesita un archivo de clave de nombre seguro. En el símbolo del sistema, escriba lo siguiente para crear un archivo de clave de nombre seguro:  
  
     **sn -k labs.snk**  
  
3.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PS_Test** y, a continuación, haga clic en **Propiedades** para iniciar el Diseñador de proyectos para el proyecto.  
  
4.  Haga clic en la pestaña **Firma** .  
  
5.  Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.  
  
6.  Busque y seleccione el archivo de clave: **labs.snk**y, a continuación, haga clic en **Abrir**.  
  
7.  Haga clic en la pestaña **Implementación** del Diseñador de proyectos.  
  
8.  Establezca el **Nombre de la aplicación** en `PS_Test`.  
  
9. En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PS_Test** y, a continuación, haga clic en **Generar**.  
  
10. Después de que la generación se complete correctamente, haga clic con el botón secundario en el proyecto **PS_Test** y, a continuación, haga clic en **Implementar**.  
  
### <a name="testing-the-application-and-viewing-the-xml-output"></a>Prueba de la aplicación y visualización de la salida XML  
 A continuación, probará la aplicación que acaba de crear e implementar. Creará el archivo XML que inicia el proceso de orquestación y, a continuación, configurará carpetas para recibir y enviar archivos XML en la aplicación. Una vez que haya configurado la aplicación, la ejecutará y visualizará los archivos XML que devuelve la orquestación.  
  
##### <a name="to-generate-the-xml-file-for-the-query"></a>Procedimiento para generar el archivo XML de la consulta  
  
1.  En el Explorador de soluciones, haga doble clic en **LOCATIONService_LOCATION_x5d.xsd** para abrir el archivo.  
  
2.  Haga clic con el botón secundario en **LOCATIONService_LOCATION_x5d.xsd** y, a continuación, haga clic en **Propiedades**. Para **Nombre de archivo de instancia de salida** , escriba la siguiente ruta de acceso y nombre de archivo para el XML del ejemplo:  
  
     `C:\LABS\PS_TEST\SAMPLEQUERY.XML`  
  
3.  Haga clic en **Aceptar.** En la ventana Propiedades, seleccione  **\<esquema >** y establecer **referencia raíz: obtener**.  
  
4.  Haga clic con el botón secundario en **LOCATIONService_LOCATION_x5d.xsd** y, a continuación, haga clic en **Generar instancia**. De este modo se genera el archivo **SampleQuery.xml** . Este archivo se colocará en la ubicación de recepción como entrada del adaptador para iniciar el proceso de orquestación.  
  
     ![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")  
  
##### <a name="to-configure-and-start-the-biztalk-application"></a>Procedimiento para configurar e iniciar la aplicación BizTalk  
  
1.  Configure carpetas para recibir los archivos entrantes y enviar los salientes. Vaya a **C:\LABS\PS_TEST** y cree dos nuevas subcarpetas denominadas `FileIn` y `FileOut`.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **Aplicaciones**, haga clic en **PS_Test** y, a continuación, haga clic en **configurar**.  
  
     ![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")  
  
3.  Seleccione **Orchestration_1** y haga clic en el cuadro desplegable **Host** . Seleccionar **BizTalkServerApplication**.  
  
4.  En **puertos de recepción**, haga clic en  **\<ninguno >**. En la lista desplegable, seleccione **Nuevo puerto de recepción**.  
  
5.  For **Nombre**, escriba `FileInPort`y, a continuación, haga clic en **Aceptar**. Aparecerá un cuadro de mensaje que indica que debe designar una ubicación de recepción. Haga clic en **Aceptar**y, a continuación, en **Nuevo**.  
  
     ![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")  
  
6.  Escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre**:`FileInLoc`  
  
     **Tipo**: **Archivo**  
  
     **Controlador de recepción**: **BizTalkServerApplication**  
  
     **Canalización de recepción**: **XMLReceive**  
  
     ![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")  
  
7.  En el menú **Configurar** y escriba `C:\LABS\PS_TEST\FILEIN` en **Carpetas de recepción**y, a continuación, haga clic en **Aceptar** .  
  
     ![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")  
  
8.  Haga clic en  **\<ninguno >** para **PeopleSoft_Port** en la lista desplegable.  
  
9. Seleccione **Nuevo puerto de envío** y, a continuación, seleccione o escriba los siguientes valores para las propiedades.  
  
     **Nombre**:`PS_Test_Port`  
  
     **Tipo**: **PeopleSoft**  
  
     **Controlador de envío**: **BizTalkServerApplication**  
  
     **Canalizaciones**: **XMLTransmit** y **XMLReceive**  
  
10. Haga clic en **Configurar**y escriba los siguientes valores de propiedades:  
  
    1.  **Ruta de acceso al servidor de aplicaciones**: **//Servername:9000**  
  
         nombreDelServidor es el servidor de la aplicación. Se trata del nombre de servidor específico o de la dirección IP y número de puerto para este sistema PeopleSoft.  
  
    2.  **JAVA_HOME**: **C:\J2SDK1.4.2_08**  
  
         Esta ruta de acceso es específica de la instalación de Java SDK en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    3.  **Contraseña**: \<escriba su contraseña de PeopleSoft >  
  
    4.  **Archivos JAR de PeopleSoft 8.x**: **C:\PSJARS\VER841\PSJOA.JAR**  
  
     **Nombre de usuario:** \<escriba el PeopleSoft UserID >  
  
11. Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.  
  
12. En el Applicationwindow configurar, haga clic en  **\<ninguno >** para **FileOut** en la lista desplegable.  
  
13. Seleccione **Nuevo puerto de envío** y escriba o seleccione los siguientes valores para las propiedades:  
  
     **Nombre**:`FileOutPort`  
  
     **Tipo**: **Archivo**  
  
     **Controlador de envío**: **BizTalkServerApplication**  
  
     **Canalización de envío**: **XMLTransmit**  
  
14. En el menú **Configurar** y escriba`C:\Labs\PS_Test\FileOut` en **Carpeta de destino** . Mantenga **%MessageID%.xml** en **Nombre de archivo** because this results in a unique file en each message.  
  
15. Haga clic en **Aceptar** tres veces para cerrar los cuadros de diálogo.  
  
16. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic con el **PS_Test** aplicación y, a continuación, haga clic en **iniciar**.  
  
     ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
##### <a name="to-test-the-orchestration"></a>Procedimiento para probar la orquestación  
  
1.  En el directorio **C:\Labs\PS_Test** , cambie el archivo **Samplequery.xml** a lo siguiente:  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>AUS01</ns0:LOCATION>  
      <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  Se usará el valor de datos **SHARE** en todos los sistemas. No obstante, el valor que va a usar para **Ubicación** en este archivo XML debe existir en el sistema. Esto se observó en la Práctica 1.  
  
2.  Guarde los cambios y copie el archivo a la carpeta **C:\Labs\PS_Test\FileIn** . Se trata de la ubicación de recepción para FileIn que inicia el proceso de orquestación.  
  
3.  En unos segundos debe aparecer un archivo XML en la carpeta **C:\Labs\PS_Test\FileOut** , que debe contener los datos del registro donde la ubicación es AUS01.  
  
     ![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")  
  
     Estos datos de registro devueltos deben coincidir con lo que devolvió la consulta en el sistema PeopleSoft en la práctica 1 de PeopleSoft. Comparando los valores que obtuvo en la práctica 1, específicamente el **Address1** y **Address2** líneas, al que se muestra a continuación en el  **\<ubicación: ADDRESS1 >** y  **\<ubicación: ADDRESS2 >** campos, podrá comprobar que el **obtener** método ha funcionado correctamente.  
  
## <a name="summary"></a>Resumen  
 En esta práctica, primero comprobó que los requisitos previos estaban correctamente configurados para obtener acceso al sistema PeopleSoft. A continuación, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk que contiene una orquestación. Configuró la orquestación de BizTalk para usar el adaptador de PeopleSoft con el fin de obtener datos del sistema PeopleSoft. Para configurar la orquestación, creó puertos de envío, recepción y envío/recepción. Enlazó estos puertos al adaptador de PeopleSoft y asignó mensajes a los puertos correspondientes.  
  
 Una vez completado el proyecto de BizTalk, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generarlo e implementarlo. A continuación, configuró la nueva aplicación y la ejecutó para obtener datos del sistema PeopleSoft. Para comprobar que la aplicación funcionó correctamente, comparó el archivo XML de salida con el archivo que recibió del sistema PeopleSoft en la Práctica 1.