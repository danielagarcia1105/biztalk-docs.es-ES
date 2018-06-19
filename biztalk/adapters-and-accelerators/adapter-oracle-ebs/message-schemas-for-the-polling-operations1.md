---
title: Esquemas de mensajes para el sondeo Operations1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c572c4ec-0a3f-42b8-bebd-40eb584438ad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61aa47a7f991c140e0c0659b67da658a11a7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216148"
---
# <a name="message-schemas-for-the-polling-operations"></a>Esquemas de mensaje para las operaciones de sondeo
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]expone varias operaciones de entrada relacionadas para sondeo según el objeto de destino en Oracle E-Business Suite. Para tablas de interfaz, vistas de interfaz, tablas y vistas, aparece una sola operación de sondeo, mientras que puede tener varias operaciones de sondeo personalizado para las API de PL/SQL, funciones y procedimientos almacenados.  
  
 Configurar las operaciones de sondeo estableciendo las propiedades de enlace el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Para obtener más información acerca de estas propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Establece el **PollingStatement** enlace de propiedad para especificar una instrucción SQL, procedimiento almacenado, función o un procedimiento dentro de un paquete para la consulta de sondeo. El conjunto de resultados de esta consulta se devuelve como datos en el código en la operación de sondeo.  
  
## <a name="message-structure-for-the-polling-operations"></a>Estructura de los mensajes para las operaciones de sondeo  
 En la tabla siguiente se muestra la estructura del mensaje XML para las distintas operaciones de sondeo.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Objeto de destino|Mensaje XML|Description|  
|---------------|-------------------|-----------------|-----------------|  
|Sondeo|: Tablas de interfaz<br /><br /> : Vistas de interfaz<br /><br /> -Tablas<br /><br /> -Vistas|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|Por ejemplo, el mensaje XML para la operación de sondeo en tablas de interfaz será como se indica a continuación:<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|[CustomPollingOperation]|-API PL/SQL<br /><br /> -Procedimientos<br /><br /> : Funciones|**API de PL/SQL**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **Funciones**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **Procedimientos almacenados**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|La estructura del conjunto en la operación de sondeo de resultados se determina por el tipo de datos de los elementos en el objeto de destino.|  
  
 Descripciones de entidad:  
  
 [Versión] = http://schemas.microsoft.com/OracleEBS/2008/05.  
  
 [CustomPollingOperation] = nombre de la operación de sondeo personalizado.  
  
 [Esquema] = nombre del esquema de Oracle. Por ejemplo, SCOTT.  
  
 [API de PL/SQL] = nombre de la API de PL/SQL en el que se realiza una operación de sondeo personalizado.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)