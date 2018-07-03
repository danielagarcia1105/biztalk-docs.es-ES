---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 1d808140049b7a65f0b316ab39a0e42139563da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985773"
---
# <a name="setting-jd-edwards-enterpriseone-transport-properties"></a>Establecimiento de las propiedades de transporte de JD Edwards EnterpriseOne
Las propiedades del transporte JD Edwards EnterpriseOne se usan para el diseño y el tiempo de ejecución. En el **propiedades de transporte** cuadro de diálogo, Establece los parámetros de conexión y credenciales específicas para el sistema del servidor y los objetos que está intentando acceder.  

 Después de configurar los parámetros de conexión, puede examinar las tablas, las vistas y los procedimientos del sistema JD Edwards EnterpriseOne en el asistente para adaptador.  

 Cuando se establece una conexión con JD Edwards EnterpriseOne, se pasan parámetros al objeto de conexión (Usuario, Contraseña, Entorno). Devuelve una instancia de la función de negocio de aplicación JD Edwards EnterpriseOne. Las credenciales se definen mejor mediante el nombre del servidor empresarial/de aplicaciones y el puerto TCP/IP definido en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escucha.  

> [!NOTE]
>  Los valores predeterminados para el nombre de servidor empresarial y el puerto se configuran en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. También se leen en un archivo denominado jdeinterop.ini. Si recibe errores de inicio de sesión, compruebe con cuidado las credenciales y valores.  

## <a name="enter-transport-properties"></a>Especifique las propiedades de transporte  

1. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  

2. Haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

3. En el **propiedades de puerto de envío** cuadro de diálogo, haga clic dentro del **nombre** cuadro y escriba un nombre para este puerto (por ejemplo, `JDEEnterpriseOneSend`).  

4. En **General**, en el **tipo de transporte** cuadro, seleccione **JDE EnterpriseOne** en la lista desplegable.  

5. En el **dirección (URI)** propiedad, haga clic en el botón de puntos suspensivos (**...** ).  

    El **propiedades de transporte de JDE EnterpriseOne** aparece el cuadro de diálogo.  

    ![](../core/media/jdeenterprise-trans.gif "JDEEnterprise_Trans")  

