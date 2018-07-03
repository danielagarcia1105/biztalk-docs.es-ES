---
title: Agregar el adaptador de BizTalk para JD Edwards OneWorld | Microsoft Docs
description: Agregar J.D. Edwards OneWorld a administración de BizTalk, cree el puerto de envío, configure las propiedades de transporte y usa las canalizaciones XMLReceive y XMLTransmit cuando se usa el adaptador de JD Edwards OneWorld en BizTalk Server
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decababef3ece92c99687a4019b15625b1b4c6b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981397"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>Configurar los artefactos de JD Edwards EnterpriseOne en administración de BizTalk
El adaptador de BizTalk para JD Edwards OneWorld contiene las carpetas Controlador de recepción y Controlador de envío. La carpeta Controlador de envío contiene BizTalkServerApplication. El adaptador de BizTalk para JD Edwards OneWorld se puede crear; se ejecuta en curso con BizTalk Server y no se ejecuta en un proceso de host aislado.  

## <a name="add-the-adapter-to-biztalk-administration"></a>Agregar el adaptador para la administración de BizTalk 

1.  Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y, a continuación, expanda **deconfiguracióndeplataforma**.  
  
2.  Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.  
  
3.  Escriba un nombre para el adaptador. Por ejemplo, escriba`JDEOneWorld`.  
  
4.  Seleccione **JDEOneWorld** desde el **adaptador** lista y seleccione **Aceptar**.  

  
### <a name="check-if-the-adapter-is-working"></a>Compruebe si funciona el adaptador 
 En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede comprobar que el adaptador funciona correctamente, examine la **sistema lógico** ventana. En la instalación inicial, esta ventana está vacía, porque todavía no se ha establecido ninguna conexión con el sistema de servidor ni se ha creado ningún sistema lógico.  
  
 
1. En **administración de BizTalk Server**, expanda **configuración de plataforma**, expanda **adaptadores**y, a continuación, seleccione **JDEOneWorld**.  
  
2. En el panel de detalles, haga clic en **BizTalkServerApplication**y seleccione **propiedades**.  
  
3. Seleccione el **propiedades** ficha.  
  
4. Establezca los parámetros de la conexión SQL.  
  
   -   **Definir parámetros de la base de datos SQL -** el nombre de SQL Server y base de datos son los que se establecen durante la instalación. Esta es el área de texto en la que se puede redefinir el servidor y la base de datos del adaptador.  
  
5. Seleccione **cerrar** para salir del **sistema lógico** ventana.  
  
    El siguiente paso es agregar un sistema lógico mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  

## <a name="create-the-send-port"></a>Crear el puerto de envío  
  
1.  En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío de petición-respuesta estático**.  
  
    > [!NOTE]
    >  También puede usar **Puerto unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío**, seleccione el **nombre** campo y escriba un nombre de puerto de envío. Por ejemplo, escriba **SendToJDE**.  
  
4.  En el **tipo** lista desplegable, seleccione **JDEOneWorld**.  
  
5.  En el **URI** lista desplegable, seleccione el controlador de envío.  
  
6.  Seleccione **Aceptar**. 

## <a name="configure-the-transport-properties"></a>Configurar las propiedades de transporte
La definición del sistema de propiedades de JD Edwards OneWorld Transport se usa para el diseño y el inicio de sesión en tiempo de ejecución. Estas credenciales se definen para examinar las funciones empresariales de JD Edwards OneWorld en tiempo de diseño y realizar llamadas en tiempo de ejecución.  
  
 Cuando se realiza una conexión con JD Edwards OneWorld, los parámetros se transfieren al objeto de conexión (Usuario, Contraseña, Entorno). Devuelve una instancia de la función empresarial aApplication de JD Edwards OneWorld. Las credenciales se definen mediante el nombre del servidor de empresa/aplicación y el puerto TCP/IP definido en el cual escucha el servicio.  
  
 El nombre de servidor empresarial y el puerto se leen desde un archivo denominado jdeinterop.ini. Estos valores deben ser los mismos que los que se encuentran en la configuración de la definición del sistema.  
  
> [!NOTE]
>  Todas las entradas distinguen entre mayúsculas y minúsculas.  
  
### <a name="set-the-properties"></a>Establecer las propiedades  
 En el **propiedades de transporte** cuadro de diálogo, se establecen los parámetros de conexión y las credenciales que son específicos para el sistema del servidor y los objetos que está intentando acceder.  
  
1.  Proporcionar credenciales. Se puede tener acceso al sistema JD Edwards OneWorld usando uno de los métodos siguientes:  
  
    -   Inicio de sesión de credenciales (nombre de usuario, contraseña): si usa este método, vaya al paso 5.  
  
    -   Inicio de sesión único (SSO).  
  
