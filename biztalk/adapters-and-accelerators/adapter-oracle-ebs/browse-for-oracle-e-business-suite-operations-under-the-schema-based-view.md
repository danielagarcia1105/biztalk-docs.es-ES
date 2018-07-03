---
title: Busque las operaciones de Oracle E-Business Suite en la vista de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d004a99f-0db1-4cdb-80cd-ea71de4e1098
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b6cc63adee4236cc3b392e0caba1b19ec97f95
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977733"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-schema-based-view"></a>Buscar operaciones de Oracle E-Business Suite en la vista basada en esquema
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar operaciones entrantes y salientes que se pueden realizar en Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. En este tema se proporciona información sobre cómo buscar operaciones entrantes y salientes en la vista de esquema.  
  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes esencialmente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los mismos temas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite para poder examinar los metadatos para las operaciones de destino. Para obtener información sobre cómo conectarse a Oracle base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="browsing-for-outbound-operations"></a>Exploración de las operaciones salientes  
 Realice los pasos siguientes para examinar las operaciones de salida en la vista de esquema.  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-schema-based-view"></a>Para examinar los metadatos para las operaciones de salida en la vista de esquema  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista para seleccionar las operaciones salientes **Client (Outbound operations)**.  
  
3. El **seleccionar una categoría** cuadro enumera las distintas vistas en la que se clasifican los artefactos de Oracle E-Business Suite.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/), y se muestran los nodos de categoría general disponibles en el nodo raíz en el **operaciones y categorías disponibles** cuadro.  
  
    ![Operaciones y categorías en el nivel raíz](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  Las operaciones estándar, como ExecuteNonQuery, ExecuteReader y ExecuteScalar están disponibles en el nivel raíz. Para obtener más información acerca de estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md). Para obtener instrucciones sobre cómo ejecutar estas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).  
  
4. Expanda el **vista basada en esquema** nodo para ver los esquemas definidos en la base de datos subyacente. Cada esquema se clasifican a su vez basándose en la API PL-SQL, procedimientos, funciones, tablas y vistas que lo contiene.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **SCOTT** esquema, mantener el foco en el **vista basada en esquema** nodo y, a continuación, escriba `SCOTT`.  
  
5. Expanda el **API PL-SQL** nodo para ver la lista de paquetes definido en la base de datos de Oracle para un esquema determinado. Haga clic en un nombre de paquete para ver las funciones y procedimientos definidos dentro de ese paquete en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar paquetes en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/582a9bd7-beed-4b36-b465-f5c4ceb6e740.gif "582a9bd7-beed-4b36-b465-f5c4ceb6e740")  
  
6. Haga clic en el **procedimientos** nodo para ver la lista de procedimientos en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar procedimientos en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/7213154e-6a26-4fc3-b4ec-1658779f77d3.gif "7213154e-6a26-4fc3-b4ec-1658779f77d3")  
  
7. Haga clic en el **funciones** nodo para ver la lista de funciones en el **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar funciones en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/5df9b42c-9d8b-4c81-a0ae-ba5336445837.gif "5df9b42c-9d8b-4c81-a0ae-ba5336445837")  
  
8. Expanda el **tablas** nodo para ver la lista de tablas para un esquema determinado. Haga clic en un nombre de tabla para ver las operaciones admitidas en la tabla en la **operaciones y categorías disponibles** cuadro.  
  
    ![Buscar tablas en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/94dd4642-1178-4d88-986b-f0ad409c414c.gif "94dd4642-1178-4d88-986b-f0ad409c414c")  
  
   > [!NOTE]
   >  Si una tabla contiene columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer datos de esas columnas. El nombre de estas operaciones son Read_\<LOBColName\>. Por ejemplo, si la tabla tiene una columna, foto, del tipo de BLOB, el adaptador expone un **Read_PHOTO** operación. Si una tabla tiene más de una columna de tipo BLOB, CLOB, NCLOB y BFILE el adaptador expondrá tantos cantidad Read_\<LOBColName\> operaciones.  
   >   
   >  De forma similar, si una tabla contiene columnas de tipo BLOB, CLOB y NCLOB el adaptador también expone una operación específica para actualizar los datos en dichas columnas. El nombre de estas operaciones son Update_\<LOBColName\>. Por ejemplo, si la tabla tiene una columna, foto, del tipo de BLOB, el adaptador expone un **Update_PHOTO** operación. Si una tabla tiene más de una columna de tipo BLOB, CLOB y NCLOB el adaptador expondrá tantos cantidad Update_\<LOBColName\> operaciones. Tenga en cuenta que la operación de actualización no se admite en columnas de tipo BFILE.  
  
