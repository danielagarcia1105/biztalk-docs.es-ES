---
title: Limitaciones del adaptador de BizTalk para Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216276"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a>Limitaciones del adaptador de BizTalk para Oracle E-Business Suite
## <a name="general-limitations"></a>Limitaciones generales  
 Los siguientes son limitaciones para conocidas [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no es compatible con puerta de enlace de XML, la cola de mensajes avanzada y eventos empresariales.  
  
     Sin embargo, puede sortear la limitación de eventos empresariales de la manera siguiente:  
  
    1.  En el sistema de eventos de negocio de Oracle, cree una suscripción para invocar un procedimiento de PL/SQL personalizado cuando se produce un evento de negocio.  
  
    2.  Escribir un procedimiento personalizado de PL/SQL que recibe el evento de negocio.  
  
    3.  Utilice el procedimiento personalizado de PL/SQL para almacenar los datos resultantes (evento y carga del evento) en una tabla.  
  
    4.  Use la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear y/o recibir notificaciones de la tabla.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite los tipos de XML.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no permiten a los clientes establecer el valor del primer elemento en un VARRAY en NULL.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no no los registros de soporte técnico que contienen campos de tipo de tablas de PL/SQL del tipo de registro.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos definidos por el usuario (UDT) que se haya referencias circulares.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite el tipo de datos BFILE dentro de los tipos complejos (por ejemplo, registro tipo, tabla tipo, UDT y VARRAY).  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite UDT hasta dos niveles de anidamiento.  
  
-   Excepto para tablas de PL/SQL, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que se definen dentro de un paquete.  
  
-   Al usar los adaptadores con BizTalk Server, si el puerto de envío de las credenciales de WCF-custom son incorrectas, no se procesan los mensajes de solicitud. Después de especificar las credenciales correctas, el mensaje se envía a Oracle E-Business Suite y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida. En estos escenarios, debe reiniciar la instancia de host.  
  
## <a name="limitations-due-to-odpnet"></a>Limitaciones debido a ODP.NET  
 Los siguientes son limitaciones para conocidas [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] debido a la limitación de ODP.NET:  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tablas de PL/SQL que no están indizadas por un campo numérico.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite matrices asociativas que no contiene ningún elemento.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contienen el tipo de datos de marca de tiempo con atributos de zona horaria local (TimeStampLTZ).  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contengan un "." (punto) en sus nombres.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite UDT que contienen tipos de datos BLOB, CLOB y NCLOB como un parámetro IN OUT.  
  
-   El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite Varray de Varray de los siguientes tipos simples: BFILE, IntervalDS, IntervalYM, TimeStampLTZ y TimeStampTZ.  
  
-   Debido a la limitación de las matrices asociativas, tablas de PL/SQL de registros que contienen cualquiera de los siguientes tipos de datos o tablas de PL/SQL no se admiten en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
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
 [Comprender el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)