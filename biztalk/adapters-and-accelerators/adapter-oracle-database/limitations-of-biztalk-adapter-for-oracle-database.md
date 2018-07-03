---
title: Limitaciones del adaptador de BizTalk para Oracle Database | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8138449cf3af067c9a76848f203c7e1809f6adbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986613"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>Limitaciones del adaptador de BizTalk para Oracle Database
## <a name="general"></a>General  
 Lo siguiente es limitaciones para conocidas el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
- Salvo algunas excepciones, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con la versión anterior de los adaptadores. Para obtener una lista de los cambios que ha sucedido desde la última versión, consulte [características clave en el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos de XML.  
  
- La operación SQLEXECUTE no devuelve los valores de salida o en los parámetros OUT procedimientos, funciones o los paquetes. Por este motivo, debe invocar procedimientos, funciones y paquetes mediante el uso de las operaciones dedicadas que los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.  
  
- Al recuperar datos de la base de datos de Oracle mediante el proxy de programación, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] deserializar los mensajes XML que tengan más de 65536 nodos. Asegúrese de que el mensaje de respuesta tiene nodos menor o igual a 65536. Puede evitar esta limitación si modifica el archivo app.config para su aplicación. Para obtener instrucciones, consulte [solucionar problemas de funcionamiento con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cadenas de entrada toma y construye los comandos SQL que se ejecutan mediante el adaptador. Sin embargo, la cadena de entrada podría contener otros comandos SQL que también se ejecutan y pueden provocar errores en el contrato de operación.  
  
   Considere un escenario donde el adaptador proporciona un REF CURSOR de entrada a un procedimiento almacenado. En este escenario, el cliente del adaptador debe proporcionar un comando que, cuando se ejecuta, obtiene el REF CURSOR. A continuación, el adaptador pasa el REF CURSOR en el procedimiento almacenado. Sin embargo, si el comando para obtener el REF CURSOR realiza algunas modificaciones adicionales en la base de datos, el contrato de operación para ejecutar el procedimiento almacenado se interrumpe.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite hasta dos niveles de anidamiento de UDT.  
  
- Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales en el WCF-custom puerto son incorrectos, no se procesan los mensajes de solicitud de envío. Después de especificar las credenciales correctas, el mensaje se envía a la base de datos de Oracle y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida. En estos escenarios, debe reiniciar la instancia de host.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (como registro tipo tabla tipo, UDT y VARRAY).  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos definidos por el usuario (UDT) que tienen referencias circulares.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.  
  
- Excepto para las tablas de PL/SQL, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT se definen dentro de un paquete.  
  
## <a name="limitations-due-to-odpnet"></a>Limitaciones debido a ODP.NET  
 Lo siguiente es limitaciones para conocidas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] debido a la limitación de ODP.NET:  
  
- Para los tipos de datos de Oracle que toman los valores decimales, ODP.NET no produce una excepción si el valor de entrada contiene caracteres alfabéticos. Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa ODP.NET para interactuar con la base de datos de Oracle, el adaptador demasiado no producir una excepción al pasar los caracteres alfabéticos. Por ejemplo:  
  
  -   Pasar un valor "54r" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "54".  
  
  -   Pasar un valor "r54" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "0".  
  
- Debido a una limitación de ODP.NET la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el uso de procedimientos sobrecargados con cursores REF cursor de fuertemente tipadas y débilmente tipada. Internamente, el adaptador trata los CURSORES REF fuertemente tipadas y débilmente tipada como simplemente cursores REF cursor.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite matrices asociativas que no contienen ningún elemento.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen un "." (punto) en sus nombres.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los UDT que contienen los tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.  
  
- El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.  
  
- Debido a la limitación de matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
  -   BFILE  
  
  -   BLOB  
  
  -   CLOB  
  
  -   IntervalDS  
  
  -   IntervalYM  
  
  -   Long  
  
  -   NCLOB  
  
  -   RowID  
  
  -   TimeStamp  
  
  -   TimeStampLTZ  
  
  -   TimeStampTZ  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)