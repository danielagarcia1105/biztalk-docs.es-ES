---
title: "Busque las operaciones de Oracle E-Business Suite en la vista basada en la aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d4d4d67df9d7463a699b1ec9448feeea0a9c57a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>Busque las operaciones de Oracle E-Business Suite en la vista basada en la aplicación
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que pueden realizarse en Oracle E-Business Suite con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Este tema proporciona información acerca de cómo buscar operaciones entrantes y salientes en la vista basada en la aplicación.  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes básicamente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los temas de la mismos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite antes de que se pueden examinar los metadatos para las operaciones de destino. Para obtener información acerca de cómo conectar con Oracle con la base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="browsing-for-outbound-operations"></a>Exploración de las operaciones de salida  
 Realice los pasos siguientes para examinar las operaciones de salida en la vista basada en la aplicación.  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>Para examinar los metadatos para las operaciones de salida en la vista basada en la aplicación  
  
1.  Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** seleccione **Client (Outbound operations)**.  
  
3.  El **seleccione una categoría de** cuadro enumera las distintas vistas en las que se clasifican los artefactos de Oracle E-Business Suite.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/) y los nodos de categoría general disponibles bajo el nodo raíz se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Operaciones y categorías en el nivel raíz](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  Las operaciones estándar como ExecuteReader, ExecuteScalar y ExecuteNonQuery están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md). Para obtener instrucciones sobre cómo ejecutar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar u operaciones de ExecuteNonQuery en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
4.  Expanda el **vista basada en la aplicación** nodo para ver todas las aplicaciones de conjunto de Oracle E-Business disponibles en el servidor conectado a. Expanda una aplicación para ver las categorías de tablas de interfaz, vistas de interfaz, programas simultáneos y conjuntos de solicitud disponible para esa aplicación.  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **alerta** nodo, mantener el foco en el **vista basada en la aplicación** nodo y, a continuación, escriba `Alert`.  
  
5.  Expanda el **tablas de interfaz** nodo para ver las tablas de interfaz para la aplicación de Oracle. Haga clic en una tabla de la interfaz para ver la lista de operaciones disponibles para la tabla en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar tablas de interfaz en Oracle E &#45; Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
    > [!NOTE]
    >  Si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. El nombre de tales operaciones son Read_\<LOBColName\>. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Read_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB y BFILE el adaptador expondrá tantos número de Read_\<LOBColName\> operaciones.  
    >   
    >  De forma similar, si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB y NCLOB el adaptador también expone una operación específica para actualizar datos en esas columnas. El nombre de tales operaciones son Update_\<LOBColName\>. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Update_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB y NCLOB el adaptador expondrá tantos número de Update_\<LOBColName\> operaciones. Tenga en cuenta que la operación de actualización no se admite en las columnas de tipo BFILE.  
  
6.  Expanda el **vistas de interfaz** nodo para ver las vistas de interfaz para la aplicación de Oracle. Haga clic en una vista de la interfaz para ver la lista de operaciones disponibles para la vista en la **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar vistas de interfaz en Oracle E &#45; Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
    > [!NOTE]
    >  Si una vista de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer los datos de esas columnas. El nombre de tales operaciones son Read_\<LOBColName\>. Por ejemplo, si la vista de la interfaz tiene una columna, FILE_CONTENT, de tipo BLOB, el adaptador expone un **Read_FILE_CONTENT** operación. Si una vista de la interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB o BFILE el adaptador expondrá tantos número de Read_\<LOBColName\> operaciones. Tenga en cuenta que Update_\<LOBColName\> operaciones no se admiten en las vistas.  
  
7.  Haga clic en el **programas simultáneos** nodo para ver los programas simultáneos para una aplicación en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar programas simultáneos de la aplicación Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
     Esta ilustración muestra los programas simultáneos específicos a una aplicación de Oracle y los programas simultáneos estándares para todas las aplicaciones de Oracle.  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de programas simultáneos. Sin embargo, los metadatos para el programa simultáneo tiene el nombre real del programa simultáneo. Por ejemplo, la aplicación de cuentas por cobrar contiene un programa simultáneo de "Interfaz de cliente". Sin embargo, los metadatos tiene el nombre del programa simultáneas como RACUST, que es el nombre real del programa simultáneo.  
  
8.  Haga clic en el **solicitud establece** conjuntos de nodos para ver la solicitud de una aplicación en el **categorías y operaciones disponibles** cuadro.  
  
     ![Examinar conjuntos de solicitudes para una aplicación de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
    > [!IMPORTANT]
    >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de conjuntos de solicitudes. Sin embargo, los metadatos para el conjunto de solicitud tiene el nombre real del conjunto de solicitud. Por ejemplo, la aplicación de DBA de aplicaciones contiene un conjunto de solicitud de "DownloadPatches". Sin embargo, los metadatos tiene el nombre del conjunto de solicitud como FNDRSSUB1623, que es el nombre real del conjunto de solicitud.  
  
## <a name="browsing-for-inbound-operations"></a>Buscar operaciones entrantes  
 Realice los pasos siguientes para examinar las operaciones de entrada en la vista basada en la aplicación.  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>Para examinar los metadatos para operaciones de entrada en la vista basada en la aplicación  
  
1.  Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** lista, para las operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3.  El **seleccione una categoría de** cuadro enumera las distintas vistas en las que se clasifican los artefactos de Oracle E-Business Suite.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/) y los nodos de categoría general disponibles bajo el nodo raíz se enumeran en la **categorías y operaciones disponibles** cuadro.  
  
     ![Operación en el nivel raíz de entrada](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     La operación de entrada, **notificación**, también está disponible en el nivel raíz.  
  
4.  Expanda el **vista basada en la aplicación** nodo para ver todas las aplicaciones de conjunto de Oracle E-Business disponibles en el servidor conectado a. Expanda una aplicación para ver las categorías de tablas de interfaz y vistas de interfaz.  
  
    > [!TIP]
    >  Puede ir directamente a la categoría "inmediata" nodos de subcategoría en el árbol, puede escribir el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccione una categoría de** cuadro. Por ejemplo, para saltar a la **alerta** nodo, mantener el foco en el **vista basada en la aplicación** nodo y, a continuación, escriba `Alert`.  
  
5.  Expanda una aplicación de Oracle para ver las categorías de tablas de interfaz y vistas de interfaz disponibles para esa aplicación. Expanda el **tablas de interfaz** y **vistas de interfaz** nodos para ver las tablas de interfaz y las vistas de interfaz para la aplicación de Oracle. Haga clic en una vista de tabla o la interfaz de interfaz para disfrutar de la operación de entrada disponible para la tabla o vista en la **categorías y operaciones disponibles** cuadro.  
  
     En la ilustración siguiente, se selecciona una vista de la interfaz en el **seleccione una categoría de** cuadro y la operación de entrada compatible con la vista se muestra en el **categorías y operaciones disponibles** cuadro.  
  
     ![Operaciones en las vistas de interfaz entrantes](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
    > [!NOTE]
    >  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no expuesta programas simultáneos y solicitar conjuntos de operaciones de entrada.  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener los metadatos de las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)