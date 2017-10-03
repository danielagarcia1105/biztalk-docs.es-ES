---
title: Busque las operaciones de Oracle E-Business Suite en la vista basada en el artefacto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 962ac1cc-826c-46d6-848a-4cd371804596
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3757514839e29d1d9748ffdcf56e7cc97ea075b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-artifact-based-view"></a>Busque las operaciones de Oracle E-Business Suite en la vista basada en el artefacto
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que pueden realizarse en Oracle E-Business Suite con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Este tema proporciona información acerca de cómo buscar operaciones entrantes y salientes en la vista basada en el artefacto.  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes básicamente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los temas de la mismos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite antes de que se pueden examinar los metadatos para las operaciones de destino. Para obtener información acerca de cómo conectar con Oracle con la base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="browsing-for-outbound-operations"></a>Exploración de las operaciones de salida  
 Realice los pasos siguientes para examinar las operaciones de salida en la vista basada en el artefacto.  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-artifact-based-view"></a>Para examinar los metadatos para las operaciones de salida en la vista basada en el artefacto  
  
1.  Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista para seleccionar las operaciones salientes **Client (Outbound operations)**.  
  
3.  El **seleccione una categoría de** cuadro enumera las distintas vistas en las que se clasifican los artefactos de Oracle E-Business Suite.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/) y los nodos de categoría general disponibles bajo el nodo raíz se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Operaciones y categorías en el nivel raíz](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  Las operaciones estándar como ExecuteReader, ExecuteScalar y ExecuteNonQuery están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md). Para obtener instrucciones sobre cómo ejecutar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
4.  Expanda el **vista basada en el artefacto** nodo para ver la categoría de artefactos, tanto para Oracle E-Business Suite y la base de datos subyacente. Cada categoría se clasifica en función de la aplicación que pertenece (para los artefactos de Oracle-E-Business Suite como tabla de interfaz, vistas de interfaz, programas simultáneos y conjuntos de solicitudes) o el esquema pertenece a (para Oracle base artefactos como Las API PL-SQL, procedimientos, funciones, tablas y vistas).  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **procedimientos** nodo, mantener el foco en el **vista basada en el artefacto** nodo y, a continuación, escriba `Procedures`.  
  
5.  Expanda el **tablas de interfaz** nodo para ver todas las aplicaciones de Oracle E-Business Suite. Expanda una aplicación de Oracle E-Business suite para enumerar todas las tablas de interfaz que pertenecen a esa aplicación. Haga clic en un nombre de tabla de la interfaz para ver las operaciones disponibles para la tabla en la **categorías y operaciones disponibles** cuadro.  
  
    > [!NOTE]
    >  Si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. El nombre de tales operaciones son Read_\<LOBColName >. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Read_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB y BFILE el adaptador expondrá tantos número de Read_\<LOBColName > operaciones.  
    >   
    >  De forma similar, si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB y NCLOB el adaptador también expone una operación específica para actualizar datos en esas columnas. El nombre de tales operaciones son Update_\<LOBColName >. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Update_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB y NCLOB el adaptador expondrá tantos número de Update_\<LOBColName > operaciones. Tenga en cuenta que la operación de actualización no se admite en las columnas de tipo BFILE.  
  
6.  Expanda el **vistas de interfaz** nodo para ver todas las aplicaciones de Oracle E-Business Suite. Expanda una aplicación de Oracle E-Business suite para enumerar todas las vistas de interfaz que pertenecen a esa aplicación. Haga clic en un nombre de vista de la interfaz para ver las operaciones disponibles para la vista en la **categorías y operaciones disponibles** cuadro.  
  
    > [!NOTE]
    >  Si una vista de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. Los nombres de estas operaciones son Read_\<LOBColName >. Por ejemplo, si la vista de la interfaz tiene una columna, FILE_CONTENT, de tipo BLOB, el adaptador expone un **Read_FILE_CONTENT** operación. Si una vista de la interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB o BFILE el adaptador expondrá tantos número de Read_\<LOBColName > operaciones. Tenga en cuenta que Update_\<LOBColName > operaciones no se admiten en las vistas.  
  
