---
title: Tipos de datos básicos de SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f744fe14-4134-486d-b060-9ac2d5f21c56
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8e60816dc362fc4630e263397048bcdee8d774b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222620"
---
# <a name="basic-sql-server-data-types"></a>Tipos de datos básicos de SQL Server
Este tema se describe cómo la [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]expone los tipos de datos básicos de SQL Server.  
  
## <a name="supported-sql-server-data-types"></a>Tipos de datos de SQL Server admitidos  
 En la tabla siguiente se muestra cómo aparecen los tipos de datos de SQL Server por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
|Tipo de datos de SQL Server|Tipo XSD|Tipo de .NET|Comentarios|  
|--------------------------|--------------|---------------|--------------|  
|Bigint|Long|Long|-|  
|Binario|Base64Binary|Byte[]|-|  
|bit|Boolean|Bool|-|  
|Char|String|String|-|  
|Date|DateTime|DateTime|-|  
|Fecha y hora|DateTime|DateTime|Al escribir datos en un campo de fecha y hora, el adaptador siempre almacena la hora en GMT. Si se especifica la información de zona horaria, el adaptador usa para convertir el valor en un valor válido de GMT y lo escribe en la tabla de base de datos. Por ejemplo, 12/31/2008T23:59:59 + 5:30 se escribe en la tabla como 31/12/2008 6:29:59 PM.<br /><br /> Sin embargo, si no se especifica la información de zona horaria, el adaptador tiene en cuenta el valor sea ya GMT y escribe el mismo valor en la tabla. Por ejemplo, 12/31/2008T23:59:59 se escribe en la tabla como 31/12/2008 11:59:59 PM.|  
|Datetime2|DateTime|DateTime|-|  
|Datetimeoffset|DateTime|DateTime|-|  
|Decimal|xsd: decimal si precisión < = 28<br /><br /> xsd: String si precisión > 28|Decimal si precisión < = 28<br /><br /> La cadena si precisión > 28|-|  
|Secuencia de archivos|Base64Binary|Byte[]|-|  
|Float|Doble|Doble|-|  
|Geografía|String|String|-|  
|Geometría|String|String|-|  
|Hierarchyid|String|String|-|  
|Imagen|Base64Binary|Byte[]|-|  
|int|int|int|-|  
|Money|Decimal|Decimal|-|  
|Nchar|String|String|-|  
|Ntext|String|String|-|  
|Numérico|Decimal|Decimal|-|  
|nvarchar|String|String|-|  
|Nvarchar (max)|String|String|-|  
|Real|Float|Float|-|  
|Smalldatetime|DateTime|DateTime|-|  
|Smallint|Short|Short|-|  
|Smallmoney|Decimal|Decimal|-|  
|SQLVariant|String|String|-|  
|Texto|String|String|-|  
|Time|Duración|intervalo de tiempo|-|  
|Timestamp|Base64Binary|Byte[]|-|  
|Tinyint|UnsignedByte|Byte|-|  
|Uniqueidentifier|{http://schemas.microsoft.com/2003/10/Serialization/}: guid|Guid|-|  
|Varbinary|Base64Binary|Byte[]|-|  
|Varbinary (max)|Base64Binary|Byte[]|-|  
|Varchar|String|String|-|  
|Varchar (max)|String|String|-|  
|XML|String|String|-|  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)