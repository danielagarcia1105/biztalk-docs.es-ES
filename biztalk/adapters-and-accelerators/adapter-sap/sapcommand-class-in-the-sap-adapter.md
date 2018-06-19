---
title: Clase SAPCommand en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPCommand, supported methods, classes, and constructors
ms.assetid: 55ad334e-1cc3-47c1-8764-be0f4e93f8b5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee083ed5afea06a5d350e9d73a9103adf157d8b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216564"
---
# <a name="sapcommand-class-in-the-sap-adapter"></a>Clase SAPCommand en el adaptador SAP
Este comando representa una consulta SQL que se ejecuta en el back-end SAP. El [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] admite actualmente solo las instrucciones SELECT y EXEC. Las instrucciones SELECT habilitar extracción de datos de una sola tabla SAP y las instrucciones de EXEC permiten a los usuarios ejecutar RFC en el servidor SAP.  
  
 Esto se deriva de **System.Data.Common.DbCommand**.  
  
## <a name="supported-properties"></a>Propiedades admitidas  
  
|Nombre|Get/Set.|Description|  
|----------|--------------|-----------------|  
|**CommandText**|Get y Set|Es compatible con las instrucciones SELECT y EXEC. Para obtener más información acerca de la instrucción SELECT, vea [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md). Para obtener más información acerca de la instrucción EXEC, consulte [sintaxis de una instrucción EXEC en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).|  
|**CommandTimeout**|Get y Set|No compatible.|  
|**CommandType**|Get y Set|CommandType.Text compatible.|  
|**Conexión**|Get y Set|La conexión de SAP subyacente en el que se ejecutará el comando.|  
|**DesignTimeVisible**|Obtener|No compatible. Devuelve false.|  
|**Parámetros**|Obtener|Colección de parámetros utilizada para este comando.|  
|**UpdatedRowSource**|-|No compatible.|  
  
## <a name="supported-methods"></a>Métodos admitidos  
  
|Nombre|Description|  
|----------|-----------------|  
|**Cancel()**|Cancela el comando al recuperar datos mediante varios lotes. Cancelación se produce después de recupera un lote.|  
|**ExecuteNonQuery()**|No genera ningún DataReader. Sin embargo, los valores estarán disponibles a través de parámetros enlazados.|  
|**ExecuteReader()**|Da como resultado un DataReader con todos los parámetros de la tabla y el tipo complejo de exportación como conjuntos de resultados. Los valores también se pueden obtener a través de parámetros enlazados.|  
|**ExecuteReader(CommandBehavior)**|CommandBehaviors admitidos son:<br /><br /> -Valor predeterminado<br />-SingleResult<br />-SingleRow<br />-SchemaOnly|  
|**ExecuteScalar()**|Se asigna a:<br /><br /> -CommandBehaviour.SingleRow con las instrucciones SELECT.<br />-CommandBehaviour.SingleResult de instrucciones EXEC.|  
|**Prepare()**|-EXEC admite enlaza parámetros.<br />-Seleccione admite enlaza parámetros.|  
  
## <a name="supported-constructors"></a>Constructores  
  
|Nombre|Description|  
|----------|-----------------|  
|**SAPCommand()**|Crear una nueva instancia de SAPCommand.|  
|**SAPCommand(string)**|SAPCommand con texto de comando.|  
|**SAPCommand (string, SAPConnection)**|SAPCommand con texto de comando y el objeto de SAPConnection mediante que se ejecutará el comando|  
  
## <a name="see-also"></a>Vea también  
 [Extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)