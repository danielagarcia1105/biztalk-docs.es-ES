---
title: Clase SAPConnection en el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPConnection, supported methods, classes, and constructors
ms.assetid: a700602d-8135-4f67-a38b-770357d4e28b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb5a1778fac8577efb3c3c21a10b16f47a026397
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="sapconnection-class-in-the-sap-adapter"></a>Clase SAPConnection en el adaptador SAP
En la siguiente sección se enumera los métodos y propiedades para la **SAPConnection** clase. Representa una conexión ADO.NET en el servidor de aplicaciones de SAP.  
  
 Esto se deriva de **System.Data.Common.DbConnection**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|Get y Set|Vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).|  
|**ConnectionTimeout**|Obtener|No compatible. Devuelve 0.|  
|**Base de datos**|Obtener|Identificador del sistema SAP.|  
|**DataSource**|Obtener|Devuelve el nombre del host del servidor de aplicaciones SAP.|  
|**ServerVersion**|Obtener|Esto muestra el número de versión para la instancia SAP y no la versión del servidor de SAP. Por ejemplo, si el cliente ADO.NET se conecta al servidor SAP versión 4.6 con el número de versión de instancia 620, esta propiedad mostrará 620.|  
|**State**|Obtener|Estado de conexión. Los Estados admitidos son:<br /><br /> -[System.Data.ConnectionState]<br /><br /> -Cierre<br /><br /> -Abierto<br /><br /> -Conectar|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**ChangeDatabase(string)**|No compatible.|  
|**Close()**|Cierra la conexión con el sistema SAP.|  
|**CreateCommand()**|Devuelve un nuevo SAPCommand asociado con esta conexión.|  
|**GetSchema()**|Obtiene la lista de tablas SAP detectadas. Todos los detectados tablas están disponibles en un archivo XML SAPDiscoveredObjects.xml. El archivo se encuentra en \<unidad de instalación\>: \Program Files\Common Files\Microsoft Shared\Adapters\SAP.|  
|**GetSchema(string)**|Obtiene el esquema que se basa en el nombre de la colección. Es compatible con el nombre de la colección "Tables".|  
  
|Nombre|Description|  
|----------|-----------------|  
|**GetSchema (string, string[])**|Obtiene el esquema basado en las restricciones y el nombre de la colección. En la siguiente tabla representa los nombres de colección y restricciones que admite:|  
  
|Nombre|Nombre de la colección|Restricciones|Description|  
|----------|---------------------|------------------|-----------------|  
|**GetSchema (string, string[])**|Tablas|-|Lista de tablas de SAP detectados|  
|**GetSchema (string, string[])**|Procedimientos|-|Lista de RFC detectadas|  
|**GetSchema (string, string[])**|SearchRFCs|arr [0]: expresión de búsqueda|Lista de búsqueda de coincidencias de RFC|  
|**GetSchema (string, string[])**|ImportParameters|arr [1]: nombre RFC|Importación de parámetros de solicitud de cambio|  
|**GetSchema (string, string[])**|ImportParameterColumn|arr [1]: nombre RFC<br /><br /> arr [2]: nombre de parámetro|Esquema de parámetros de importación|  
|**GetSchema (string, string[])**|Método ExportParameters|arr [1]: nombre RFC|Exportar los parámetros de solicitud de cambio|  
|**GetSchema (string, string[])**|ExportParameterColumn|arr [1]: nombre RFC<br /><br /> arr [2]: nombre de parámetro|Exportar el esquema de parámetros|  
|**GetSchema (string, string[])**|TableParameters|arr [1]: nombre RFC|Parámetros de la tabla de solicitud de cambio|  
|**GetSchema (string, string[])**|TableParameterColumn|arr [1]: nombre RFC<br /><br /> arr [2]: nombre de parámetro|Esquema de parámetros de la tabla|  
|**GetSchema (string, string[])**|ChangingParameters|arr [1]: nombre RFC|Cambiar los parámetros de solicitud de cambio|  
|**GetSchema (string, string[])**|ChangingParameterColumn|arr [1]: nombre RFC<br /><br /> arr [2]: nombre de parámetro|Cambiar el esquema de parámetros|  
|**GetSchema (string, string[])**|columnas|arr [1]: nombre de tabla|Esquema de columna de tabla SAP|  
  
|Nombre|Description|  
|----------|-----------------|  
|**Open()**|Abre una conexión de SAP en función de la cadena de conexión.|  
  
> [!NOTE]
>  Excepto los movimientos de la colección de tabla, procedimiento y SearchRFCs, para todas las demás entradas de la colección debe especificar un valor ficticio para arr [0].  
  
## <a name="supported-constructors"></a>Constructores  
  
|Nombre|Description|  
|----------|-----------------|  
|**SAPConnection()**|Crea una instancia de objeto SAPConnection.|  
|**SAPConnection(string)**|Acepta una cadena de conexión de SAP. Produce una excepción si la cadena de conexión no es válida.|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)