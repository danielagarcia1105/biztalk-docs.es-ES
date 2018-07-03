---
title: Ejecutar procedimientos almacenados de SQL Server con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245626a7-f546-4aca-90df-c0579139a872
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6515baa313fc6b68c62556ad5b5883500cfde8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021557"
---
# <a name="execute-stored-procedures-in-sql-server-using-the-sql-adapter"></a>Ejecutar procedimientos almacenados de SQL Server con el adaptador de SQL
El Transact-SQL y procedimientos almacenados de CLR en SQL Server se exponen como operaciones en [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] bajo el **procedimientos** nodo mientras usa la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Los nombres de las operaciones exponen por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] son los mismos que el nombre del procedimiento almacenado en SQL Server. Todos los parámetros del procedimiento almacenado se exponen en la operación correspondiente. El parámetro de salida contiene el valor devuelto del procedimiento almacenado. El conjunto de resultados del procedimiento almacenado es una matriz de conjunto de datos. Para obtener más información sobre el conjunto de datos, vea [ http://go.microsoft.com/fwlink/?LinkId=196853 ](http://go.microsoft.com/fwlink/?LinkId=196853). La información de esquema del objeto de destino se obtiene como parte del mensaje de respuesta en tiempo de ejecución.  

 Sin embargo, si desea obtener la información del esquema del objeto de destino en tiempo de diseño, debe generar esquemas para los procedimientos en el **Strongly-Typed procedimientos** nodo en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Tenga en cuenta que los mismos procedimientos almacenados aparecen bajo el **procedimientos** y **Strongly-Typed procedimientos** nodo. El valor devuelto del procedimiento almacenado es fuertemente tipado y no solamente una matriz de conjunto de datos. Como la información de esquema está disponible en el tiempo de diseño, puede usarlo para asignar el esquema del procedimiento almacenado a otro esquema para una operación distinta. Por ejemplo, puede asignar el esquema generado para un procedimiento fuertemente tipado para el esquema generado para la operación de inserción en una tabla de base de datos.  

> [!NOTE]
>  No podrá ver la información de esquema en tiempo de diseño para un procedimiento almacenado fuertemente tipados si:  
> 
> - Utiliza un cursor, que es un valor devuelto de otro procedimiento almacenado, como el parámetro de entrada para el procedimiento almacenado fuertemente tipado.  
>   -   Es un procedimiento almacenado CLR que realiza algunas operaciones en una tabla.  

## <a name="support-for-stored-procedures-with-for-xml-clause"></a>Compatibilidad con procedimientos almacenados con la cláusula FOR XML  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] también le permite ejecutar procedimientos almacenados que tienen una instrucción SELECT con una cláusula FOR XML. Se utiliza una cláusula FOR XML en una instrucción SELECT para devolver los resultados como XML en lugar de un conjunto de filas. Para obtener más información acerca de la cláusula FOR XML, vea [ http://go.microsoft.com/fwlink/?LinkId=131402 ](http://go.microsoft.com/fwlink/?LinkId=131402).  

> [!NOTE]
>  "Nativo" [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] disponibles con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] admite solo los procedimientos almacenan que devuelven XML, es decir, tienen la cláusula FOR XML en la instrucción SELECT. Con la compatibilidad con procedimientos almacenados con la cláusula FOR XML, puede ejecutar estos procedimientos almacenados con el basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] sin realizar cambios en la definición del procedimiento almacenado.  

## <a name="support-for-stored-procedures-with-temporary-tables"></a>Compatibilidad con procedimientos almacenados con tablas temporales  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] le permite generar metadatos para los procedimientos almacenados que contienen las tablas temporales en sus definiciones. Sin embargo, para tales procedimientos almacenados debe generar metadatos seleccionando los procedimientos almacenados solo desde el **procedimientos** nodo, al usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. El adaptador no admite generar metadatos para dichos procedimientos almacenados en el **Strongly-Typed procedimientos** nodo.  

## <a name="support-for-result-sets-containing-columns-without-names-or-with-same-names"></a>Compatibilidad con conjuntos de resultados que contiene las columnas sin nombre o con el mismo nombre  
 La siguiente tabla muestra cómo el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] controla las columnas sin nombres y los mismos nombres en los conjuntos de resultados para los procedimientos almacenados y procedimientos almacenados fuertemente tipados.  


|    Contiene el conjunto de resultados...     |                                                                                                                                                       Procedimiento almacenado                                                                                                                                                       |                                                                                                           Procedimientos almacenados fuertemente tipados                                                                                                            |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  **Columnas sin nombre**  | El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] genera un nombre para la columna de la siguiente manera: se genera un identificador único (GUID) para la columna sin "-" (guión), y, a continuación, la cadena de GUID viene precedida por un "C" porque el GUID generado puede comenzar con un dígito, pero no un nombre de etiqueta XML. |                                El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] genera el siguiente nombre para la columna: "UnNamedColumn [column_index]", donde se inicia column_index entre '0'.                                |
| **Columnas con los mismos nombres** |                                                                                Los nombres de las columnas que no sea la primera de ellas se anexan con "*" (carácter de subrayado) seguido de un GUID aleatorio sin "-" (guión). Por ejemplo: "\\*[GUID]".                                                                                | El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite las columnas con los mismos nombres en los conjuntos de resultados y produce una excepción. **Importante:** debe asegurarse de que los nombres de columna en un conjunto de resultados tienen nombres únicos. |

> [!NOTE]
>  En general, se recomienda que todas las columnas en un resultado de establecen para procedimientos almacenados y procedimientos almacenados fuertemente tipada deben denominarse y tienen nombres únicos.  

 Para obtener más información acerca de:  

-   Cómo ejecutar procedimientos almacenados, vea [ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).  

-   Cómo ejecutar procedimientos almacenados con una cláusula FOR XML, vea [ejecutar procedimientos almacenados con una cláusula FOR XML en SQL Server mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md).  

-   Los esquemas para los procedimientos almacenados de mensajes, vea [esquemas de mensaje para procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).  

## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)