9. Expanda el **vistas** nodo para ver la lista de vistas para un esquema determinado. Haga clic en un nombre de vista para ver las operaciones admitidas en la vista en el **operaciones y categorías disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/e1893e48-065c-4642-b076-192758d103db.gif "e1893e48-065c-4642-b076-192758d103db")  
  
    > [!NOTE]
    >  Si una vista contiene las columnas de tipo BLOB, CLOB, NCLOB o BFILE el adaptador también expone una operación específica para leer datos de esas columnas. El nombre de estas operaciones son Read_\<LOBColName\>. Por ejemplo, si la vista tiene una columna, tipo de regla, BLOB, el adaptador expone un **Read_RULE** operación. Si una vista tiene más de una columna de tipo BLOB, CLOB, NCLOB o el adaptador BFILE expondrá tantos cantidad Read_\<LOBColName\> operaciones. Tenga en cuenta que Update_\<LOBColName\> operaciones no se admiten en las vistas.  
  
## <a name="browsing-for-inbound-operations"></a>Buscar operaciones entrantes  
 Realice los pasos siguientes para examinar las operaciones de entrada en la vista de esquema.  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-schema-based-view"></a>Para examinar los metadatos para operaciones de entrada en la vista de esquema  
  
1. Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2. Desde el **seleccione el tipo de contrato** lista para operaciones de entrada, seleccione **(operaciones de entrada) de servicio**.  
  
3. El **seleccionar una categoría** cuadro enumera las distintas vistas en la que se clasifican los artefactos de Oracle E-Business Suite.  
  
    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Se selecciona el nodo raíz (/), y se muestran los nodos de categoría general disponibles en el nodo raíz en el **operaciones y categorías disponibles** cuadro.  
  
    ![Operación en el nivel raíz de la entrada](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    La operación de entrada, **notificación**, también está disponible en el nivel raíz.  
  
4. Expanda el **vista basada en esquema** nodo para ver los esquemas definidos en la base de datos subyacente. Cada esquema se clasifican a su vez basándose en la API PL-SQL, procedimientos, funciones, tablas y vistas que lo contiene.  
  
   > [!TIP]
   >  Puede ir directamente a la categoría "inmediatos" nodos de subcategoría en el árbol, escribiendo el nombre del artefacto mientras el foco está en la vista de árbol en el **seleccionar una categoría** cuadro. Por ejemplo, para saltar a la **SCOTT** esquema, mantener el foco en el **vista basada en esquema** nodo y, a continuación, escriba `SCOTT`.  
  
5. Expanda el **API PL-SQL** nodo para ver la lista de paquetes definido en la base de datos de Oracle para un esquema determinado. Haga clic en un nombre de paquete para ver las funciones y procedimientos definidos dentro de ese paquete en el **operaciones y categorías disponibles** cuadro. Cada una de las funciones enumeradas y los procedimientos se puede usar para sondear la base de datos de Oracle.  
  
    ![Examinar paquetes en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/ab45e4a3-1425-4b23-afc2-8aecef546802.gif "ab45e4a3-1425-4b23-afc2-8aecef546802")  
  
6. Haga clic en el **procedimientos** nodo para ver la lista de procedimientos de **las operaciones y categorías disponibles** cuadro. Cada uno de los procedimientos enumerados puede usarse para sondear la base de datos de Oracle.  
  
    ![Examinar procedimientos en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/04538693-5abf-4162-82e9-4107b4088b56.gif "04538693-5abf-4162-82e9-4107b4088b56")  
  
7. Haga clic en el **funciones** nodo para ver la lista de funciones en el **operaciones y categorías disponibles** cuadro. Cada una de las funciones enumeradas se puede usar para sondear la base de datos de Oracle.  
  
    ![Examinar funciones en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b.gif "b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b")  
  
8. Expanda el **tablas** nodo para ver la lista de tablas para un esquema determinado. Haga clic en un nombre de tabla para ver el **sondeo** operación admitida en la tabla de entrada la **operaciones y categorías disponibles** cuadro.  
  
    ![Examinar tablas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/58e9315d-3194-4a01-a505-bd1514e9d7e3.gif "58e9315d-3194-4a01-a505-bd1514e9d7e3")  
  
9. Expanda el **vistas** nodo para ver la lista de vistas para un esquema determinado. Haga clic en un nombre de vista para ver el **sondeo** admitida la vista en la operación de entrada la **operaciones y categorías disponibles** cuadro.  
  
     ![Examinar vistas en la base de datos de Oracle para sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1282f17-efbe-43e6-90fa-5676e04051e8.gif "f1282f17-efbe-43e6-90fa-5676e04051e8")  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)