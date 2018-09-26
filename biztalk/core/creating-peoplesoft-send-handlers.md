---
title: Crear artefactos de envío del adaptador de PeopleSoft | Documentos de Microsoft
description: Crear el puerto de envío, las propiedades de transporte de envío y actualizar el número máximo de llamadas simultáneas para enviar mensajes a PeopleSoft mediante el adaptador de PeopleSoft Enterprise en BizTalk Server
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc559f4e3c25560540a171b3f47ff25e6f34e89
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25969554"
---
# <a name="create-peoplesoft-send-artifacts"></a>Crear artefactos de envío de PeopleSoft
Microsoft BizTalk Adapter para PeopleSoft Enterprise obtiene acceso a PeopleSoft y explora los componentes disponibles o procesa las solicitudes SOAP En este tema se muestra cómo crear los artefactos de envío en administración de BizTalk Server para usar el adaptador de PeopleSoft.


## <a name="create-the-send-port"></a>Crear el puerto de envío

1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación deseada.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío**, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío. Por ejemplo, escriba `SSOSendToPeopleSoft`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
    6.  Seleccione **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de PeopleSoft**, realice lo siguiente:  
  
    1.  Expanda **propiedades de adaptador necesarias**y escriba **ruta de acceso de servidor de aplicación**, **JAVA_HOME**, **nombre de usuario**,  **contraseña**y el archivo Jar para la conexión en el sistema Peoplesoft.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema PeopleSoft.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Seleccione **Aceptar**.  
  
5.  Seleccione **Aceptar**.

## <a name="set-the-transport-properties"></a>Establecer las propiedades de transporte
Las propiedades de transporte de PeopleSoft se usan en el diseño y el tiempo de ejecución. En el **propiedades de transporte** cuadro de diálogo, Establece los parámetros de conexión y credenciales específicas para el sistema de servidor y los objetos que está intentando obtener acceso.  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  Expanda las propiedades necesarias del adaptador y complete toda la información que necesite para conectar con el servidor de PeopleSoft.  
  
     Defina los parámetros de configuración para conectar el adaptador de Microsoft BizTalk para PeopleSoft Enterprise a PeopleSoft Enterprise. Estos datos distinguen entre mayúsculas y minúsculas.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|Cadena que representa el equipo y el puerto en que se ejecuta y escucha el servidor de aplicaciones de PeopleSoft. La sintaxis de la ruta de acceso de dirección URL para la aplicación PeopleSoft 8 es / / < nombre_equipo >:\<puerto\>. Pida al administrador de PeopleSoft para la \<puerto\> valor. El \<puerto\> valor es el JOLT puerto de escucha de protocolo, no al puerto del servidor de aplicaciones. El puerto JOLT predeterminado es 9000.|  
    |`JAVA_HOME`|Establezca la variable JAVA_HOME para que apunte a la instalación de JDK, por ejemplo: **C:\j2sdk1.4.2_08**.|  
    |`Password`|Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.<br /><br /> Cadena que representa la contraseña del usuario para iniciar sesión en un sistema de PeopleSoft. Los caracteres no aparecen, pero están representados por asteriscos (*).|  
    |`PeopleSoft 8.x Jar Files`|Para usar interfaces de componentes (solo para PeopleSoft 8), debe actualizar CLASSPATH para que incluya el archivo jar de la interfaz de componentes de PeopleSoft. For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.|  
    |`User Name`|Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.<br /><br /> Cadena que representa el nombre de usuario necesario para iniciar sesión en un sistema de PeopleSoft.|  
  
2.  Escriba un **parámetros adicionales** valor cuando se usa una fecha como una clave; tiene un formato diferente. AAAA-MM-DD es el formato predeterminado.  
  
