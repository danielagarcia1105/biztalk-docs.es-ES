---
title: Cuadro de diálogo de propiedades de transporte de OneWorld JD Edwards | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JDEOneWorld
helpviewer_keywords:
- Transport Properties dialog box [JD Edwards OneWorld adapters]
ms.assetid: 34d6b5d0-4bd9-4522-a540-8415d3143762
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 625479ef124aad6d7c0b10cde34b45a142ff9f90
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-oneworld-transport-properties-dialog-box"></a>Cuadro de diálogo Propiedades de transporte de OneWorld JD Edwards
Use el cuadro de diálogo Propiedades de transporte de JD Edwards OneWorld para configurar las propiedades requeridas por el adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Propiedades de adaptador necesarias**||  
|Host|Escriba el nombre del equipo del servidor de host (por ejemplo, `actsvr1`).<br /><br /> --o bien<br /><br /> Escriba la dirección IP del equipo (por ejemplo, `123.456.0.789`).|  
|JAVA_HOME|Escriba la ruta de acceso completa a la instalación de JDK.|  
|Entorno JDEdwards|Escriba el nombre de un entorno en JD Edwards OneWorld (por ejemplo, `DV7333`).<br /><br /> DV7333 es un nombre común para el entorno de desarrollo, PY7333 es común para el entorno de prototipo y PD7333 es común para el entorno de producción.|  
|Archivos JAR de JDEdwards|Escriba el nombre de archivo y ruta de acceso completos para cada uno de los archivos JAR:<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-BTSLIBInterop.jar<br /><br /> Cada archivo jar debe estar separado mediante un punto y coma (;) y sin espacio (por ejemplo, `<c:>\Connector.jar;<c:>\Kernel.jar;`).|  
|Contraseña|Escriba una contraseña de usuario. Si no usa Inicio de sesión único (SSO), debe establecer parámetros de credenciales para que el adaptador de BizTalk para JD Edwards OneWorld tenga acceso al sistema del servidor. La contraseña corresponde al nombre de usuario. La contraseña determina los privilegios que se conceden al obtener acceso a la base de datos.|  
|Puerto|Escriba el identificador numérico de envío o puerto de recepción (por ejemplo, `6009`).|  
|Nombre de usuario.|Escriba el nombre del usuario y, a continuación, haga clic en **Aceptar**.|  
|Máximo de llamadas simultáneas|Escriba un valor numérico para el **número máximo de llamadas simultáneas**. Este número representa el número máximo de llamadas simultáneas, por ejemplo, **10**.<br /><br /> El valor predeterminado para este campo es **5**, lo que significa que ninguna protección se produce.|  
|Agente de actualización|Seleccione **Sí** para el **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.<br /><br /> Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.|  
|Affiliate Application|Seleccione la aplicación afiliada de la lista solo si está usando SSO.|  
|Utilice SSO|Seleccione **Sí** si está usando SSO; una contraseña no es necesaria en este caso.|  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications3.md)   
 [Referencia de la interfaz de usuario del adaptador de BizTalk para JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)