---
title: Operaciones en funciones y procedimientos con registros Types1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006437"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>Operaciones en funciones y procedimientos con tipos RECORD
Tipos de registros de Oracle se usan para representar información jerárquica de los parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. 

## <a name="supported-record-types"></a>Tipos admitidos de registro
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite los siguientes tipos de los tipos de registros:  
  
- Tipos de registros que se declaran como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.  
  
- Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL. Por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));  
  
- Tipos de registros que contienen registros anidados.  
  
- Tipos de registros que aparecen como IN, OUT o IN OUT parámetros a procedimientos o funciones.  
  
- Tipos de registros que son los valores devueltos de funciones.  
  
  > [!NOTE]
  >  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos BFILE como miembros de registro.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)