---
title: Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: a35be7008c47e46ca65962d113c4604c1cfad42b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984301"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a>Operaciones en tablas y vistas que contienen datos LOB en la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:  
  
- Objeto binario grande (BLOB)  
  
- Objeto grande de caracteres (CLOB)  
  
- Objetos grandes de carácter nacional (NCLOB)  
  
- Archivo binario (BFILE). Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
  
  En la base de datos de Oracle, los tipos de datos LOB se usan para almacenar grandes cantidades de datos (hasta 4 GB). Tipos LOB admiten entrada y salida de transmisión por secuencias.  
  
  El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] presenta las siguientes operaciones en tablas y vistas que contienen columnas LOB:  
  
- **ReadLOB**. La operación ReadLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB, NCLOB y BFILE. Mediante el uso de la operación ReadLOB, los clientes del adaptador pueden leer valores de una columna LOB como un flujo de datos. Esta operación toma como parámetros el nombre de columna de tipo de datos LOB y una cadena de filtro. Los clientes del adaptador deben asegurarse de que la cadena de filtro recopila exactamente una fila coincidente. Si hay más de una fila coincidente, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] solo devuelve la columna LOB para la primera fila (coincidencia).  
  
  > [!NOTE]
  >  La operación ReadLOB está diseñada para admitir la entrada de transmisión por secuencias de datos LOB en el modelo de servicio WCF. Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canal de WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución. Para obtener más información sobre el streaming, consulte [compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).  
  
- **UpdateLOB**. La operación UpdateLOB aparece para las tablas y vistas que contienen columnas BLOB, CLOB y NCLOB. Mediante el uso de la operación UpdateLOB, los clientes del adaptador pueden actualizar valores en una columna LOB. Esta operación toma el nombre de columna de tipo de datos LOB, una cadena de filtro y datos como parámetros codificados de base64binary. Los clientes del adaptador deben asegurarse de que la cadena de filtro recopila exactamente una fila coincidente; de lo contrario el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una XmlReaderParsingException.  
  
  > [!NOTE]
  >  La operación UpdateLOB:  
  > 
  > - No se admite para el tipo de datos BFILE. Los clientes del adaptador o bien pueden usar la operación de actualización. Para obtener más información, consulte [operaciones en tablas que contiene los tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
  >   -   Debe realizarse como parte de una transacción. Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**. Para obtener información sobre la **UseAmbientTransaction** enlaza la propiedad, vea [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
> [!NOTE]
>  ReadLOB y UpdateLOB operan en una sola columna LOB en una sola fila de tabla. Para que funcione en las columnas LOB en varias filas o en varias columnas LOB de una sola fila, debe invocar ReadLOB o UpdateLOB para cada columna de destino dentro de cada fila de destino.  
  
 Para obtener más información acerca de:  
  
- Invocar la operación UpdateLOB en una tabla de base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [realizar operaciones en tablas con datos de tipos de objeto grande por mediante BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx). (Debe usar una operación de selección de tabla para leer los tipos de datos LOB en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)  
  
- Invocar operaciones ReadLOB y UpdateLOB en una tabla de base de datos de Oracle mediante el modelo de servicio WCF, vea [ejecutar operaciones en tablas con tipos de objeto grande mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).  
  
- Estructura de mensajes de acciones SOAP para realizar operaciones de ReadLOB y UpdateLOB, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)