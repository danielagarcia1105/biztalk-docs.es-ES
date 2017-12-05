---
title: "Más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77219fb74b7af377953a3761c4d9f241b3a8bd0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a>Más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP
Para establecer la conectividad a un sistema SAP, los clientes ADO.NET deben especificar las propiedades de conexión de SAP en forma de una cadena de conexión. El formato de la cadena de conexión ADO de SAP tiene el siguiente aspecto:  
  
```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  
  
 La cadena de conexión para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] puede tener los siguientes tipos:  
  
-   **Escriba A:** una conexión de aplicación basado en host en el que el URI de conexión especifica un servidor de aplicaciones a través del cual el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se conecta al sistema SAP.  
  
-   **TIPO B:** una conexión con equilibrio de carga en el que el URI de conexión especifica un servidor de mensajes a través del cual el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se conecta al sistema SAP.  
  
-   **TIPO D:** una conexión basada en destino en el que el URI de conexión especifica un destino en el archivo saprfc.ini que contiene los parámetros de conexión para el sistema SAP.  
  
 En la tabla siguiente describe cómo se especifican estas conexiones en el URI de conexión.  
  
|TYPE|Propiedad 1|Propiedad 2|Description|  
|----------|----------------|----------------|-----------------|  
|Un|ASHOST (Host de servidor de aplicación)|SYSNR (número de sistema SAP)|Especifica una conexión basada en host de aplicación.|  
|B|MSHOST (Host de servidor de mensaje)|R3NAME (nombre SAP R3)|Especifica una conexión a través de un servidor de mensajes de equilibrio de carga. Para una conexión de equilibrio de carga, se puede especificar un grupo de servidor opcional.|  
|D|DESTINO (destino que contiene los parámetros de conexión en el archivo saprfc.ini)|-|Especifica una conexión basada en destino. Los parámetros de conexión de SAP se encuentran en el destino especificado en el archivo saprfc.ini. Sólo las conexiones de tipo A y B de tipo pueden especificarse en el destino. **Nota:** si se especifican valores de conexión en el archivo saprfc.ini, asegúrese de que el archivo se encuentra en la misma carpeta como el .exe que tiene acceso al archivo o en una ubicación estándar según sea necesario por el sistema SAP. Para obtener más información, consulte la documentación de SAP.|  
  
 Según el tipo de conexión, la cadena de conexión para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] puede contener las siguientes propiedades.  
  
|Propiedad|Usar para el tipo|Description|  
|--------------|-------------------|-----------------|  
|Host de servidor de aplicación (ASHOST)|Un|Nombre del host del servidor de aplicaciones SAP.|  
|Número del sistema (SYSNR)|Un|El número del sistema SAP|  
|Nombre de grupo de servidores de aplicación (grupo)|B|Nombre del grupo de servidores SAP. Se trata de un grupo de servidores de aplicaciones en una conexión de equilibrio de carga opcional.|  
|Host de servidor de mensaje (MSHOST)|B|Nombre del host del servidor de mensajes SAP|  
|Servicio de servidor de mensajes (MSSERV)|B|Nombre del servicio del servidor de mensajes SAP como se especifica en el \<unidad del sistema\>: archivo \WINDOWS\system32\drivers\etc\services. Si no especifica un valor, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se da por supuesto que sea "sapms\<nombre del sistema R/3\>". Por ejemplo, si el nombre del sistema R/3 se DV1, el adaptador asume el nombre de servicio del servidor de mensaje como "sapmsDV1".<br /><br /> Sin embargo, si la entrada en el archivo de servicios es diferente, debe especificar ese valor.|  
|Nombre del sistema R/3 (R3NAME)|B|El nombre SAP R/3.|  
|Destino (destino)|D|Toma los parámetros de conexión del archivo saprfc.ini.|  
|(Cliente)|A, B, D|El número de cliente SAP|  
|Language (lenguaje)|A, B, D|Lenguaje|  
|Contraseña (PASSWD)|A, B, D|La contraseña de usuario SAP|  
|Nombre de usuario (usuario)|A, B, D|El nombre de usuario para conectarse a un sistema SAP|  
|Habilitar la depuración (AbapDebug) de GUI de SAP|A, B, D|Parámetro opcional que especifica si ABAP depuración desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] está habilitada y si el adaptador utiliza la GUI de SAP para la depuración. El valor puede ser True o False. Si es True, se habilita la depuración de ABAP y se abre la GUI de SAP. El valor predeterminado es False.|  
|Seguimiento RFC SDK(RfcSdkTrace)|A, B, D|Parámetro opcional que especifica si está habilitado el seguimiento de la biblioteca RFC. El valor puede ser True o False. Si es True, está habilitado el seguimiento de la biblioteca de RFC. El valor predeterminado es False.|  
  
> [!NOTE]
>  Los valores proporcionados entre paréntesis en la columna de propiedad son el nombre de las propiedades de conexión que se debe especificar al tiempo que proporciona el URI de conexión a través de una solución de programación. Sin embargo, si está utilizando el complemento DDEX o el Asistente para importación de SQL Server y exportación para usar la interfaz de ADO, se enumeran las propiedades de conexión como nombres descriptivos.  
  
## <a name="example-connection-string-for-type-a"></a>Ejemplo de cadena de conexión para el tipo A  
 Un ejemplo de cadena de conexión para un tipo sería:  
  
```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
> [!NOTE]
>  De forma predeterminada el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] siempre considera que la cadena de conexión para que sea de tipo a.  
  
## <a name="example-connection-string-for-type-b"></a>Ejemplo de cadena de conexión para el tipo B  
 Un ejemplo de cadena de conexión de tipo B sería:  
  
```  
TYPE=B; R3NAME=NAME1; GROUP=ADAPTER; MSHOST=MSSERVER; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
## <a name="example-connection-string-for-type-d"></a>Ejemplo de cadena de conexión para el tipo D  
 Un ejemplo de cadena de conexión de tipo D sería:  
  
```  
TYPE=D; DEST=TESTSAPSRV; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
 Es similar un archivo saprfc.ini de ejemplo:  
  
```  
DEST=TESTSAPSRV  
TYPE=A  
ASHOST=ADAPSAP47  
SYSNR=00  
```  
  
 Para obtener más información acerca del archivo saprfc.ini, consulte [http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457).  
  
 La contraseña para todos los tipos de conexión tres no debe contener comillas dobles. Sin embargo, si la contraseña contiene caracteres especiales, la contraseña debe incluirse entre comillas dobles. Por ejemplo:  
  
```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  
  
> [!IMPORTANT]
>  Debe especificar los parámetros de conexión para la conexión solo un tipo A, B o D. Por ejemplo, si especifica al Host del servidor de aplicaciones en la cadena de conexión, no debe especificar un nombre de Host de servidor de mensaje o el R3NAME.  
  
## <a name="see-also"></a>Vea también  
 [Uso del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)