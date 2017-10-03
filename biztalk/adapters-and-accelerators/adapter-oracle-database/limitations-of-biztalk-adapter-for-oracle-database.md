---
title: Limitaciones del adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6cfea523333752c0ee18fefbc6a1848057fe36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a>Limitaciones del adaptador de BizTalk para base de datos de Oracle
## <a name="general"></a>General  
 Los siguientes son limitaciones para conocidas el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   Salvo algunas excepciones, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con la versión anterior de los adaptadores. Para obtener una lista de cambios que se ha producido desde la última versión, consulte [características clave en el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite los tipos de XML.  
  
-   La operación SQLEXECUTE no devuelve los valores de salida o en los parámetros OUT procedimientos, funciones o paquetes. Por este motivo, debe invocar procedimientos, funciones y paquetes mediante las operaciones dedicadas que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.  
  
-   Al recuperar datos de la base de datos de Oracle mediante el proxy de programación, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] deserializar los mensajes XML que tienen más de 65536 nodos. Asegúrese de que el mensaje de respuesta tiene nodos menor o igual que 65536. Puede evitar esta limitación si modifica el archivo app.config para la aplicación. Para obtener instrucciones, consulte [solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] entrada toma las cadenas y construye los comandos SQL que se ejecutan, a continuación, el adaptador. Sin embargo, la cadena de entrada puede contener otros comandos SQL que también se ejecutan y pueden provocar errores en el contrato de operación.  
  
     Considere un escenario donde el adaptador proporciona un REF CURSOR de entrada a un procedimiento almacenado. En este escenario, el adaptador cliente debe proporcionar un comando que, cuando se ejecuta, obtiene el REF CURSOR. A continuación, pasa el adaptador en el REF CURSOR al procedimiento almacenado. Sin embargo, si el comando para obtener el REF CURSOR realiza algunas modificaciones adicionales en la base de datos, el contrato de operación para ejecutar el procedimiento almacenado se interrumpe.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite UDT hasta dos niveles de anidamiento.  
  
-   Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales de WCF-custom puerto son correctos, no se procesan los mensajes de solicitud de envío. Después de especificar las credenciales correctas, el mensaje se envía a la base de datos de Oracle y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida. En estos escenarios, debe reiniciar la instancia de host.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (por ejemplo, registro tipo, tabla tipo, UDT y VARRAY).  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos definidos por el usuario (UDT) que se haya referencias circulares.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.  
  
-   Excepto para tablas de PL/SQL, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite UDT que se definen dentro de un paquete.  
  
## <a name="limitations-due-to-odpnet"></a>Limitaciones debido a ODP.NET  
 Los siguientes son limitaciones para conocidas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] debido a la limitación de ODP.NET:  
  
-   Para los tipos de datos de Oracle que toman los valores decimales, ODP.NET no produce una excepción si el valor de entrada contiene caracteres alfabéticos. Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza ODP.NET para comunicarse con la base de datos de Oracle, el adaptador demasiado no produce una excepción al pasar caracteres alfabéticos. Por ejemplo:  
  
    -   Se pasa un valor "54r" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "54".  
  
    -   Se pasa un valor "r54" para una operación de inserción no produce una excepción; en su lugar, se inserta el valor "0".  
  
-   Debido a una limitación de ODP.NET, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite el uso de procedimientos sobrecargados con cursores REF cursor de fuertemente tipadas y débilmente tipada. Internamente, el adaptador trata los CURSORES REF fuertemente tipadas y débilmente tipada como simplemente cursores REF cursor.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite matrices asociativas que no contiene ningún elemento.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite UDT que contengan un "." (punto) en sus nombres.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite UDT que contienen tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.  
  
-   Debido a la limitación de las matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
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
 [Comprender el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)