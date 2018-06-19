---
title: Acceso a datos en el motor de reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, data access
- Business Rules Engine, helper classes
- data, data access
ms.assetid: 38da32af-1e0d-43fb-b946-fb49a11f1681
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58de70c2befd13f4995ebd073ebd70a2e7d84ea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238620"
---
# <a name="data-access-in-the-business-rule-engine"></a>Acceso a datos en el motor de reglas de negocios
El motor de reglas admite solo objetos .NET de forma nativa. Para controlar datos de una base de datos, puede utilizar directamente los objetos ADO.NET pero el motor proporciona algunas clases auxiliares para simplificar el uso de datos de bases de datos de reglas. El motor de reglas amplía su compatibilidad exponiendo tres tipos relacionados con la base de datos: **TypedDataRow**, **TypedDataTable**, y **DataConnection**. En esta sección se describen estas clases auxiliares, se proporcionan recomendaciones sobre cuándo utilizar cada tipo y se analizan algunas implicaciones de rendimiento a la hora de utilizarlas.  
  
 Las clases auxiliares son las siguientes:  
  
-   **TypedDataRow.** Construido mediante una referencia a un ADO.NET **DataRow** instancia. El **TypedDataRow** es una opción clara para reglas que solo tratan con datos de uno o un número pequeño de filas de una tabla determinada.  
  
-   **TypedDataTable.** Literalmente una colección de **TypedDataRow** objetos. Cada fila de la tabla de base de datos se ajustará como un **TypedDataRow** y se imponen en la memoria de trabajo por el motor de reglas.  
  
     A **TypedDataTable** requiere un ADO.NET en memoria **DataTable**, lo que puede ser un determinado de sobrecarga si este rendimiento **DataTable** contiene un gran número de filas. Si un número reducido de filas de la tabla de base de datos es relevante y puede determinar estas filas antes de llamar a las reglas, use un **DataTable**, de lo contrario utilice **TypedDataRow**. La suposición es que un gran número de filas de la tabla de datos está relacionado con las reglas.  
  
-   **DataConnection.** Representa una tabla de una base de datos a la que se ha obtenido acceso mediante una conexión de base de datos. La diferencia entre **DataConnection** y **TypedDataTable** es que además del nombre de conjunto de datos y el nombre de la tabla, **DataConnection** requiere una base de datos puede usar conexión y, opcionalmente, un contexto de transacción de base de datos.  
  
     Algunos o todos los predicados que se utilizan en las reglas con el **DataConnection** pasaría a formar parte de las restricciones de consulta en la conexión de base de datos. solo las filas que cumplen las restricciones de consulta se recuperarán de la base de datos y serán utilizadas por el motor. Este mecanismo proporciona mejor rendimiento y consume menos memoria que mantiene un gran **DataTable** en la memoria.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Consideraciones al utilizar DataConnection](../core/considerations-when-using-dataconnection.md)  
  
-   [Utilizar DataConnection y TypedDataTable](../core/using-dataconnection-and-typeddatatable.md)