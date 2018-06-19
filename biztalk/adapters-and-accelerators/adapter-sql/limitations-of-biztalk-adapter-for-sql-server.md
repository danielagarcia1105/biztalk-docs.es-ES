---
title: Limitaciones del adaptador de BizTalk para SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a80990a9e3f417b64a06d8823300d53b2c4f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222684"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>Limitaciones del adaptador de BizTalk para SQL Server
Los siguientes son limitaciones para conocidas [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
-   El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no es compatible con los sinónimos creados en la base de datos de SQL Server. Para obtener información acerca de los sinónimos en SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111).  
  
-   Si cambia la hora del sistema del equipo que ejecuta el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, el tiempo no se actualiza automáticamente en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host. Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que utilizan el puerto de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción después de haber cambiado la hora del sistema del equipo ejecuta.  
  
-   Si un nombre de parámetro en un procedimiento almacenado contiene 127 o varios caracteres, no se puede ejecutar el procedimiento almacenado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Esto es debido a la limitación de ADO.NET.  
  
-   El WSDL del [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] genera, cuando se convierte en un servidor proxy, expone la columna DateTimeOffset como System.DateTime. Este tipo de datos no puede almacenar información de zona horaria. En consecuencia, cualquier valor de fecha y hora que el adaptador envía al servidor proxy se convertirán en hora local en la aplicación. NET. Si desea mantener la información de zona horaria, debe cambiar la interfaz del proxy para utilizar el tipo de cadena en lugar de System.DateTime. A continuación, utilice XmlConvert.ToDateTimeOffset para crear un objeto Sytstem.DateTimeOffset, que puede almacenar la información de zona horaria.  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)