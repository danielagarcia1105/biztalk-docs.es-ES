---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2b0a1aa81971e3e086881e23bcfd6d7ba5d5799d
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24012883"
---
# <a name="optimize-configuration"></a>Optimizar configuración
Esta sección contiene información acerca de cómo optimizar la configuración del adaptador de BizTalk para PeopleSoft Enterprise e incluye una descripción de los parámetros necesarios para configurar el adaptador.  
  
## <a name="message-overload-protection"></a>Protección ante sobrecarga de mensajes  
 El parámetro `Max Concurrent Calls` es una característica que permite optimizar la configuración. Este parámetro se usa en aquellas instancias en las que el rendimiento excede las capacidades de procesamiento del servidor. Puede agregar el parámetro a los adaptadores en el **propiedades de transporte de puerto de envío** cuadro de diálogo para activar la protección de sobrecarga de mensajes. El valor predeterminado es -1, lo que significa que las llamadas no están limitadas.  
  
 Cuando el servidor BizTalk Server envía mensajes al adaptador de transmisión, recibe, en primer lugar, un lote del adaptador y, seguidamente, invoca `TransmitMessage()` en el lote para transmitir los distintos mensajes. A continuación, el servidor BizTalk Server invoca `Done()` en el lote, y el adaptador comienza a transmitir los mensajes al servidor. Si el servidor obtiene varios lotes antes de que se invoque `Done`, puede que el comando `Done` nunca se produzca. El establecimiento del número máximo de mensajes que se van a incluir en un lote le permite controlar los mensajes que se van a transmitir al servidor. Este parámetro se aplica transcurrido un minuto. BizTalk Server debe recuperar los cambios de la configuración del adaptador que se haya guardado en la base de datos de SQL.  
  
## <a name="change-the-max-concurrent-calls-parameter"></a>Cambie el parámetro de número máximo de llamadas simultáneas  
  
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
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de PeopleSoft](../core/creating-peoplesoft-send-handlers.md)