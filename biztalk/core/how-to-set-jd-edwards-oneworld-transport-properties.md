---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 5290f424bbeb5cf54e78c903c50a6c2d945bc8cc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a>Cómo establecer las propiedades de transporte de OneWorld JD Edwards

## <a name="overview"></a>Información general
La definición del sistema de propiedades de JD Edwards OneWorld Transport se usa para el diseño y el inicio de sesión en tiempo de ejecución. Estas credenciales se definen para examinar las funciones empresariales de JD Edwards OneWorld en tiempo de diseño y realizar llamadas en tiempo de ejecución.  
  
 Cuando se realiza una conexión con JD Edwards OneWorld, los parámetros se transfieren al objeto de conexión (Usuario, Contraseña, Entorno). Devuelve una instancia de la función empresarial aApplication de JD Edwards OneWorld. Las credenciales se definen mediante el nombre del servidor de empresa/aplicación y el puerto TCP/IP definido en el cual escucha el servicio.  
  
 El nombre de servidor empresarial y el puerto se leen desde un archivo denominado jdeinterop.ini. Estos valores deben ser los mismos que los que se encuentran en la configuración de la definición del sistema.  
  
> [!NOTE]
>  Todas las entradas distinguen entre mayúsculas y minúsculas.  
  
## <a name="set-the-transport-properties"></a>Establecer las propiedades de transporte  
 En el **propiedades de transporte** cuadro de diálogo, se establecen los parámetros de conexión y las credenciales que son específicos del sistema servidor y los objetos que está intentando obtener acceso.  
  
1.  Proporcionar credenciales.  
  
     Se puede tener acceso al sistema JD Edwards OneWorld usando uno de los métodos siguientes:  
  
    -   Credenciales (contraseña, nombre de usuario) de inicio de sesión: Si utiliza este método, vaya al paso 5.  
  
    -   Inicio de sesión único (SSO).  
  
2.  Para usar el inicio de sesión único (SSO), seleccione **Sí** en el **usar SSO**.  
  
     Para obtener más información acerca de cómo configurar SSO, vea [seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  Seleccione una aplicación afiliada en la lista.  
  
     Una aplicación afiliada, creada por herramientas de inicio de sesión único de la empresa, representa una aplicación como JD Edwards OneWorld. El Adaptador de Microsoft BizTalk para JD Edwards OneWorld usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de credenciales de SSO del sistema del servidor para una aplicación afiliada determinada. Las credenciales son aquellas que pertenecen al usuario de la aplicación que inició el proyecto de BizTalk Server.  
  
     Para obtener más información, consulte [crear aplicaciones afiliadas](../core/creating-affiliate-applications3.md).  
  
4.  Expanda el **sistema JD Edwards OneWorld** nodo y escriba toda la información necesaria para la conexión al servidor de JD Edwards OneWorld.  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     Después de establecer los parámetros de conexión, puede examinar un sistema JD Edwards OneWorld. Para obtener más información, consulte [importar JD Edwards OneWorld esquemas en proyectos de BizTalk Server](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).  
  
5.  Escriba un valor que representa el número de llamadas, por ejemplo, 200, en **número máximo de llamadas simultáneas** si es necesario.  
  
     El `Max Concurrent Calls` parámetro le permite optimizar su configuración. Este parámetro se usa en aquellas instancias en las que el rendimiento excede las capacidades de procesamiento del servidor, para activar la protección ante la sobrecarga de mensajes. El valor predeterminado es -1, lo que significa que las llamadas son ilimitadas.  
  
     Cuando BizTalk Server envía mensajes al adaptador de transmisión, recibe, en primer lugar, un lote del adaptador. Invoca `TransmitMessage` en el lote para transmitir los distintos mensajes. A continuación, el servidor BizTalk Server invoca `Done` en el lote, y el adaptador comienza a transmitir los mensajes al servidor. Si BizTalk Server obtiene varios lotes antes de invocar `Done`, puede que nunca tenga lugar. El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor.  
  
     Cambiar este parámetro ejerce efecto en el plazo de un minuto; BizTalk Server debe recuperar los cambios de la configuración del adaptador que se haya guardado en la base de datos de SQL.  
  
6.  Seleccione **Sí** para **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.  
  
     Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.  
  
    > [!NOTE]
    >  Browsingagent.exe no se actualiza hasta que no salga de la sesión de exploración actual. Por ejemplo, debe salir de la **agregar genera elemento** exploración sesión y volver a entrar para actualizar browsingagent.exe.  
  
7.  Después de proporcionar toda la información necesaria, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** para aceptar la información de conexión.  
  
     Debe configurar parámetros de conexión para que el Adaptador de BizTalk para JD Edwards OneWorld pueda obtener acceso a JD Edwards OneWorld.  
  
## <a name="adapter-required-properties"></a>Propiedades de adaptador necesario  
 Si no ha especificado variables de entorno globales en el Panel de control, puede hacerlo en esta sección.  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`Host`|Escriba el nombre del nombre de equipo del servidor de host (por ejemplo, `actsvr1`); o la dirección IP del equipo (por ejemplo, `123.456.0.789`).|  
|JAVA_HOME|Escriba la ruta de acceso completa de la instalación de JDK.|  
|Entorno JDE Edwards|Escriba el nombre de un entorno en JD Edwards OneWorld, por ejemplo, `DV7333`.<br /><br /> DV7333 es un nombre común para el entorno de desarrollo, PY7333 es común para el entorno de prototipo y PD7333 es común para el entorno de producción.|  
|Archivos JAR de JDEdwards|Escriba la ruta de acceso y el nombre de archivo completos para cada archivo JAR:<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> Cada archivo jar debe estar separado mediante un punto y coma (;) y sin espacio. Por ejemplo:<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|Contraseña|Escriba la contraseña del usuario especificado.|  
|Puerto|Escriba el número de puerto que intercambiará datos (por ejemplo, `6009`).|  
|Nombre de usuario|Escriba un nombre de usuario de JD Edwards OneWorld que se usará para iniciar sesión en ese sistema.|  
  