7.  Expanda el **programas simultáneos** nodo para ver todas las aplicaciones de Oracle E-Business Suite. Haga clic en una aplicación de Oracle E-Business suite para enumerar todos los programas simultáneos que pertenecen a esa aplicación en el **categorías y operaciones disponibles** cuadro.  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de programas simultáneos. Sin embargo, los metadatos para el programa simultáneo tiene el nombre real del programa simultáneo. Por ejemplo, la aplicación de cuentas por cobrar contiene un programa simultáneo de "Interfaz de cliente". Sin embargo, los metadatos tiene el nombre del programa simultáneas como RACUST, que es el nombre real del programa simultáneo.  
  
8.  Expanda el **solicitar conjuntos** nodo para ver todas las aplicaciones de Oracle E-Business Suite. Haga clic en una aplicación de Oracle E-Business suite para enumerar todos los conjuntos de solicitud que pertenecen a esa aplicación en el **categorías y operaciones disponibles** cuadro.  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de conjuntos de solicitudes. Sin embargo, los metadatos para el conjunto de solicitud tiene el nombre real del conjunto de solicitud. Por ejemplo, la aplicación de DBA de aplicaciones contiene un conjunto de solicitud de "DownloadPatches". Sin embargo, los metadatos tiene el nombre del conjunto de solicitud como FNDRSSUB1623, que es el nombre real del conjunto de solicitud.  
  
9. Expanda el **API PL-SQL** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todos los paquetes definidos para ese esquema. Haga clic en un nombre de paquete para ver las funciones y los procedimientos dentro del paquete en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar paquetes en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/7a9dc061-db0b-4a8e-bfc6-3a003ad687d8.gif "7a9dc061-db0b-4a8e-bfc6-3a003ad687d8")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de paquetes que se ha definido para ese esquema. Haga clic en un nombre de paquete para ver las funciones y los procedimientos dentro del paquete en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar paquetes en la base de datos de Oracle para todos los esquemas](../../adapters-and-accelerators/adapter-oracle-ebs/media/09a4841b-b88f-490d-a49a-94e392b5493c.gif "09a4841b-b88f-490d-a49a-94e392b5493c")  
  
10. Expanda el **procedimientos** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Haga clic en el **esquema actual (\<nombre de esquema >)** nodo para ver todos los procedimientos definidos para ese esquema en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar procedimientos en la base de datos de Oracle para un esquema](../../adapters-and-accelerators/adapter-oracle-ebs/media/6d78563a-53f7-45cc-8652-f40d4703bdf4.gif "6d78563a-53f7-45cc-8652-f40d4703bdf4")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Haga clic en un nodo de esquema para ver una lista de procedimientos definidos para ese esquema en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar procedimientos en la base de datos de Oracle para esquemas](../../adapters-and-accelerators/adapter-oracle-ebs/media/a514d199-d6c1-44a0-bf6b-28ddf702081a.gif "a514d199-d6c1-44a0-bf6b-28ddf702081a")  
  
11. Expanda el **funciones** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Haga clic en el **esquema actual (\<nombre de esquema >)** nodo para ver todas las funciones definidas para ese esquema en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar funciones en la base de datos de Oracle para un esquema](../../adapters-and-accelerators/adapter-oracle-ebs/media/22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd.gif "22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Haga clic en un nodo de esquema para ver una lista de las funciones definidas para ese esquema en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar funciones en la base de datos de Oracle para todos los esquemas](../../adapters-and-accelerators/adapter-oracle-ebs/media/b4d29036-3d37-4a50-82c2-3532adbe2875.gif "b4d29036-3d37-4a50-82c2-3532adbe2875")  
  
12. Expanda el **tablas** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todas las tablas definidas para ese esquema. Haga clic en un nombre de tabla para ver las operaciones admitidas en la tabla en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas en la base de datos de Oracle para un esquema](../../adapters-and-accelerators/adapter-oracle-ebs/media/6ba7420f-9893-4b3e-91cb-10f29d725ad3.gif "6ba7420f-9893-4b3e-91cb-10f29d725ad3")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de tablas definidas para ese esquema. Haga clic en un nombre de tabla para ver las operaciones admitidas en la tabla en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas de base de datos de Oracle para todos los esquemas](../../adapters-and-accelerators/adapter-oracle-ebs/media/d7c52ab4-ba27-404a-9db6-32b2a635ad2f.gif "d7c52ab4-ba27-404a-9db6-32b2a635ad2f")  
  
    > [!NOTE]
    >  Si una tabla contiene columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. El nombre de tales operaciones son Read_\<LOBColName >. Por ejemplo, si la tabla tiene una columna, fotos, de tipo BLOB, el adaptador expone un **Read_PHOTO** operación. Si una tabla tiene más de una columna de tipo BLOB, CLOB, NCLOB y BFILE el adaptador expondrá tantos número de Read_\<LOBColName > operaciones.  
    >   
    >  De forma similar, si una tabla contiene columnas de tipo BLOB, CLOB y NCLOB el adaptador también expone una operación específica para actualizar datos en esas columnas. El nombre de tales operaciones son Update_\<LOBColName >. Por ejemplo, si la tabla tiene una columna, fotos, de tipo BLOB, el adaptador expone un **Update_PHOTO** operación. Si una tabla tiene más de una columna de tipo BLOB, CLOB y NCLOB el adaptador expondrá tantos número de Update_\<LOBColName > operaciones. Tenga en cuenta que la operación de actualización no se admite en las columnas de tipo BFILE.  
  
