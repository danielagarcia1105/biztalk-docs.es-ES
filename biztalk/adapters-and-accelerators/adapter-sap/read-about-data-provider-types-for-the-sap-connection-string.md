---
title: Lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 142afd61966640e004e3dc1160c5ce486984d8e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013429"
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a>Lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP
Para establecer la conectividad a un sistema SAP, los clientes de ADO.NET deben especificar las propiedades de conexión de SAP en forma de una cadena de conexión. El formato de la cadena de conexión ADO de SAP tiene el siguiente aspecto:  

```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  

 La cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] puede tener los siguientes tipos:  

- **R: tipo** una conexión basada en host de aplicación en la que el URI de conexión especifica un servidor de aplicaciones a través del cual el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se conecta al sistema SAP.  

- **TIPO B:** una conexión con equilibrio de carga en la que el URI de conexión especifica un servidor de mensajes a través del cual el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se conecta al sistema SAP.  

- **D: tipo** una conexión basada en destino en la que el URI de conexión especifica un destino en el archivo saprfc.ini que contiene los parámetros de conexión para el sistema SAP.  

  En la tabla siguiente se describe cómo estas conexiones se especifican en el URI de conexión.  

|TYPE|Propiedad 1|Propiedad 2|Descripción|  
|----------|----------------|----------------|-----------------|  
|Un|ASHOST (Host de servidor de aplicaciones)|SYSNR (número de sistema SAP)|Especifica una conexión basada en host de aplicación.|  
|B|MSHOST (Host de servidor de mensaje)|R3NAME (nombre SAP R3)|Especifica una conexión a través de un servidor de mensajes de equilibrio de carga. Para una conexión de equilibrio de carga, se puede especificar un grupo de servidor opcional.|  
|D|DEST (destino que contiene los parámetros de conexión en el archivo saprfc.ini)|-|Especifica una conexión de destino. Los parámetros de conexión de SAP se encuentran en el destino especificado en el archivo saprfc.ini. Solo las conexiones de un tipo y el tipo B se pueden especificar en el destino. **Nota:** si se especifican valores de conexión en el archivo saprfc.ini, asegúrese de que el archivo se encuentra en la misma carpeta, como el .exe que se obtiene acceso al archivo o en una ubicación estándar según sea necesario por el sistema SAP. Para obtener más información, consulte la documentación de SAP.|  

 Según el tipo de conexión, la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] puede contener las siguientes propiedades.  


|               Property                | Utilizado para el tipo |                                                                                                                                                                                                                                               Descripción                                                                                                                                                                                                                                                |
|---------------------------------------|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   Host de servidor de aplicación (ASHOST)    |       Un       |                                                                                                                                                                                                                                 Nombre del host de servidor de aplicaciones SAP.                                                                                                                                                                                                                                 |
|         Número de sistema (SYSNR)         |       Un       |                                                                                                                                                                                                                                          El número de sistema SAP                                                                                                                                                                                                                                           |
| Nombre del grupo de servidores de aplicación (grupo) |       B       |                                                                                                                                                                                              Nombre del grupo de servidores SAP. Se trata de un grupo de servidores de aplicaciones en una conexión de equilibrio de carga opcional.                                                                                                                                                                                              |
|     Host de servidor de mensaje (MSHOST)      |       B       |                                                                                                                                                                                                                                   Nombre de host del servidor de mensajes SAP                                                                                                                                                                                                                                    |
|    Servicio de servidor de mensajes (MSSERV)    |       B       | Nombre del servicio SAP message server como se especifica en el \<unidadDelSistema\>: archivo \WINDOWS\system32\drivers\etc\services. Si no especifica un valor, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se da por supuesto que ésta sea "sapms\<nombre del sistema R/3\>". Por ejemplo, si el nombre del sistema R/3 es DV1, el adaptador asume el nombre de servicio del servidor de mensaje como "sapmsDV1".<br /><br /> Sin embargo, si la entrada del archivo de servicios es diferente, debe especificar ese valor. |
|       Nombre del sistema R/3 (R3NAME)        |       B       |                                                                                                                                                                                                                                            El nombre SAP R/3.                                                                                                                                                                                                                                             |
|          Destino (DEST)           |       D       |                                                                                                                                                                                                                        Toma los parámetros de conexión del archivo saprfc.ini.                                                                                                                                                                                                                         |
|            (Cliente)            |     A, B Y D     |                                                                                                                                                                                                                                          El número de cliente SAP                                                                                                                                                                                                                                           |
|            Language (idioma)            |     A, B Y D     |                                                                                                                                                                                                                                                 Idioma                                                                                                                                                                                                                                                 |
|           Contraseña (PASSWD)           |     A, B Y D     |                                                                                                                                                                                                                                          La contraseña de usuario SAP                                                                                                                                                                                                                                           |
|            Nombre de usuario (usuario)            |     A, B Y D     |                                                                                                                                                                                                                                El nombre de usuario para conectarse a un sistema SAP                                                                                                                                                                                                                                 |
| Habilitar la depuración (AbapDebug) de GUI de SAP  |     A, B Y D     |                                                                                      Parámetro opcional que especifica si la depuración de ABAP de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] está habilitada y si el adaptador utiliza la GUI de SAP para la depuración. El valor puede ser True o False; Si es True, se habilita la depuración de ABAP y se abre la GUI de SAP. El valor predeterminado es False.                                                                                      |
|      Seguimiento de RFC SDK(RfcSdkTrace)       |     A, B Y D     |                                                                                                                                                                 Parámetro opcional que especifica si está habilitada la traza de la biblioteca RFC. El valor puede ser True o False; Si es True, está habilitado el seguimiento de la biblioteca de RFC. El valor predeterminado es False.                                                                                                                                                                 |

> [!NOTE]
>  Los valores proporcionados entre paréntesis en la columna propiedad son el nombre de las propiedades de conexión que se debe especificar proporcionando el URI de conexión a través de una solución de programación. Sin embargo, si utiliza el complemento DDEX o el Asistente para importación de SQL Server y exportación para usar la interfaz ADO, se enumeran las propiedades de conexión como los nombres descriptivos.  

## <a name="example-connection-string-for-type-a"></a>Ejemplo de cadena de conexión para el tipo A  
 Un ejemplo de cadena de conexión para un tipo sería:  

```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  

> [!NOTE]
>  De forma predeterminada el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] siempre considera que la cadena de conexión sea de tipo a.  

## <a name="example-connection-string-for-type-b"></a>Ejemplo de cadena de conexión para el tipo B  
 Un ejemplo de cadena de conexión para el tipo B sería:  

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

 Para obtener más información acerca del archivo saprfc.ini, consulte [ http://go.microsoft.com/fwlink/?LinkId=91457 ](http://go.microsoft.com/fwlink/?LinkId=91457).  

 La contraseña para todos los tipos de conexión de tres no puede contener comillas dobles. Sin embargo, si la contraseña contiene caracteres especiales, la contraseña debe incluirse entre comillas dobles. Por ejemplo:  

```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  

> [!IMPORTANT]
>  Debe especificar los parámetros de conexión para la conexión solo un tipo A, B o D. Por ejemplo, si especifica al Host del servidor de aplicaciones en la cadena de conexión, no debe especificar un nombre de Host del servidor de mensaje o el R3NAME.  

## <a name="see-also"></a>Vea también  
 [Uso del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)