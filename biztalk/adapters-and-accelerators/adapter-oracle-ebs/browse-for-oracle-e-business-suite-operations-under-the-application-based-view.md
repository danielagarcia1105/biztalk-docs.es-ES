---
title: Buscar operaciones de Oracle E-Business Suite en la vista basada en aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890fd8a6dc582b644d1f0e73338973820b97ea81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966925"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>Buscar operaciones de Oracle E-Business Suite en la vista basada en aplicaciones
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que se pueden realizar en Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. En este tema se proporciona información sobre cómo buscar operaciones entrantes y salientes en la vista basada en la aplicación.  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes esencialmente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los mismos temas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite para poder examinar los metadatos para las operaciones de destino. Para obtener información sobre cómo conectarse a Oracle base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="browsing-for-outbound-operations"></a>Exploración de las operaciones salientes  
 Realice los pasos siguientes para examinar las operaciones de salida en la vista basada en la aplicación.  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>Para examinar los metadatos para operaciones de salida en la vista basada en aplicaciones  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** , seleccione **Client (Outbound operations)**.  
  
3. El **seleccionar una categoría** cuadro enumera las distintas vistas en la que se clasifican los artefactos de Oracle E-Business Suite.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/), y se muestran los nodos de categoría general disponibles en el nodo raíz en el **operaciones y categorías disponibles** cuadro.  
  
    ![Operaciones y categorías en el nivel raíz](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  Las operaciones estándar, como ExecuteNonQuery, ExecuteReader y ExecuteScalar están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md). Para obtener instrucciones sobre cómo ejecutar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
4. Expanda el **vista basada en la aplicación** nodo para ver todas las Oracle E-Business suite las aplicaciones disponibles en el servidor que está conectado. Expanda una aplicación para ver las categorías de tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitud disponible para esa aplicación.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **alerta** nodo, mantener el foco en el **vista basada en la aplicación** nodo y, a continuación, escriba `Alert`.  
  
5. Expanda el **tablas de interfaz** nodo para ver las tablas de la interfaz de la aplicación de Oracle. Haga clic en una tabla de la interfaz para ver la lista de las operaciones disponibles para la tabla en la **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar tablas de interfaz en Oracle E&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
   > [!NOTE]
   >  Si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer datos de esas columnas. El nombre de estas operaciones son Read_\<LOBColName\>. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Read_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB y BFILE el adaptador expondrá tantos cantidad Read_\<LOBColName\> operaciones.  
   >   
   >  De forma similar, si una tabla de la interfaz contiene las columnas de tipo BLOB, CLOB y NCLOB el adaptador también expone una operación específica para actualizar los datos en dichas columnas. El nombre de estas operaciones son Update_\<LOBColName\>. Por ejemplo, si la tabla de interfaz tiene una columna, FILE_DATA, de tipo BLOB, el adaptador expone un **Update_FILE_DATA** operación. Si una tabla de interfaz tiene más de una columna de tipo BLOB, CLOB y NCLOB el adaptador expondrá tantos cantidad Update_\<LOBColName\> operaciones. Tenga en cuenta que la operación de actualización no se admite en columnas de tipo BFILE.  
  
6. Expanda el **vistas de interfaz** nodo para ver las vistas de interfaz de la aplicación de Oracle. Haga clic en una vista de la interfaz para ver la lista de las operaciones disponibles para la vista en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar vistas de interfaz en Oracle E&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
   > [!NOTE]
   >  Si una vista de la interfaz contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer datos de esas columnas. El nombre de estas operaciones son Read_\<LOBColName\>. Por ejemplo, si la vista de la interfaz tiene una columna, FILE_CONTENT, de tipo BLOB, el adaptador expone un **Read_FILE_CONTENT** operación. Si una vista de la interfaz tiene más de una columna de tipo BLOB, CLOB, NCLOB o el adaptador BFILE expondrá tantos cantidad Read_\<LOBColName\> operaciones. Tenga en cuenta que Update_\<LOBColName\> operaciones no se admiten en las vistas.  
  
7. Haga clic en el **programas simultáneos** nodo para ver los programas simultáneos para una aplicación en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar programas simultáneos de la aplicación Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
    Esta ilustración muestra los programas simultáneos específicos para una aplicación de Oracle y los programas simultáneos estándares para todas las aplicaciones de Oracle.  
  
   > [!IMPORTANT]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de programas simultáneos. Sin embargo, los metadatos para el programa simultáneo tienen el nombre real del programa simultáneo. Por ejemplo, la aplicación de cuentas por cobrar contiene un programa simultáneo de "Interfaz de cliente". Sin embargo, los metadatos tiene el nombre de programa simultáneo como RACUST, que es el nombre real del programa simultáneo.  
  
8. Haga clic en el **solicitud establece** conjuntos de nodos para ver la solicitud para una aplicación en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar conjuntos de solicitudes para una aplicación Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
   > [!IMPORTANT]
   >  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) muestra los nombres descriptivos de los conjuntos de solicitudes. Sin embargo, los metadatos para el conjunto de solicitud tienen el nombre real del conjunto de solicitud. Por ejemplo, la aplicación de DBA de aplicaciones contiene un conjunto de solicitud "DownloadPatches". Sin embargo, los metadatos tiene el nombre del conjunto de solicitud como FNDRSSUB1623, que es el nombre real del conjunto de solicitud.  
  
## <a name="browsing-for-inbound-operations"></a>Buscar operaciones entrantes  
 Realice los pasos siguientes para examinar las operaciones de entrada en la vista basada en la aplicación.  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>Para examinar los metadatos para operaciones de entrada en la vista basada en aplicación  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista para operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3. El **seleccionar una categoría** cuadro enumera las distintas vistas en la que se clasifican los artefactos de Oracle E-Business Suite.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/), y se muestran los nodos de categoría general disponibles en el nodo raíz en el **operaciones y categorías disponibles** cuadro.  
  
    ![Operación en el nivel raíz de la entrada](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    La operación de entrada, **notificación**, también está disponible en el nivel raíz.  
  
4. Expanda el **vista basada en la aplicación** nodo para ver todas las Oracle E-Business suite las aplicaciones disponibles en el servidor que está conectado. Expanda una aplicación para ver las categorías de tablas y vistas de interfaz.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto en mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **alerta** nodo, mantener el foco en el **vista basada en la aplicación** nodo y, a continuación, escriba `Alert`.  
  
5. Expanda una aplicación de Oracle para ver las categorías de tablas y vistas de interfaz disponibles para esa aplicación. Expanda el **tablas de interfaz** y **vistas de interfaz** nodos para ver las tablas y vistas de interfaz de la aplicación de Oracle. Haga clic en una vista de tabla o la interfaz de interfaz para ver la operación de entrada disponible para la tabla o vista en el **operaciones y categorías disponibles** cuadro.  
  
    En la ilustración siguiente, se selecciona una vista de interfaz en el **seleccionar una categoría** cuadro y la operación de entrada compatible con la vista se muestra en el **operaciones y categorías disponibles** cuadro.  
  
    ![Operaciones entrantes en vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
   > [!NOTE]
   >  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no programas simultáneos de superficie y solicitar conjuntos de operaciones de entrada.  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)