---
title: Soporte técnico para Oracle definido por el usuario Types2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d4b9980-fa5b-4340-a62f-e4a4f98603dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9bd33864523f40255cbf0dcf993fd916f02270
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973269"
---
# <a name="support-for-oracle-user-defined-types"></a>Compatibilidad con tipos definidos por el usuario de Oracle
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite la realización de operaciones en los artefactos en Oracle E-Business Suite y la base de datos subyacente que contienen tipos Oracle User-Defined (UDT). Los UDT pueden estar presentes en los siguientes artefactos:  
  
-   Tablas y vistas de interfaz que contiene las columnas UDT.  
  
-   Las tablas de base de datos y vistas que contienen las columnas UDT.  
  
-   Paquetes, procedimientos almacenados y funciones que contiene los parámetros UDT.  
  
## <a name="what-is-an-oracle-udt"></a>¿Qué es un UDT de Oracle?  
 Ayudar los UDT de Oracle que representan entidades complejas como un objeto de "único" que se puede compartir entre las aplicaciones. Por ejemplo, es posible que las entidades reales del modelo, como "Customers" o "Sales Orders" como objetos en la base de datos de Oracle. Los UDT de Oracle se definen en la base de datos de Oracle, y son de los dos tipos siguientes:  
  
- Tipos de objeto. Por ejemplo, el objeto de Oracle.  
  
- Tipos de colección. Por ejemplo, los tipos de tabla anidada o VARRAY.  
  
  El nombre del UDT Oracle distingue mayúsculas de minúsculas y debe especificarse en la siguiente manera: [nombre_esquema]. [UDT_NAME].  
  
## <a name="how-does-the-adapter-support-oracle-udt"></a>¿Cómo admite el adaptador de Oracle UDT?  
 ODP.NET admite UDT representando los UDT de Oracle definido en la base de datos de Oracle como tipos de .NET (tipos personalizados). Tipos personalizados definen la asignación entre los atributos del UDT de Oracle o elementos a los miembros. NET. Tipos personalizados pueden ser clases .NET o estructuras y pueden representar los objetos de Oracle o colecciones de Oracle.  Debido a la que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para conectarse a la base de datos de Oracle, hereda la compatibilidad con UDT de Oracle.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza el ODP.NET para especificar una asignación de tipo personalizado para asignar un tipo personalizado de .NET en un UDT de Oracle en la base de datos. Para especificar una asignación de tipo personalizado, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza un generador de tipo personalizado. Por lo tanto, para poder usar un UDT de Oracle, se requiere un ensamblado (archivo .dll) que define el generador de tipo personalizado. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] le permite generar un ensamblado para el generador de tipo personalizado al generar los metadatos de un artefacto o de la operación que contiene un UDT de Oracle.  
  
> [!NOTE]
>  El adaptador genera el ensamblado para los UDT de Oracle en función de las clases utilizadas por la ODP.NET para admitir los UDT de Oracle. Para obtener información detallada acerca de cómo se admiten UDT de Oracle en ODP.NET, consulte [ http://go.microsoft.com/fwlink/?LinkId=140697 ](http://go.microsoft.com/fwlink/?LinkId=140697).  
  
 Para generar el archivo de ensamblado para el uso de los UDT de Oracle en tiempo de diseño y, a continuación, usarla más adelante en el tiempo de ejecución, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone las propiedades de enlace siguiente:  
  
- **GeneratedUserTypesAssemblyFilePath** (tiempo de diseño)  
  
- **GeneratedUserTypesAssemblyKeyFilePath** (tiempo de diseño)  
  
- **UserAssembliesLoadPath** (tiempo de ejecución)  
  
  Para obtener información acerca de estas propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
## <a name="performing-operations-on-artifacts-containing-oracle-udts"></a>Realizar operaciones en los artefactos que contiene los UDT de Oracle  
 Para realizar operaciones en los artefactos que contiene los UDT mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe hacer lo siguiente durante el tiempo de diseño y tiempo de ejecución.  
  
### <a name="design-time"></a>Tiempo de diseño  
 Debe realizar estos pasos al esquema de generación para la operación en Visual Studio.  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener información acerca de cómo hacerlo, consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
2. Durante la conexión, en el **propiedades de enlace** pestaña de la **configurar el adaptador de** diálogo cuadro, especifique los valores adecuados para el **GeneratedUserTypesAssemblyFilePath** y **GeneratedUserTypesAssemblyKeyFilePath** propiedades de enlace. Para obtener información acerca de estas propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
3. Cuando esté conectado a Oracle E-Business Suite en Visual Studio, busque el artefacto necesario que contiene un UDT de Oracle. Para obtener información acerca de la exploración de los artefactos, vea [examinar, buscar y recuperar metadatos para operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
4. Seleccione el artefacto necesario y, a continuación, haga clic en **Aceptar**. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] genera los metadatos para la operación seleccionada junto con el ensamblado (archivo .dll) para que el UDT de Oracle en el artefacto seleccionado. Se crea el ensamblado en la ubicación que especificó en el **GeneratedUserTypesAssemblyFilePath** enlaza la propiedad.  
  
5. Continúe con el resto de los pasos para crear e implementar el proyecto.  
  
### <a name="run-time"></a>Tiempo de ejecución  
 Debe realizar estos pasos en los clientes del adaptador para realizar operaciones en los UDT de Oracle.  
  
 **En BizTalk Server**  
  
- Agregar manualmente el ensamblado UDT de Oracle creado en el paso 4 en "Tiempo de diseño" a la caché de ensamblados Global (GAC) en el equipo. Como alternativa, puede copiar manualmente el ensamblado UDT de Oracle en la ubicación de instalación de BizTalk Server. Para que BizTalk Server, esto suele \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.  
  
- Al configurar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] WCF-Custom o WCF-OracleEBS de puerto, en la **enlace** ficha, especifique la ubicación del ensamblado UDT de Oracle para el **UserAssembliesLoadPath** enlaza la propiedad. Para obtener información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
  **En Visual Studio**  
  
- Agregar manualmente el ensamblado UDT de Oracle creado en el paso 4 en "Tiempo de diseño" a la caché de ensamblados Global (GAC) en el equipo. Como alternativa, puede copiar manualmente el ensamblado UDT de Oracle en la misma ubicación que el archivo ejecutable del proyecto, que normalmente se encuentra en la carpeta \bin\Debug del proyecto.  
  
- Especifique la ubicación del ensamblado UDT de Oracle para el **UserAssembliesLoadPath** enlaza la propiedad. Para obtener información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)