2.  Para usar el inicio de sesión único (SSO), seleccione **Sí** en el **usar SSO**.  
  
     Para obtener más información acerca de cómo configurar el inicio de sesión único, vea [seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  Seleccione una aplicación afiliada en la lista.  
  
     Una aplicación afiliada, creada por herramientas de inicio de sesión único de la empresa, representa una aplicación como JD Edwards OneWorld. El Adaptador de Microsoft BizTalk para JD Edwards OneWorld usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de credenciales de SSO del sistema del servidor para una aplicación afiliada determinada. Las credenciales son aquellas que pertenecen al usuario de la aplicación que inició el proyecto de BizTalk Server.  
  
     Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications3.md).  
  
4.  Expanda el **sistema JD Edwards OneWorld** nodo y escriba toda la información necesaria para la conexión al servidor de JD Edwards OneWorld.  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     Después de establecer los parámetros de conexión, puede examinar un sistema JD Edwards OneWorld. Para obtener más información, consulte [importar esquemas de JD Edwards OneWorld en proyectos de BizTalk Server](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).  
  
5.  Escriba un valor que representa el número de llamadas, por ejemplo, 200, en **las llamadas máximas simultáneas** si es necesario.  
  
     El `Max Concurrent Calls` parámetro le permite optimizar su configuración. Este parámetro se usa en aquellas instancias en las que el rendimiento excede las capacidades de procesamiento del servidor, para activar la protección ante la sobrecarga de mensajes. El valor predeterminado es -1, lo que significa que las llamadas son ilimitadas.  
  
     Cuando BizTalk Server envía mensajes al adaptador de transmisión, recibe, en primer lugar, un lote del adaptador. Invoca `TransmitMessage` en el lote para transmitir los distintos mensajes. A continuación, el servidor BizTalk Server invoca `Done` en el lote, y el adaptador comienza a transmitir los mensajes al servidor. Si BizTalk Server obtiene varios lotes antes de invocar `Done`, puede que nunca tenga lugar. El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor.  
  
     Cambiar este parámetro ejerce efecto en el plazo de un minuto; BizTalk Server debe recuperar los cambios de la configuración del adaptador que se haya guardado en la base de datos de SQL.  
  
6.  Seleccione **Sí** para **agente de actualización** para forzar los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.  
  
     Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.  
  
    > [!NOTE]
    >  Browsingagent.exe no se actualiza hasta que no salga de la sesión de exploración actual. Por ejemplo, debe salir de la **agregar genera elemento** exploración de la sesión y vuelva a escribir para actualizar browsingagent.exe.  
  
7.  Después de proporcionar toda la información necesaria, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** para aceptar la información de conexión.  
  
     Debe configurar parámetros de conexión para que el Adaptador de BizTalk para JD Edwards OneWorld pueda obtener acceso a JD Edwards OneWorld.  
  
### <a name="adapter-required-properties"></a>Propiedades de adaptador necesaria  
 Si no ha especificado variables de entorno globales en el Panel de control, puede hacerlo en esta sección.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`Host`|Escriba el nombre del nombre de equipo del servidor de host (por ejemplo, `actsvr1`); o la dirección IP del equipo (por ejemplo, `123.456.0.789`).|  
|JAVA_HOME|Escriba la ruta de acceso completa de la instalación de JDK.|  
|Entorno JDE Edwards|Escriba el nombre de un entorno en JD Edwards OneWorld, por ejemplo, `DV7333`.<br /><br /> DV7333 es un nombre común para el entorno de desarrollo, PY7333 es común para el entorno de prototipo y PD7333 es común para el entorno de producción.|  
|Archivos JAR de JDEdwards|Escriba la ruta de acceso y el nombre de archivo completos para cada archivo JAR:<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> Cada archivo jar debe estar separado mediante un punto y coma (;) y sin espacio. Por ejemplo:<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|Contraseña|Escriba la contraseña del usuario especificado.|  
|Puerto|Escriba el número de puerto que intercambiará datos (por ejemplo, `6009`).|  
|Nombre de usuario|Escriba un nombre de usuario de JD Edwards OneWorld que se usará para iniciar sesión en ese sistema.|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>Usa las canalizaciones XMLTransmit y XMLReceive
Microsoft BizTalk Adapter para JD Edwards OneWorld necesita que seleccione XMLTransmit y XMLReceive para el envío y las canalizaciones de recepción.  
  
1.  En **administración de BizTalk Server**, expanda **aplicaciones**y, a continuación, expanda la aplicación.  
  
2.  Seleccione **puertos de envío**, haga clic en el puerto de envío y seleccione **propiedades**.  
  
3.  En el **propiedades de puertos de envío**, realice lo siguiente:  
  
    1.  Seleccione la canalización de envío desde la **canalización de envío** lista desplegable.  
  
    2.  Seleccione la canalización de recepción desde el **canalización de recepción** lista desplegable.  
  
4.  Seleccione **Aceptar**.  

## <a name="next-steps"></a>Pasos siguientes
[Importar esquemas de adaptador a Visual Studio](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[Usar propiedades de contexto de mensaje](using-message-context-properties2.md)