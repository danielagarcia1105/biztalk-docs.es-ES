---
title: Operaciones en sinónimos en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 608e8c36-ac78-4d7d-aca4-be552505fc2b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e782f5257658f9145bda3cabc67a306acf22f94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986069"
---
# <a name="operations-on-synonyms-in-oracle-database"></a>Operaciones en sinónimos en la base de datos de Oracle
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite realizar operaciones en sinónimos. Un sinónimo es un alias o nombre descriptivo para los objetos de base de datos (como tablas, vistas, procedimientos almacenados, funciones y paquetes). Para obtener más información acerca de los sinónimos en Oracle, vea [ http://go.microsoft.com/fwlink/?LinkId=138058 ](http://go.microsoft.com/fwlink/?LinkId=138058).  
  
## <a name="advantages-of-using-synonyms"></a>Ventajas del uso de sinónimos  
 Sinónimos son útiles en los escenarios siguientes:  
  
-   **Trabajar con esquemas diferentes**: Si trabaja con esquemas diferentes y la necesidad de tener acceso a los objetos entre esquemas, tendrá que usar instrucciones SQL diferentes para tener acceso a esos objetos. Puede crear un sinónimo para un objeto en un esquema y usar el sinónimo en la instrucción SQL para tener acceso al objeto. Si necesita tener acceso al objeto subyacente en un esquema diferente, modifique la definición del sinónimo para que apunte al objeto en un esquema diferente. Por lo tanto, las aplicaciones basadas en el sinónimo seguirán funcionando sin modificaciones en la instrucción SQL.  
  
     Por ejemplo, suponga que tiene dos esquemas idénticos para los entornos de prueba y producción: "Test" y "Prod". Para obtener acceso a una tabla denominada "Employee" en el esquema de "Prueba", debe usar `Test.Employee` o `Employee` (si es "Test" es el esquema predeterminado) en la instrucción SQL. Si desea usar la tabla "Empleados" en el esquema de producción, debe usar ahora `Prod.Employee` o `Employee` (cambiar el esquema predeterminado a "Prod") en la instrucción SQL. Para solucionar este problema, puede crear un sinónimo de la tabla "Test.Employee" (por ejemplo, "EMP") y, a continuación, utilizarlo en las instrucciones SQL. Siempre que necesite realizar la operación en la tabla "Prod.Employee", modifique la definición del sinónimo "EMP" para que apunte a la tabla "Prod.Employee". Esto garantiza que no es necesario modificar las instrucciones SQL para realizar la operación en el objeto en esquemas diferentes.  
  
-   **Los cambios en los objetos subyacentes**: aislará los sinónimos de los cambios en el nombre o la ubicación de los objetos subyacentes en el que está realizando una operación. Puede modificar la definición de sinónimo para dar cabida a los cambios en el nombre o la ubicación de los objetos subyacentes.  
  
     Por ejemplo, suponga que va a utilizar una tabla en uno de los procedimientos almacenados. Ahora, si los cambios de nombre de tabla o la tabla se mueve a otra ubicación, a continuación, el procedimiento almacenado dejará de funcionar. Para solucionar este problema, puede usar un sinónimo para la tabla en el procedimiento almacenado y actualizar la definición del sinónimo si se produce un cambio en el nombre o la ubicación de la tabla.  
  
-   **Un acceso simplificado y seguro**: en un entorno distribuido, debe usar el nombre del esquema junto con los nombres de objeto para asegurarse de que tiene acceso el objeto correcto. Además, también debe asegurarse de que el usuario tiene necesarios privilegios en el objeto de destino. Para simplificar este proceso, puede asignar un nombre sencillo para un objeto mediante la creación de un sinónimo que tiene la ruta de acceso completa al objeto y, a continuación, conceda los privilegios adecuados en el sinónimo.  
  
## <a name="working-with-synonyms-in-the-adapter"></a>Trabajar con sinónimos en el adaptador  
 La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone los sinónimos de Oracle para:  
  
- Tablas  
  
- Vistas  
  
- Procedimientos almacenados  
  
- Funciones  
  
- .  
  
  Los sinónimos para cada uno de estos artefactos se exponen junto con el artefacto respectivo subyacente en el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Por ejemplo, el **tabla** nodo bajo un esquema mostrará todos los sinónimos para las tablas junto con las tablas de base de datos en un esquema, el **vista** nodo bajo un esquema mostrará todos los sinónimos de vistas a lo largo de con las vistas de base de datos en un esquema y así sucesivamente.  
  
- Para los sinónimos creados en las tablas y vistas, se exponen las mismas operaciones en cuanto a las tablas y vistas de base, respectivamente. Por ejemplo, si las tablas y vistas base contienen columnas LOB, también los sinónimos de esas tablas y vistas de exponer las operaciones de ReadLOB y UpdateLOB.  
  
- Para los sinónimos creados en los procedimientos almacenados, funciones y paquetes, los sinónimos se exponen como operaciones junto con los respectivos procedimientos almacenados subyacentes, funciones y paquetes en un esquema.  
  
> [!NOTE]
>  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sólo locales sinónimos. Esto implica que solo los sinónimos son compatibles con el adaptador que tienen como destino los artefactos en el servidor local.  
  
 Además, las acciones de mensaje para los sinónimos son el mismo que el objeto subyacente, excepto el nombre del artefacto en el que se realiza la acción. Por ejemplo, la acción de mensaje para el **seleccione** operación en una tabla en el esquema SCOTT es: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[TABLE_NAME]/Select`. Si va a realizar una operación de selección para un sinónimo para la misma tabla en el esquema SCOTT, será la acción del mensaje: `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[SYNONYM_NAME]/Select`.  
  
 Cuando se invoca una operación en un sinónimo en el adaptador, el adaptador llama el sinónimo en la base de datos de Oracle para ejecutar la operación. Sin embargo, el adaptador utiliza el nombre del objeto subyacente en la definición del sinónimo para capturar los metadatos.  
  
 Sinónimos pueden usarse en las operaciones normales de salida, operaciones compuestas y sondeo.  
  
> [!NOTE]
>  Puede buscar sinónimos en [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] al igual que otros objetos. Sin embargo, no puede buscar para ver los procedimientos dentro de los paquetes de sinónimo de un nodo de nivel jerárquico superior como haría para los procedimientos dentro de paquetes. Para obtener información acerca de cómo buscar las operaciones en el adaptador, vea [examinar, buscar y obtener metadatos para operaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)