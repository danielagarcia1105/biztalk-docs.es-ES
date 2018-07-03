---
title: Operaciones en tablas, vistas de interfaz, tablas y vistas que contienen datos LOB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f1336c1d6f5fb6ea7c0b68e4c7670616f141583
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967693"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a>Operaciones en tablas, vistas de interfaz, tablas y vistas que contienen datos LOB
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] proporciona compatibilidad para los tipos de datos de objetos grandes (LOB) de Oracle:  
  
- Objeto binario grande (BLOB)  
  
- Objeto grande de caracteres (CLOB)  
  
- Objetos grandes de carácter nacional (NCLOB)  
  
- Archivo binario (BFILE). Para obtener más información, consulte [operaciones en tablas que contienen tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
  
  En la base de datos de Oracle subyacente, los tipos de datos LOB se usan para almacenar grandes cantidades de datos, hasta 4 gigabytes (GB). Excepto para el tipo de datos BFILE, los tipos de datos LOB admiten entrada y salida de transmisión por secuencias.  

## <a name="operations-for-tables-and-views"></a>Operaciones de tablas y vistas  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] presenta las siguientes operaciones en tablas, vistas de interfaz, tablas y vistas que contienen columnas LOB:  
  
- **Read_\<LOBColName\>**: el `Read_<LOBColName>` operación aparece para las tablas, vistas de interfaz, tablas y vistas que contienen columnas BLOB, CLOB, NCLOB y BFILE, donde \<LOBColName\>es el nombre de la columna de tipo BLOB, CLOB, NCLOB o BFILE. Mediante el uso de la Read_\<LOBColName\> operación, los clientes del adaptador pueden leer valores de una columna LOB como un flujo de datos. Esta operación acepta una cadena de filtro como parámetro.  
  
  > [!NOTE]
  >  El `Read_<LOBColName>` operación está diseñada para admitir la entrada de transmisión por secuencias de datos LOB en el modelo de servicio WCF. Debe usar una operación de selección de tabla para leer datos LOB de un modelo de canal WCF o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- **Update_\<LOBColName\>**: el `Update_<LOBColName>` operación aparece para las tablas de interfaz y las tablas solo que contienen columnas BLOB, CLOB y NCLOB, donde \<LOBColName\> es el nombre de la columna de tipo de BLOB, CLOB y NCLOB. Mediante el uso de la Update_\<LOBColName\> operación, los clientes del adaptador pueden actualizar valores en una columna LOB. Para el tipo de datos BLOB, esta operación toma datos codificados de base64binary como el parámetro, mientras que para los tipos de datos CLOB y NCLOB esta operación tiene un filtro de cadena como parámetro.  
  
  > [!NOTE]
  >  El `Update_<LOBColName>` operación:  
  > 
  > - No se admite para el tipo de datos BFILE. Los clientes del adaptador o bien pueden usar la operación de actualización. Para obtener más información, consulte [operaciones en tablas que contienen tipos de datos BFILE](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).  
  >   -   No se expone para las vistas y las vistas de interfaz.  
  >   -   Debe realizarse como parte de una transacción. Para asegurarse de esto, el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **True**. Para obtener información sobre la **UseAmbientTransaction** enlaza la propiedad, vea [Rad acerca del adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
> [!IMPORTANT]
>  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] superficies un `Read_<LOBColName>` y un `Update_<LOBColName>` operación para cada columna LOB de una tabla. Por lo tanto, si hay dos columnas LOB en una tabla (LOBCol1 y LOBCol2), tiene dos `Read_<LOBColName>` operaciones (Read_LOBCol1 y Read_LOBCol2) y dos `Update_<LOBColName>` operaciones (Update_LOBCol1 y Update_LOBCol2).  
  
## <a name="more-good-info"></a>Obtener más información buena  
  
- Invocar el `Read_<LOBColName>` y `Update_<LOBColName>` operaciones en una tabla en la base de datos subyacente utilizando Oracle E-Business Suite [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones en tablas con grandes tipos de datos mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md).  
  
- Estructura de mensajes de acciones SOAP para llevar a cabo `Read_<LOBColName>` y `Update_<LOBColName>` operaciones, vea [esquemas de mensaje para operaciones especiales de LOB](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)