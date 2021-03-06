---
title: Limitaciones del adaptador de BizTalk para SQL Server | Microsoft Docs
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
ms.openlocfilehash: 195701e4bba469a7faaab36a5ae1636c5abca5f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967389"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>Limitaciones del adaptador de BizTalk para SQL Server
Lo siguiente es limitaciones para conocidas [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
- El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite los sinónimos creados en la base de datos de SQL Server. Para obtener información acerca de los sinónimos en SQL Server, vea [ http://go.microsoft.com/fwlink/?LinkId=120111 ](http://go.microsoft.com/fwlink/?LinkId=120111).  
  
- Si cambia la hora del sistema del equipo que ejecuta el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, el tiempo no se actualiza automáticamente en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host. Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que usan el puerto de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción después de haber cambiado la hora del sistema del equipo ejecuta.  
  
- Si un nombre de parámetro en un procedimiento almacenado contiene 127 o más caracteres, no se puede ejecutar el procedimiento almacenado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Esto es debido a la limitación de ADO.NET.  
  
- El WSDL del [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] genera cuando se convierte en un servidor proxy, expone la columna DateTimeOffset como System.DateTime. Este tipo de datos no puede almacenar información de zona horaria. Como consecuencia, cualquier valor de fecha y hora que el adaptador envía al servidor proxy se convertirán en hora local en la aplicación. NET. Si desea mantener la información de zona horaria, debe cambiar la interfaz del proxy se utiliza el tipo de cadena en lugar de System.DateTime. A continuación, use XmlConvert.ToDateTimeOffset para crear un objeto Sytstem.DateTimeOffset, que puede almacenar la información de zona horaria.  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)