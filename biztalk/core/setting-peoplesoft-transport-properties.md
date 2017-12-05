---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 1772a30ce5496a3a14866da168a56958bc3bc78c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="setting-peoplesoft-transport-properties"></a>Definición de las propiedades de transporte de PeopleSoft
Las propiedades de transporte de PeopleSoft se usan en el diseño y el tiempo de ejecución. En el **propiedades de transporte** cuadro de diálogo, Establece los parámetros de conexión y credenciales específicas para el sistema de servidor y los objetos que está intentando obtener acceso.  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  Expanda las propiedades necesarias del adaptador y complete toda la información que necesite para conectar con el servidor de PeopleSoft.  
  
     Defina los parámetros de configuración para conectar el adaptador de Microsoft BizTalk para PeopleSoft Enterprise a PeopleSoft Enterprise. Estos datos distinguen entre mayúsculas y minúsculas.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|Cadena que representa el equipo y el puerto en que se ejecuta y escucha el servidor de aplicaciones de PeopleSoft. La sintaxis de la ruta de acceso de dirección URL para la aplicación PeopleSoft 8 es / / < nombre_equipo >:\<puerto\>. Pida al administrador de PeopleSoft para la \<puerto\> valor. El \<puerto\> valor es el JOLT puerto de escucha de protocolo, no al puerto del servidor de aplicaciones. El puerto JOLT predeterminado es 9000.|  
    |`JAVA_HOME`|Establezca la variable JAVA_HOME para que apunte a la instalación de JDK, por ejemplo: **C:\j2sdk1.4.2_08**.|  
    |`Password`|Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.<br /><br /> Cadena que representa la contraseña del usuario para iniciar sesión en un sistema de PeopleSoft. Los caracteres no aparecen, pero están representados por asteriscos (*).|  
    |`PeopleSoft 8.x Jar Files`|Para usar interfaces de componentes (solo para PeopleSoft 8), debe actualizar CLASSPATH para que incluya el archivo jar de la interfaz de componentes de PeopleSoft. Por ejemplo: **\web\PSJOA\psjoa.jar < PeopleSoft_Home >**.|  
    |`User Name`|Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.<br /><br /> Cadena que representa el nombre de usuario necesario para iniciar sesión en un sistema de PeopleSoft.|  
  
2.  Escriba un **parámetros adicionales** valor cuando se usa una fecha como una clave; tiene un formato diferente. AAAA-MM-DD es el formato predeterminado.  
  
3.  Escriba un **control de simultaneidad** valor que represente el número de llamadas, por ejemplo, 200, en **número máximo de llamadas simultáneas** si es necesario.  
  
     El **número máximo de llamadas simultáneas** parámetro activa una protección de sobrecarga si el servidor back-end no puede procesar la cantidad de datos. Una llamada concurrente es una solicitud para la que el adaptador todavía no tiene una respuesta. Establecer **número máximo de llamadas simultáneas** en casos donde el rendimiento excede las capacidades de procesamiento de back-end.  
  
     El valor predeterminado de este campo es -1, lo que significa que no se produce ninguna protección.  
  
     Si BizTalk Server envía una solicitud al adaptador de transmisión y la cantidad de llamadas es igual a o supera el valor establecido para **número máximo de llamadas simultáneas**, el proceso de envío de la solicitud se guarda hasta que el de llamadas concurrentes número sea inferior al valor establecido.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de PeopleSoft](../core/creating-peoplesoft-send-handlers.md)