13. Expanda el **vistas** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todas las vistas definidas para ese. Haga clic en el nombre de una vista para ver las operaciones admitidas en esa vista en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle para el esquema actual](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a38cfed-007d-431a-af60-c9c8be5369ab.gif "2a38cfed-007d-431a-af60-c9c8be5369ab")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de vistas definidas para ese esquema. Haga clic en el nombre de una vista para ver las operaciones admitidas en esa vista en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle para todos los esquemas](../../adapters-and-accelerators/adapter-oracle-ebs/media/67ca336c-62ac-4374-87da-07cf331ea4ad.gif "67ca336c-62ac-4374-87da-07cf331ea4ad")  
  
    > [!NOTE]
    >  Si una vista contiene columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. El nombre de tales operaciones son Read_\<LOBColName >. Por ejemplo, si la vista tiene una columna, la regla de tipo BLOB, el adaptador expone un **Read_RULE** operación. Si una vista tiene más de una columna de tipo BLOB, CLOB, NCLOB o BFILE el adaptador expondrá tantos número de Read_\<LOBColName > operaciones. Tenga en cuenta que Update_\<LOBColName > operaciones no se admiten en las vistas.  
  
## <a name="browsing-for-inbound-operations"></a>Buscar operaciones entrantes  
 Realice los pasos siguientes para examinar las operaciones de entrada en la vista basada en el artefacto.  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-artifact-based-view"></a>Para examinar los metadatos para operaciones de entrada en la vista basada en el artefacto  
  
