---
title: Compatibilidad con ExecuteNonQuery y ExecuteReader, ExecuteScalar operaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bad547627669bb22a6b32f05d96c6c7b2f68c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a>Compatibilidad con ExecuteNonQuery y ExecuteReader, ExecuteScalar operaciones
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone las siguientes operaciones de salida en el nivel raíz:  
  
-   **ExecuteNonQuery**: Use esta operación para ejecutar las instrucciones SQL arbitrarias o bloques de PL/SQL de Oracle E-Business Suite si desea devolver varios conjuntos de resultados. Los parámetros de entrada de esta función incluyen un parámetro de cadena (el bloque de PL/SQL completo que se ejecute) y una matriz de cadenas (OutRefCursorNames). Cada valor de cadena especificado en OutRefCursorNames se supone que el nombre del parámetro de una salida de REF CURSOR con el bloque de PL/SQL que devuelve los cursores REF cursor con los mismos nombres. Esta función también toma un parámetro OUT (OutRefCursors), que es una matriz de conjuntos de datos. Para obtener información sobre el conjunto de datos, consulte la documentación de Oracle en [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538). El valor devuelto de esta operación es del tipo de datos entero e indica el número de filas afectadas.  
  
-   **ExecuteReader**: Use esta operación para ejecutar las instrucciones SQL arbitrarias o bloques de PL/SQL de Oracle E-Business Suite si desea que el conjunto de resultados para devolver como conjunto de datos. Esta operación toma un parámetro de cadena como entrada y devuelve un conjunto de datos.  
  
-   **ExecuteScalar**: Use esta operación para ejecutar las instrucciones SQL arbitrarias o bloques de PL/SQL de Oracle E-Business Suite si desea que solo un valor que se devuelve. Si el valor devuelto es un conjunto de resultados, solo el valor de la primera columna de la primera fila se devuelve en un formato de cadena XML.  
  
> [!NOTE]
>  -   No se admiten las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar para los tipos de definidos por el usuario (UDT).  
> -   También puede establecer el contexto de las aplicaciones para las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Es obligatorio para establecer el contexto de las aplicaciones para las operaciones ExecuteNonQuery y ExecuteReader, ExecuteScalar si cualquiera de la operación tiene como destino de un artefacto en Oracle E-Business Suite (tabla de interfaz, vista de la interfaz, programas simultáneos o solicitud establece). Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)