3.  Escriba un **control de simultaneidad** valor que represente el número de llamadas, por ejemplo, 200, en **número máximo de llamadas simultáneas** si es necesario.  
  
     El **número máximo de llamadas simultáneas** parámetro activa una protección de sobrecarga si el servidor back-end no puede procesar la cantidad de datos. Una llamada concurrente es una solicitud para la que el adaptador todavía no tiene una respuesta. Establecer **número máximo de llamadas simultáneas** en casos donde el rendimiento excede las capacidades de procesamiento de back-end.  
  
     El valor predeterminado de este campo es -1, lo que significa que no se produce ninguna protección.  
  
     Si BizTalk Server envía una solicitud al adaptador de transmisión y la cantidad de llamadas es igual a o supera el valor establecido para **número máximo de llamadas simultáneas**, el proceso de envío de la solicitud se guarda hasta que el de llamadas concurrentes número sea inferior al valor establecido.  

## <a name="update-max-concurrent-calls"></a>Actualizar máximo de llamadas simultáneas

El parámetro `Max Concurrent Calls` es una característica que permite optimizar la configuración. Este parámetro se usa en aquellas instancias en las que el rendimiento excede las capacidades de procesamiento del servidor. Puede agregar el parámetro a los adaptadores en el **propiedades de transporte de puerto de envío** cuadro de diálogo para activar la protección de sobrecarga de mensajes. El valor predeterminado es -1, lo que significa que las llamadas no están limitadas.  
  
Cuando el servidor BizTalk Server envía mensajes al adaptador de transmisión, recibe, en primer lugar, un lote del adaptador y, seguidamente, invoca `TransmitMessage()` en el lote para transmitir los distintos mensajes. A continuación, el servidor BizTalk Server invoca `Done()` en el lote, y el adaptador comienza a transmitir los mensajes al servidor. Si el servidor obtiene varios lotes antes de que se invoque `Done`, puede que el comando `Done` nunca se produzca. El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor. Este parámetro se aplica transcurrido un minuto. BizTalk Server debe recuperar los cambios de la configuración del adaptador que se haya guardado en la base de datos de SQL.  
  
### <a name="change-the-max-concurrent-calls-parameter"></a>Cambie el parámetro de número máximo de llamadas simultáneas  
  
1.  En el **propiedades de transporte de puerto de envío** diálogo cuadro, escriba un **conexión** valor.  
  
     El valor predeterminado es 40 sesiones. Si usa un valor más pequeño, podría experimentar una degradación del rendimiento en tiempo de ejecución. También puede ocurrir lo contrario, un valor mayor puede sobrepasar la capacidad del servidor y resultar en errores de tiempo de ejecución.  
  
2.  Seleccione **Sí** para **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.  
  
     Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.  
  
     El **agente de actualización** parámetro actualiza la exploración y los agentes de tiempo de ejecución. El archivo runtimeagent.exe se actualiza tras una demora de un minuto o en la siguiente llamada de envío.  
  
3.  Proporcione credenciales para tener acceso al sistema PeopleSoft.  
  
     Puede usar dos métodos para tener acceso al sistema:  
  
    -   Credenciales de inicio de sesión (parámetros de inicio de sesión de propiedades de transporte)  
  
    -   Inicio de sesión único  
  
4.  Seleccione **Sí** para **usar SSO** usar Single Sign-On.  
  
    > [!NOTE]
    >  Para obtener más información, consulte [proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md). 
  
5.  Seleccione una aplicación afiliada en la lista.  
  
     Una aplicación afiliada, creada por herramientas de inicio de sesión único de la empresa, representa una aplicación como PeopleSoft. El adaptador de Microsoft BizTalk para PeopleSoft Enterprise usa las credenciales del usuario de una aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada. Las credenciales son aquellas que pertenecen al usuario (al usuario de la aplicación) que inició el proyecto de BizTalk.  
  
    > [!NOTE]
    >  Para obtener más información sobre cómo crear aplicaciones afiliadas, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications2.md), o la Ayuda en pantalla de Microsoft BizTalk Server.  
  
6.  Después de proporcionar toda la información necesaria para aceptar la información de conexión, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
     Se deben establecer los parámetros de conexión para el adaptador de BizTalk para PeopleSoft Enterprise para tener acceso a PeopleSoft.  
  

## <a name="next"></a>Siguiente
  
[Importar esquemas de PeopleSoft en proyectos de BizTalk Server](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[Recibir desde PeopleSoft](../core/receiving-from-peoplesoft.md)