1.  Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista, para las operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3.  El **seleccione una categoría de** cuadro enumera las distintas vistas en las que se clasifican los artefactos de Oracle E-Business Suite.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/) y los nodos de categoría general disponibles bajo el nodo raíz se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Operación en el nivel raíz de entrada](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     La operación de entrada, **notificación**, también está disponible en el nivel raíz.  
  
4.  Expanda el **vista basada en el artefacto** nodo para ver la categoría de artefactos, tanto para Oracle E-Business Suite y la base de datos subyacente. Cada categoría se clasifica según el esquema al que pertenece (para los artefactos de la base de datos de Oracle como API PL-SQL, procedimientos, funciones, o la aplicación que pertenece (para los artefactos de Oracle-E-Business Suite como tabla de interfaz y las vistas de interfaz) las tablas y vistas).  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **procedimientos** nodo, mantener el foco en el **vista basada en el artefacto** nodo y, a continuación, escriba `Procedures`.  
  
    > [!NOTE]
    >  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no expuesta programas simultáneos y solicitar conjuntos de operaciones de entrada.  
  
5.  Expanda una aplicación de Oracle para ver las categorías de tablas de interfaz y vistas de interfaz disponibles para esa aplicación. Expanda el **tablas de interfaz** y **vistas de interfaz** nodos para ver las tablas de interfaz y las vistas de interfaz para la aplicación de Oracle. Haga clic en una vista de tabla o la interfaz de interfaz para disfrutar de la operación de entrada disponible para la tabla o vista en la **categorías y operaciones disponibles** cuadro.  
  
     En la ilustración siguiente, se selecciona una vista de la interfaz en el **seleccione una categoría de** cuadro y la operación de entrada compatible con la vista se muestra en el **categorías y operaciones disponibles** cuadro.  
  
     ![Operaciones en las vistas de interfaz entrantes](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
6.  Expanda el **API PL-SQL** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todos los paquetes definidos para ese esquema. Haga clic en un nombre de paquete para ver las funciones y los procedimientos dentro del paquete en el **categorías y operaciones disponibles** cuadro. Cada una de las funciones enumeradas y los procedimientos se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar PL &#45; Base de datos de las API de SQL de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a.gif "4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de paquetes que se ha definido para ese esquema. Haga clic en un nombre de paquete para ver las funciones y los procedimientos dentro del paquete en el **categorías y operaciones disponibles** cuadro. Cada una de las funciones enumeradas y los procedimientos se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar PL &#45; Las API de SQL para todos los esquemas del sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/e28a803e-fcfb-4021-9225-924d54a484c0.gif "e28a803e-fcfb-4021-9225-924d54a484c0")  
  
7.  Expanda el **procedimientos** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Haga clic en el **esquema actual (\<nombre de esquema >)** nodo para ver todos los procedimientos definidos para ese esquema en el **categorías y operaciones disponibles** cuadro. Cada uno de los procedimientos enumerados se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar procedimientos para todos los esquemas del sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/5e78da80-d99a-44d3-8eac-f636828f8ceb.gif "5e78da80-d99a-44d3-8eac-f636828f8ceb")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Haga clic en un nodo de esquema para ver una lista de procedimientos definidos para ese esquema en el **categorías y operaciones disponibles** cuadro. Cada uno de los procedimientos enumerados se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar procedimientos en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/22d8e866-ed19-49f4-a6eb-683343b16cf5.gif "22d8e866-ed19-49f4-a6eb-683343b16cf5")  
  
8.  Expanda el **funciones** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Haga clic en el **esquema actual (\<nombre de esquema >)** nodo para ver todas las funciones definidas para ese esquema en el **categorías y operaciones disponibles** cuadro. Cada una de las funciones enumeradas se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar funciones en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf.gif "64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Haga clic en un nodo de esquema para ver una lista de las funciones definidas para ese esquema en el **categorías y operaciones disponibles** cuadro.  Cada una de las funciones enumeradas se puede utilizar para sondear la base de datos de Oracle.  
  
     ![Examinar funciones en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/1d22c3c8-8c24-4905-8144-bdb4840244f1.gif "1d22c3c8-8c24-4905-8144-bdb4840244f1")  
  
9. Expanda el **tablas** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todas las tablas definidas para ese esquema. Haga clic en un nombre de tabla para ver el **sondeo** se admite en la tabla en la operación de entrada la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/7c60dfbf-3836-4e72-abe8-5f32a0936807.gif "7c60dfbf-3836-4e72-abe8-5f32a0936807")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de tablas definidas para ese esquema. Haga clic en un nombre de tabla para ver el **sondeo** se admite en la tabla en la operación de entrada la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/c5fbaf59-2e79-4141-8a85-1e1b8eedcea7.gif "c5fbaf59-2e79-4141-8a85-1e1b8eedcea7")  
  
10. Expanda el **vistas** nodo para ver los nodos de categoría para el esquema de usuario actual (con la que inicie sesión) y todos los demás esquemas definidos en la base de datos de Oracle subyacente. Expanda el **esquema actual (\<nombre de esquema >)** nodo para ver todas las vistas definidas para ese. Haga clic en el nombre de una vista para ver el **sondeo** se admite en esa vista en la operación de entrada la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/2299de79-9f50-433d-9e71-164f6d02bd78.gif "2299de79-9f50-433d-9e71-164f6d02bd78")  
  
     De forma similar, expanda la **todos los esquemas** nodo para ver una lista de todos los esquemas definidos en la base de datos de Oracle. Expanda un nodo de esquema para ver una lista de vistas definidas para ese esquema. Haga clic en el nombre de una vista para ver el **sondeo** se admite en esa vista en la operación de entrada la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/860e6636-1ef6-42ad-a0e2-d661e632b624.gif "860e6636-1ef6-42ad-a0e2-d661e632b624")  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener los metadatos de las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)