6. En el **propiedades de transporte de JDE EnterpriseOne** cuadro de diálogo, expanda el **propiedades necesarias del adaptador**y escriba toda la información necesaria para la conexión al servidor J.D. Edwards EnterpriseOne.  

    Use las directrices siguientes para establecer las propiedades de transporte:  


   |                      Use                       |                                                                                                                                                                                                            Para hacer lo siguiente                                                                                                                                                                                                             |
   |-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **Propiedades de adaptador necesarias**           |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                        Host                         |                                                                                                                   Escriba el nombre del equipo de servidor host (por ejemplo:<br /><br /> `actsvr1`)<br /><br /> --o bien--<br /><br /> Escriba la dirección IP del equipo (por ejemplo,<br /><br /> `123.456.0.789`)                                                                                                                    |
   |                      JAVA_HOME                      |                                                                                                                                                                  Escriba la ruta de acceso completa a la instalación de JDK (por ejemplo,<br /><br /> `C:\jdk1sdk1.4.2_07`)                                                                                                                                                                  |
   |                Entorno JDEdwards                |                                                                                  Escriba el nombre de un entorno en JD Edwards EnterpriseOne (por ejemplo, `DV7333`).<br /><br /> DV7333 es un nombre común para el entorno de desarrollo, PY7333 es común para el entorno de prototipo y PD7333 es común para el entorno de producción.                                                                                   |
   |                 Archivos JAR de JDEdwards                 | Escriba el nombre de archivo y ruta de acceso completos para cada uno de los archivos JAR:<br /><br /> -C:\JDEOWJars\Connector.jar<br />-C:\JDEOWJars\Kernel.jar<br />-Programa de programa\Microsoft BizTalk Adapters for Enterprise applications\j. Edwards EnterpriseOne(r)\Classes\JDEDynAccess.jar<br /><br /> Cada archivo jar debe estar separado mediante un punto y coma (;) y sin espacio (por ejemplo,<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`) |
   |                      Contraseña                       |                                                              Escriba una contraseña de usuario. Si no usa el inicio de sesión único (SSO), debe establecer parámetros de credenciales para el adaptador BizTalk para que JD Edwards EnterpriseOne obtenga acceso al sistema servidor. La contraseña corresponde al nombre de usuario, y determina los privilegios que se le conceden al obtener acceso a la base de datos.                                                              |
   |                        Puerto                         |                                                                                                                                                                         Escriba el identificador numérico de envío o puerto de recepción (por ejemplo, `6009`).                                                                                                                                                                          |
   |                      Nombre de usuario                      |                                                                                                                                                                                         Escriba el nombre del usuario y, a continuación, haga clic en **Aceptar**.                                                                                                                                                                                         |
   | **Las propiedades necesarias del origen de datos Bootstrap\*\\**\* |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                  Data Source Name                   |                                                                                                                                                                           Escriba el nombre del origen de datos. Este nombre es obligatorio para todos los tipos de datos.                                                                                                                                                                            |
   |                   Propietario de la base de datos                    |                                                                                                                                                                                               Escriba el nombre del propietario de la base de datos.                                                                                                                                                                                                |
   |                Nombre del servidor de bases de datos                 |                                                                                                                                                                                               Escriba el nombre del servidor de bases de datos.                                                                                                                                                                                               |
   |                Puerto de servidor de bases de datos                 |                                                                                                                                                                                     Escriba el número de identificación del puerto de servidor de bases de datos.                                                                                                                                                                                      |
   |                    Tipo de base de datos                    |                                                                                                          Escriba un carácter único para el tipo de base de datos. Por ejemplo:<br /><br /> **Puedo** -iSeries<br /><br /> **O** -Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** -UDB                                                                                                           |
   |               Nombre de la base de datos física                |                                                                                                                                                                      Escriba el nombre de la base de datos física. Este nombre es obligatorio para todos los tipos de bases de datos.                                                                                                                                                                       |
   |               **Control de simultaneidad**               |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                Máximo de llamadas simultáneas                 |                                                                                                                    Escriba un valor numérico para el **las llamadas máximas simultáneas**. Este número representa el número máximo de llamadas simultáneas, por ejemplo, `10`.<br /><br /> El valor predeterminado para este campo es 5.                                                                                                                    |
   |                  **Agente de actualización**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                    Agente de actualización                    |                           Seleccione **Sí** para el **agente de actualización** para forzar los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.<br /><br /> Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.                           |
   |                 **Servidor de seguridad**                 |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                Nombre del servidor de seguridad                 |                                                                                                                                                             Escriba el nombre del servidor de seguridad. Este campo es opcional y toma de forma predeterminada el valor del host de servidor JD Edwards.                                                                                                                                                              |
   |                Conexión del nombre de servicio                 |                                                                                                                                                  Escriba el número de puerto usado por el servidor de seguridad y la asignación de configuración del objeto (OCM). El valor predeterminado es el puerto del servidor JD Edwards.                                                                                                                                                  |
   |                 **Inicio de sesión único**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                Affiliate Application                |                                                                                                                                                                        Seleccione la aplicación afiliada en la lista desplegable solo si usa SSO.                                                                                                                                                                        |
   |                       Utilice SSO                       |                                                                                                                                                                           Seleccione **Sí** si está usando SSO; una contraseña no es necesaria en este caso.                                                                                                                                                                           |


7. Haga clic en **Aceptar** para aceptar todas las propiedades.  

## <a name="bootstrap-data-source-required-properties"></a>Propiedades requeridas por el origen de datos bootstrap  
 La sección Bootstrap se usa en el inicio de sesión para proporcionar acceso a las tablas del sistema. La información de origen de datos bootstrap define el origen de datos donde reside OCM.  

 En los parámetros de origen de datos de bootstrap, no son necesarias todas las configuraciones para todas las plataformas. Si usa una base de datos poco habitual, es posible que deba actualizar la sección [JDBj-JDBC DRIVERS] de **jdeinterop.ini** para declarar el controlador JDBC. En la siguiente lista se identifica la configuración necesaria por plataforma:  

-   **iSeries**. Nombre del origen de datos, tipo de base de datos, nombre de servidor de base de datos, nombre de la base de datos física  

-   **Oracle**. Nombre del origen de datos, tipo de base de datos, nombre de la base de datos física, propietario de la base de datos  

-   **SQL Server**. Nombre del origen de datos, tipo de base de datos, nombre del servidor de la base de datos, puerto del servidor de la base de datos, nombre de la base de datos física, propietario de la base de datos  

-   **SQL Server OLEDB**. Nombre del origen de datos, tipo de base de datos, nombre del servidor de la base de datos, puerto del servidor de la base de datos, nombre de la base de datos física, propietario de la base de datos  

-   **UDB**. Nombre del origen de datos, tipo de base de datos, nombre de la base de datos física, propietario de la base de datos  

## <a name="optimization-configuration"></a>Configuración de optimización  
 La siguiente información puede ayudarle a optimizar la configuración de BizTalk Adapter para JD Edwards EnterpriseOne.  

### <a name="max-concurrent-calls-parameter"></a>Parámetro de llamadas simultáneas máximas  
 Puede usar el parámetro `Max Concurrent Calls` en instancias donde el rendimiento excede de las capacidades de procesamiento de back-end. Agregue el parámetro a los adaptadores en el **propiedades de transporte de puerto de envío** página para activar la protección de sobrecarga del mensaje. El valor predeterminado es -1, lo que significa que las llamadas no están limitadas.  

 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía mensajes al adaptador de transmisión, primero obtiene un lote del adaptador e invoca `TransmitMessage()` en el lote para transmitir cada mensaje. Cuando finaliza, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invoca `Done()` en el lote, y el adaptador empieza a transmitir los mensajes al back-end.  

 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] obtiene varios lotes antes de invocar `Done`, puede que el comando `Done` nunca se ejecute. El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor.  

 Los cambios realizados en el parámetro surte efecto en un minuto. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe recuperar los cambios en la configuración del adaptador guardada en la base de datos SQL.  

### <a name="refresh-agent"></a>Agente de actualización  
 Al seleccionar **Sí** para el **agente de actualización**, forzar los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.  

 Por ejemplo, supongamos que desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o en aquellos casos en los que se han agregado parámetros al servidor y no se muestran en el asistente para adaptadores de Microsoft para su selección.  

 El parámetro Agente de actualización se establece en la ventana Propiedades de transporte y actualiza los agentes de examen y de tiempo de ejecución. runtimeagent.exe se actualiza después de un retraso de un minuto o en la siguiente llamada de envío.  

> [!NOTE]
>  browsingagent.exe no se actualiza hasta que termina la sesión de examen actual. Por ejemplo, debe salir de "Agregar elemento generado …" sesión de exploración y vuelva a escribir para actualizar browsingagent.exe.  

### <a name="single-sign-on"></a>Inicio de sesión único  
 Hay dos métodos que se pueden usar para tener acceso al sistema JD Edwards EnterpriseOne. Puede usar las credenciales de inicio de sesión (parámetros de inicio de sesión de propiedades de transporte) o el inicio de sesión único (SSO). Seleccione **Sí** en el **usar SSO** campo Utilizar inicio de sesión único.  

 Para obtener más información e instrucciones básicas sobre la configuración de Single Sign-On, vea [seguridad en el adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md).

 También debe seleccionar una aplicación afiliada en la lista desplegable. Una aplicación afiliada, creada por herramientas de inicio de sesión único empresariales, representa una aplicación como JD Edwards EnterpriseOne. BizTalk Adapter para JD Edwards EnterpriseOne usa las credenciales para un usuario de la aplicación.  

 Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada. Las credenciales son las del usuario (de la aplicación) que inició el proyecto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

 Para obtener más información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications4.md). También puede consultar la Ayuda en pantalla de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

## <a name="see-also"></a>Vea también  
 [Inicio de sesión único y adaptador de BizTalk para JD Edwards EnterpriseOne](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
