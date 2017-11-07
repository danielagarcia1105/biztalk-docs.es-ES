---
title: "Cuadro de diálogo de propiedades de JD Edwards EnterpriseOne transporte | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: JDE
helpviewer_keywords: Transport Properties dialog box [JD Edwards EnterpriseOne adapters
ms.assetid: 6a37eeb2-af91-4f58-9699-7a7cbe296862
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f510009161a21e64d7bbf80c7b1fda20c0c018aa
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-enterpriseone-transport-properties-dialog-box"></a>Cuadro de diálogo Propiedades de transporte de JD Edwards EnterpriseOne
Use el cuadro de diálogo Propiedades de transporte de JD Edwards EnterpriseOne para configurar las propiedades requeridas por el adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Propiedades de adaptador necesarias**||  
|Host|Escriba el nombre del equipo del servidor de host (por ejemplo, `actsvr1`).<br /><br /> -O bien-<br /><br /> Escriba la dirección IP del equipo (por ejemplo, `123.456.0.789`).|  
|JAVA_HOME|Escriba la ruta de acceso completa a la instalación de JDK (por ejemplo,<br /><br /> `C:\jdk1sdk1.4.2_07`).|  
|Entorno JDEdwards|Escriba el nombre de un entorno en JD Edwards EnterpriseOne (por ejemplo, `DV7333`).<br /><br /> DV7333 es un nombre común para el entorno de desarrollo; PY7333 es común para el entorno de prototipo. y PD7333 es común para el entorno de producción.|  
|Archivos JAR de JDEdwards|Escriba el nombre de archivo y ruta de acceso completos para cada uno de los archivos JAR:<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br /><br /> Cada archivo jar debe estar separado mediante un punto y coma (;) y sin espacio (por ejemplo:<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`).|  
|Contraseña|Escriba una contraseña de usuario. Si lo hace no useSingle Sign-On (SSO), debe establecer parámetros de credenciales para el adaptador de BizTalk para JD Edwards EnterpriseOne tenga acceso al sistema de servidor. La contraseña corresponde al nombre de usuario. La contraseña determina los privilegios que se conceden cuando se tiene acceso a la base de datos.|  
|Puerto|Escriba el identificador numérico de envío o puerto de recepción (por ejemplo, `6009`).|  
|Nombre de usuario|Escriba el nombre del usuario y haga clic en **Aceptar**.|  
|**Propiedades necesarias del origen de datos Bootstrap**||  
|Data Source Name|Escriba el nombre del origen de datos. Este nombre es obligatorio para todos los tipos de datos.|  
|Propietario de la base de datos|Escribir el nombre del propietario de la base de datos|  
|Nombre del servidor de bases de datos|Escribir el nombre del servidor de la base de datos|  
|Puerto de servidor de bases de datos|Escriba el número de identificación del puerto de servidor de bases de datos.|  
|Tipo de base de datos|Escriba un carácter único para el tipo de base de datos. Por ejemplo:<br /><br /> **¿** -ISeries<br /><br /> **O** -Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** -UDB|  
|Nombre de la base de datos física|Escriba el nombre de la base de datos física. Este nombre es obligatorio para todos los tipos de bases de datos.|  
|**Control de simultaneidad**||  
|Máximo de llamadas simultáneas|Escriba un valor numérico para el **número máximo de llamadas simultáneas**. Este número representa el número máximo de llamadas simultáneas, por ejemplo, **10**.<br /><br /> El valor predeterminado para este campo es 5.|  
|**Agente de actualización**||  
|Agente de actualización|Seleccione **Sí** para el **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.<br /><br /> Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores de Microsoft para su selección.|  
|**Servidor de seguridad**||  
|Nombre del servidor de seguridad|Escriba el nombre del servidor de seguridad. Este campo es opcional y toma de forma predeterminada el valor del host de servidor JD Edwards.|  
|Conexión del nombre de servicio|Escriba el número de puerto usado por el servidor de seguridad y la asignación de configuración del objeto (OCM). El valor predeterminado es el puerto del servidor JD Edwards.|  
|**Inicio de sesión único**||  
|Affiliate Application|Seleccione la aplicación afiliada de la lista desplegable solo si está usando el Inicio de sesión único (SSO).|  
|Utilice SSO|Seleccione **Sí** si está usando SSO; una contraseña no es necesaria en este caso.|  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications4.md)   
 [Referencia de la interfaz de usuario para el adaptador de BizTalk para JD Edwards EnterpriseOne](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md)