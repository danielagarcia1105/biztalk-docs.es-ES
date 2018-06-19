---
title: Operaciones en funciones y procedimientos con registros Types1 | Documentos de Microsoft
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
ms.openlocfilehash: 43974d1c392a357b9781ff7f6fae5286e282513a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216084"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a>Operaciones en funciones y procedimientos con tipos de registro
Tipos de registros de Oracle se usan para representar la información jerárquica de parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. 

## <a name="supported-record-types"></a>Tipos admitidos de registro
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con los siguientes tipos de tipos de registros:  
  
-   Tipos de registro que se declaran como tabla % ROWTYPE parámetros en procedimientos almacenados y funciones.  
  
-   Tipos de registro que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL. Por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));  
  
-   Tipos de registros que contienen registros anidados.  
  
-   Tipos de registro que aparecen como IN, OUT o IN los parámetros OUT procedimientos o funciones.  
  
-   Tipos de registros que son los valores devueltos de funciones.  
  
    > [!NOTE]
    >  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos BFILE como miembros de registro.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)