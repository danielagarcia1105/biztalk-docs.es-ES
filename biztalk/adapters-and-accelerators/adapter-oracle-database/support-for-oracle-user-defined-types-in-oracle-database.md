---
title: Compatibilidad con tipos definidos por el usuario de Oracle en base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68edf0f2-a798-4096-86ca-85d2cfa9088a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de61b0659e06ebbf7b95f0b4adcad210c5c986e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="support-for-oracle-user-defined-types-in-oracle-database"></a>Compatibilidad con tipos definidos por el usuario de Oracle en base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite la realización de operaciones en artefactos en la base de datos de Oracle que contienen tipos de Oracle User-Defined (UDT). Los UDT pueden estar presentes en los siguientes artefactos:  
  
-   Las tablas y vistas que contienen columnas UDT.  
  
-   Paquetes, procedimientos almacenados y las funciones que contienen parámetros UDT.  
  
## <a name="what-is-an-oracle-udt"></a>¿Qué es un UDT de Oracle?  
 Ayuda del UDT de Oracle en que representan entidades complejas como un objeto "único" que se pueden compartir entre las aplicaciones. Por ejemplo, es posible que las entidades reales del modelo, como "Clientes" o "Sales Orders" como objetos en la base de datos de Oracle. Los UDT de Oracle se definen en la base de datos de Oracle y son de los dos tipos siguientes:  
  
-   Tipos de objeto. Por ejemplo, el objeto de Oracle.  
  
-   Tipos de colección. Por ejemplo, tipos de tabla anidada o VARRAY.  
  
 El nombre del UDT Oracle distingue mayúsculas de minúsculas y debe especificarse de la manera siguiente: [nombre_esquema]. [UDT_NAME].  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>¿Cómo admite el adaptador de Oracle UDT?  
 ODP.NET admite UDT mediante la representación de UDT de Oracle definido en la base de datos de Oracle como tipos de .NET (tipos personalizados). Tipos personalizados definen la asignación entre los atributos de UDT de Oracle o elementos a los miembros. NET. Tipos personalizados pueden ser clases .NET o estructuras y pueden representar objetos de Oracle o colecciones de Oracle.  Debido a la que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza ODP.NET para conectarse a la base de datos de Oracle, que hereda de compatibilidad con UDT de Oracle.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] el ODP.NET se utiliza para especificar una asignación de tipo personalizado para un tipo personalizado de .NET se asignan a un UDT de Oracle en la base de datos. Para especificar una asignación de tipo personalizado, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa un generador de tipo personalizado. Por lo tanto, para poder usar un UDT de Oracle, se requiere un ensamblado (archivo .dll) que define el generador de tipo personalizado. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] permite generar un ensamblado para el generador de tipo personalizado al generar los metadatos de un artefacto/operación que contiene un UDT de Oracle.  
  
> [!NOTE]
>  El adaptador genera el ensamblado para los UDT de Oracle en función de las clases utilizadas por la ODP.NET para admitir los UDT de Oracle. Para obtener información detallada acerca de cómo se admiten UDT de Oracle en ODP.NET, consulte [http://go.microsoft.com/fwlink/?LinkId=140697](http://go.microsoft.com/fwlink/?LinkId=140697).  
  
 Para generar el archivo de ensamblado para el uso de los UDT de Oracle en tiempo de diseño y, a continuación, utilizarlo más adelante en el tiempo de ejecución, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone las siguientes propiedades de enlace:  
  
-   **GeneratedUserTypesAssemblyFilePath** (tiempo de diseño)  
  
-   **GeneratedUserTypesAssemblyKeyFilePath** (tiempo de diseño)  
  
-   **UserAssembliesLoadPath** (tiempo de ejecución)  
  
 Para obtener información acerca de estas propiedades de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>Realizar operaciones en los artefactos que contiene el UDT de Oracle  
 Para realizar operaciones en los artefactos que contiene el UDT mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe hacer lo siguiente en tiempo de diseño y tiempo de ejecución.  
  
### <a name="design-time"></a>Tiempo de diseño  
 Debe realizar estos pasos al esquema de generación para la operación en Visual Studio.  
  
1.  Conectarse a la base de datos de Oracle mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener información acerca de cómo hacerlo, consulte [conectar con base de datos de Oracle en Visual Studio mediante el servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).  
  
2.  Al conectarse, en el **propiedades de enlace de** pestaña de la **configurar el adaptador** cuadro de diálogo, especifique los valores adecuados para el **GeneratedUserTypesAssemblyFilePath** y **GeneratedUserTypesAssemblyKeyFilePath** propiedades de enlace. Para obtener información acerca de estas propiedades de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
3.  Cuando está conectado a la base de datos de Oracle en Visual Studio, busque el artefacto necesario que contiene un UDT de Oracle. Para obtener información acerca de cómo explorar artefactos, vea [buscar, búsqueda y obtener los metadatos de las operaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md).  
  
4.  Seleccione el artefacto necesario y, a continuación, haga clic en **Aceptar**. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] genera los metadatos para la operación seleccionada junto con el ensamblado (archivo .dll) para que el UDT de Oracle en el artefacto seleccionado. Se crea el ensamblado en la ubicación que especificó en el **GeneratedUserTypesAssemblyFilePath** propiedad de enlace.  
  
5.  Continúe con el resto de los pasos para crear e implementar el proyecto.  
  
### <a name="run-time"></a>Tiempo de ejecución  
 Debe realizar estos pasos en los clientes de adaptador para realizar operaciones en los UDT de Oracle.  
  
 **En BizTalk Server**  
  
-   Agregar manualmente el ensamblado UDT de Oracle creado en el paso 4 "En tiempo de diseño" a la caché de ensamblados Global (GAC) en el equipo. Como alternativa, puede copiar manualmente el ensamblado UDT de Oracle en la ubicación de instalación de BizTalk Server. Para que BizTalk Server, esto suele \<unidad de instalación\>: \Program BizTalk Server.  
  
-   Al configurar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] WCF-Custom o WCF-OracleDB puerto, en la **enlace** ficha, especifique la ubicación del ensamblado UDT de Oracle para el **UserAssembliesLoadPath** propiedad de enlace. Para obtener información acerca de esta propiedad de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
 **En Visual Studio**  
  
-   Agregar manualmente el ensamblado UDT de Oracle creado en el paso 4 "En tiempo de diseño" a la caché de ensamblados Global (GAC) en el equipo. Como alternativa, puede copiar manualmente el ensamblado UDT de Oracle en la misma ubicación que el archivo ejecutable del proyecto, que normalmente se encuentra en la carpeta \bin\Debug del proyecto.  
  
-   Especifique la ubicación del ensamblado UDT de Oracle para el **UserAssembliesLoadPath** propiedad de enlace. Para obtener información acerca de esta propiedad de enlace, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)