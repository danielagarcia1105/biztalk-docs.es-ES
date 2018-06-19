---
title: Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba5e110af598ac75ca9a8b6e7ebf2e5e8acc7aee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214396"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a>Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:  
  
-   Objeto binario grande (BLOB)  
  
-   Objeto grande de caracteres (CLOB)  
  
-   Objeto grande de caracteres nacional (NCLOB)  
  
-   Archivo binario (BFILE). Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
  
 En la base de datos de Oracle, los tipos de datos LOB se utilizan para almacenar grandes cantidades de datos (hasta 4 GB). Tipos LOB admiten entrada y salida de transmisión por secuencias.  
  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] presenta las siguientes operaciones para tablas y vistas que contienen columnas LOB:  
  
-   **ReadLOB**. La operación de ReadLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB, NCLOB y BFILE. Mediante el uso de la operación de ReadLOB, los clientes de adaptador pueden leer valores de una columna LOB como un flujo de datos. Esta operación toma como parámetros el nombre de columna de tipo de datos LOB y una cadena de filtro. Los clientes de adaptador deben asegurarse de que la cadena de filtro captura exactamente una fila coincidente. Si hay más de una fila coincidente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] solo devuelve la columna LOB para la primera fila (coincidencia).  
  
    > [!NOTE]
    >  La operación ReadLOB está diseñada para admitir la transmisión de entrada de datos LOB en el modelo de servicio WCF. Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canales de WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución. Para obtener más información sobre el streaming, vea [compatibilidad con el Streaming de tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).  
  
-   **UpdateLOB**. La operación de UpdateLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB y NCLOB. Mediante el uso de la operación de UpdateLOB, los clientes de adaptador pueden actualizar valores en una columna LOB. Esta operación toma el nombre de columna de tipo de datos LOB, una cadena de filtro, y datos como parámetros codificados de base64binary. Los clientes de adaptador deben asegurarse de que la cadena de filtro captura exactamente una fila coincidente; de lo contrario el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una XmlReaderParsingException.  
  
    > [!NOTE]
    >  La operación UpdateLOB:  
    >   
    >  -   No se admite para el tipo de datos BFILE. Los clientes de adaptador o bien pueden usar la operación de actualización. Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
    > -   Debe realizarse como parte de una transacción. Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**. Para obtener información sobre la **UseAmbientTransaction** enlace de propiedad, vea [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
> [!NOTE]
>  ReadLOB y UpdateLOB operan en una sola columna LOB en una sola fila de tabla. Para que funcione en las columnas LOB en varias filas o en varias columnas LOB de una sola fila, debe invocar ReadLOB o UpdateLOB para cada columna de destino dentro de cada fila de destino.  
  
 Para obtener más información acerca de:  
  
-   Invocar la operación UpdateLOB en una tabla de base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [realizar operaciones en tablas con datos de tipos de objeto grandes por mediante BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx). (Debe utilizar una operación de selección de tabla para leer los tipos de datos LOB en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)  
  
-   Invocar operaciones ReadLOB y UpdateLOB en una tabla de base de datos de Oracle mediante el modelo de servicio WCF, vea [ejecutar operaciones en tablas con tipos de objeto grandes mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).  
  
-   Estructura y acciones SOAP para realizar operaciones de ReadLOB y UpdateLOB de mensajes, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)