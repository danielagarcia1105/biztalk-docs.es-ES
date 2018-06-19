---
title: Cuadro de diálogo de propiedades de transporte de PeopleSoft | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PeopleSoft
helpviewer_keywords:
- PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50362e60b982a2d304efea8c26f58019148e5c16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265148"
---
# <a name="peoplesoft-transport-properties-dialog-box"></a>Cuadro de diálogo de propiedades de transporte de PeopleSoft
Use el cuadro de diálogo Propiedades de transporte de PeopleSoft para establecer las propiedades requeridas por el adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Propiedades de adaptador necesarias**||  
|Ruta de acceso de servidor de aplicaciones|Escriba la ruta de acceso para el servidor de PeopleSoft (por ejemplo, `//psserver.domain.com:9000`).|  
|JAVA_HOME|Escriba el nombre de la ubicación JAVA_HOME (por ejemplo, `<drive:>\jdk1.4.2_08`).|  
|Contraseña|Escriba la contraseña para este usuario.|  
|Archivos JAR de PeopleSoft 8.x|Escriba la ruta de acceso para la ubicación de los archivos JAR de PeopleSoft (por ejemplo, `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`).|  
|Nombre de usuario.|Escriba el nombre del usuario y haga clic en **Aceptar**.|  
|**Parámetros adicionales**||  
|Formato de fecha base de datos|Escriba el formato en el que desea que aparezcan las fechas (por ejemplo,**aaaa-MM-DD**).<br /><br /> La fecha tiene un formato diferente cuando se utiliza como clave.|  
|**Control de simultaneidad**||  
|Máximo de llamadas simultáneas|Escriba un valor numérico para el **número máximo de llamadas simultáneas**. Este número representa el número máximo de llamadas concurrentes, por ejemplo, 200.<br /><br /> El valor predeterminado de este campo es -1, lo que significa que no se produce ninguna protección.|  
|**Conexión**||  
|Número máximo de sesiones|Escriba un número para representar el número máximo de sesiones.<br /><br /> El número predeterminado de conexiones es 40.|  
|**Agente de actualización**||  
|Agente de actualización|Seleccione **Sí** para el **agente de actualización** para forzar que los procesos runtimeagent.exe y browsingagent.exe se reinicie automáticamente cuando sea necesario.<br /><br /> Por ejemplo, si desea que el proceso se reinicie automáticamente si éste pierde la conexión con el servidor, o si agrega algo al servidor y no se muestra en el asistente para adaptadores para su selección.|  
|**Inicio de sesión único**||  
|Affiliate Application|Seleccione la aplicación afiliada de la lista solo si está usando el Inicio de sesión único (SSO).|  
|Utilice SSO|Seleccione **Sí** si está usando SSO; una contraseña no es necesaria en este caso. **Nota:** si ya ha escrito una contraseña y desea usar el inicio de sesión único, haga clic en el campo contraseña y seleccione **anular contraseña**.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de interfaz de usuario para el adaptador de BizTalk para PeopleSoft Enterprise](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)