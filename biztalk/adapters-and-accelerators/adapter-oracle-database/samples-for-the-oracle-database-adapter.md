---
title: Ejemplos para el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- samples, WCF channel model
- samples, WCF service model
- samples, BizTalk
- samples, migration
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4973c0b4ea54ef3b7692dbe4be19773acf1e6e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a>Ejemplos para el adaptador de la base de datos de Oracle
Ejemplos de [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] se clasifican en categorías:  
  
-   Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
-   Ejemplos de modelo de servicio WCF  
  
-   Ejemplos de modelo de canal WCF  
  
-   Ejemplos de migración  
  
 Los ejemplos están disponibles en [http://go.microsoft.com/fwlink/p/?LinkID=196854](http://go.microsoft.com/fwlink/p/?LinkID=196854). Los scripts SQL para crear las tablas, paquetes, etcetera. usar en los ejemplos también están disponibles junto con los ejemplos para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 En la lista siguiente contiene los nombres y descripciones de los ejemplos para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|Func_RecordTypes|Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Func_RefCursor|Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|InvokeFunction|Muestra cómo invocar una función de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|InvokeOverloadedProc|Muestra cómo invocar con las funciones sobrecargadas y los procedimientos de la base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Operate_BFILE|Muestra cómo utilizar tipos BFILE de Oracle en los procedimientos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|Operate_LOB|Muestra cómo realizar operaciones de ReadLOB y UpdateLOB en tablas con tipos de datos LOB mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|PollingQuery|Muestra cómo configurar una consulta de sondeo y recibir los resultados utilizando la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|SelectAccTable|Muestra cómo realizar una consulta select en una tabla de base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
|SqlExec|Muestra cómo realizar consultas con parámetros mediante la operación SQLEXECUTE en una base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].|  
  
## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|OracleBfileTypeSM|Muestra cómo utilizar tipos BFILE de Oracle en las operaciones básicas de SQL que aparecen para las tablas de Oracle y como parámetros a procedimientos de Oracle.|  
|OracleOverloadsSM|Muestra cómo invocar las funciones sobrecargadas y los procedimientos de un paquete.|  
|OraclePollingSM|Muestra cómo configurar una consulta de sondeo y recibir los resultados.|  
|OracleRecordTypesSM|Muestra cómo usar parámetros de tipo de registro y valores devueltos en funciones y procedimientos.|  
|OracleRefCursorsSM|Muestra cómo utilizar los parámetros REF CURSOR en funciones y procedimientos|  
|OracleTransactedDmlSM|Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción utilizando el modelo de servicio WCF.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal de WCF  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|OraclePollingCM|Muestra cómo configurar una consulta de sondeo y recibir los resultados.|  
|OracleStreamingDemo|Muestra cómo realizar-to-end de transmisión por secuencias de datos LOB mediante las operaciones Select UpdateLOB y tabla|  
|OracleTransactedDmlCM|Muestra cómo realizar operaciones en la base de datos de Oracle en una transacción mediante el modelo de canal WCF.|  
  
## <a name="migration-samples"></a>Ejemplos de migración  
  
|Nombre del directorio de ejemplo|Description|  
|---------------------------|-----------------|  
|Oracle_Migration|Muestra cómo utilizar un proyecto de BizTalk creado con el adaptador de BizTalk ODBC para base de datos de Oracle (suministrado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]) y ponerla en marcha con basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] (incluido con [!INCLUDE[adapterpack20](../../includes/adapterpack20-md.md)]).|  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)