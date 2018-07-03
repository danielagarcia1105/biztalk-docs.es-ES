---
title: RFC personalizadas usadas por el proveedor de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b359fc893b8616fd4fb7339e9efbc42d7d3e13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992725"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a>RFC personalizadas usadas por el proveedor de SAP
El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] proporciona las siguientes RFC personalizadas que usa internamente para realizar operaciones en el sistema SAP.  
  
- **RFC Z_EXTRACT_DATA_OO**. La extracción de datos RFC, Z_EXTRACT_DATA_OO, extrae datos de tablas o vistas en el sistema SAP R/3, convierte los datos y devuelve los datos de forma sincrónica en una tabla de SQL Server o volcados de datos a un archivo plano. El Z_EXTRACT_DATA_OO se usa para realizar la operación de selección con las cláusulas WHERE. El rendimiento de esta solicitud de cambio depende del hardware del sistema SAP.  
  
   Para obtener información sobre cómo se asignan los tipos de datos de .NET y SAP Z_EXTRACT_DATA_OO RFC, consulte [Data Type Mapping for Custom RFC](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md).  
  
- **RFC Z_EXECUTE_SAP_QUERY**. Esta RFC se usa por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] para ejecutar consultas que ya están definidas en el sistema SAP. Este RFC ejecuta internamente la RFC de SAP, RSAQ_REMOTE_QUERY_CALL. Las consultas SAP son consultas que se crean gráficamente mediante la GUI de SAP mediante la selección de las tablas, columnas, parámetros de entrada, el criterio de ordenación del conjunto de resultados, etcetera. Mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ahora puede ejecutar estas consultas SAP desde un cliente ADO.NET.  
  
   Todos los valores devueltos por la operación de EXECQUERY son del tipo de cadena.  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a>Limitaciones relacionadas a la RFC Z_EXTRACT_DATA_OO  
  
-   La RFC Z_EXTRACT_DATA_OO admite la lectura de datos de tablas que cumplen las condiciones siguientes:  
  
    -   TabClass para la tabla es TRANSP, clúster o grupo.  
  
    -   TabClass es la vista y ViewClass es D o P.  
  
-   Z_EXTRACT_DATA_OO no admite tablas de clúster de recursos humanos, por ejemplo PCL1, PCL2, PCL3, PCL4, PCL5.  
  
-   El número de filas que se pueden extraer Z_EXTRACT_DATA_OO depende de los recursos de hardware en el servidor SAP.  
  
-   Todos los datos extraídos se devuelven en orden de las claves principales.  
  
-   No se admiten tablas o vistas que contienen los tipos de datos de longitud variable de cadena, SSTRING y RAWSTRING. No se puede extraer las tablas o vistas que contienen estos tipos de datos.  
  
-   Z_EXTRACT_DATA_OO ejecuta sale de la conversión en todos los campos que tienen salidas de conversión asignados a ellos. Los valores convertidos resultantes deben especificarse en la cláusula WHERE de una instrucción SELECT. También se devuelven los valores convertidos. Esto puede provocar incoherencias entre los resultados devueltos por Z_EXTRACT_DATA_OO y los resultados devueltos en el Explorador de datos SAP (SE16).  
  
-   Las tablas seleccionadas no pueden contener nombres de campo que son nombres reservados de ABAP (por ejemplo, la conexión).  
  
-   Debido a una limitación en el procesador de consultas de SAP R/3 4.6C, versión valores para los campos de tipo entero INT4 debe ser mayor o igual que-999999999 en la cláusula WHERE. No se extraerá las filas con valores de INT4 menor-999999999 independientemente de si se selecciona el campo que contiene el valor.  
  
-   Tipos de valores para todos los datos en una cláusula WHERE están limitados a 256 caracteres cuando se ejecuta en la versión 4.7 o superior; del sistema SAP el límite es de 70 caracteres en la versión 4.6c. Para los valores de tipo de datos sin procesar, estos límites se reduce a la mitad a 35 y 128 caracteres, respectivamente. No hay ningún límite en la longitud del tipo de datos RAW y LCHR cuando se devuelven como resultado.  
  
-   En SAP R/3 4.6C, versión campos en el lugar en la cláusula se limitan a 70 caracteres.  
  
-   En SAP R/3 4.6C versión, no se puede extraer todas las tablas con un campo de clave principal que tiene una longitud mayor que 70 caracteres de la salida.  
  
-   En SAP R/3, versión 4.6 c, las tablas y vistas que contienen tipos de datos de longitud variable (`VARC`) no se admiten y las tablas y vistas que contienen estos tipos de datos no se puede extraer del origen de datos mediante la llamada de función Z_EXTRACT_DATA_OO.  
  
-   En el modo de archivo, la llamada de función Z_EXTRACT_DATA_OO no comprueba si un archivo de destino ya está abierto, por sí mismo o por otra aplicación. Por lo tanto, la función incorrectamente puede escribir en un archivo abierto mientras se anexan al mismo tiempo los datos en el mismo archivo. Se produce ningún error.  
  
-   En el modo de archivo, la llamada de función Z_EXTRACT_DATA_OO puede sobrescribir archivos existentes. Asegúrese de que los usuarios SAP que usan Z_EXTRACT_DATA_OO han restringido el acceso de sistema de archivos por medio de S_DATASET.  
  
## <a name="security-considerations-with-the-custom-rfc"></a>Consideraciones de seguridad con la RFC personalizada  
  
-   `Security Issue`: No hay posibles para exponer los datos que se escriben en archivos planos, si no le ayudan a proteger esos archivos.  
  
     `Best practice`: Mejorar la seguridad del recurso compartido al que se escriban los datos mediante la llamada de función Z_EXTRACT_DATA_OO en modo de archivo sin formato.  
  
-   `Security Issue`: Es posible que se deben sobrescribir los archivos en cualquier recurso compartido que se escribe en el uso de la llamada de función Z_EXTRACT_DATA_OO en modo de archivo. Esto puede ocurrir en cualquier archivo en cualquier recurso compartido al que la cuenta de dominio SAP tiene acceso.  
  
     `Best practice`: Se esfuerzan por proteger todos los recursos compartidos a los que la cuenta de dominio SAP tiene acceso.  
  
-   `Security Issue`: Los usuarios tienen la capacidad para inspeccionar datos (o "Examinar") durante la transmisión desde un servidor de aplicaciones de SAP para su recurso compartido de archivos de destino, en los casos, cuando el destino está en un equipo físico diferente.  
  
     `Best practice`: Use IPsec u otro método adecuado para ayudar a proteger la comunicación entre el servidor SAP y sus destinos.  
  
## <a name="see-also"></a>Vea también  
 [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)