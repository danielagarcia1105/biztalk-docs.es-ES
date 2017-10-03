---
title: Compatibilidad con EDI en BizTalk Server2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6162276e5e394bd17b75825535ddaf097a7f589c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-support-in-biztalk-server"></a>Compatibilidad con EDI en BizTalk Server
Las diferentes versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admiten EDI en las siguientes características y componentes:  
  
|Versión|Componente/función que proporciona la compatibilidad de EDI|  
|---|---|  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]y todas las versiones más recientes|Funcionalidad nativa de EDI|  
|[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|Adaptador de EDI base|  
|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]|Adaptador de EDI base|  
|[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|Funcionalidad nativa de EDI|  
  
## <a name="feature-set-comparison-chart"></a>Comparación de conjunto de características  
 En la tabla siguiente se muestra la compatibilidad con EDI que proporcionan los componentes y características de EDI en las versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. ‘S’ significa que la característica es compatible; ‘N’ significa que no es compatible.  
  
|Característica|[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] - [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] - [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]|BizTalk Server 2009|BizTalk Server 2010|Comentario|  
|---|---|---|---|---|---|---|  
|Modificación del segmento ISA en el conjunto de transacciones|S|N|S|S|S|Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior con la creación de acuerdos específicos de conjuntos de transacciones.|  
|ISA11: Estados Unidos u otros estándares|S|N|S|S|S|-|  
|ISA12: Versión de Control de intercambio|S|N|S|S|S|-|  
|ISA13: Número de Control de intercambio (aumento del número)|S|N|S|S|S|-|  
|ISA15: Prueba o producción|S|N|S|S|S|-|  
|Modificación del segmento GS en el nivel de documento o transacción|S|N|S|S|S|-|  
|GS remitente/receptor de GS permitido sea distinto a ISA|S|N|S|S|S|-|  
|Identificadores de documento de entrada distinto de ISA y GS de salida|S|N|S|S|S|-|  
|GS01: Capacidad para cambiar el tipo de documento|S|N|S|S|S|-|  
|GS04: Fecha (posibilidad de cambiar el formato)|N|N|S|S|S|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior contiene opciones de interfaz de usuario para seleccionar el formato como CCAAMMDD y AAMMDD|  
|GS05: Hora (posibilidad de cambiar el formato)|N|N|S|S|S|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior contiene opciones de interfaz de usuario para seleccionar el formato como HHMM, HHMMSS y HHMMSSdd|  
|GS06: Cambiar el número de control|S|N|S|S|S|-|  
|GS07: Agencia código|S|N|S|S|S|-|  
|GS08: Posibilidad de colocarlo en versiones estándar|S|N|S|S|S|-|  
|Capacidad de reemplazar el sobre EDI en tiempo de ejecución|N|N|N|S|S|-|  
|Esquemas EDI personalizados|S|N|S|S|S|-|  
|Organización/configuración de entidades|S|S (mínimo)|S|S|S|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y BizTalk Server 2009 permiten crear entidades a partir de plantillas.<br /><br /> BizTalk Server 2010 y posterior las remodela separando la entidad y los acuerdos. Permite crear acuerdos a partir de plantillas.|  
|Enrutamiento a través de la definición de documento de documentos EDI|S|-|S|S|S|-|  
|Confirmaciones 997 automáticas a socios comerciales|S|S|S|S|S|Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y BizTalk Server 2009 mediante la configuración específica de la entidad.<br /><br /> Compatible con BizTalk Server 2010 y posterior mediante la configuración específica para perfiles de negocio.|  
|Confiable de mensajería a través de 997 de salida EDI|S|S|S|S|S|-|  
|Compatibilidad con EDIFACT|S|S (mínimo)|S|S|S|Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior (de D93 a D05 para ISO 9735 v4.1)|  
|Admitir X12|S|S (mínimo)|S|S|S|Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior (de 2040 a 5030)|  
|Compatibilidad con HIPAA|N|S (en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)])|S|S|S|Compatible con [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] como acelerador de Microsoft BizTalk para HIPAA (BTAHIPAA) 3.3. Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior como parte de la funcionalidad EDI nativa.|  
|Capacidad de quitar enumeradores/listas de códigos|S|N|S|S|S|Compatible con [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior mediante el editor de Visual Studio/BizTalk|  
|AS2 Envío y recepción|N|N|S|S|S|En BizTalk Server 2009 y posterior, AS2 es el certificado Drummond para la compatibilidad con varios archivos adjuntos, la compatibilidad con la conservación de nombres de archivo y la interoperabilidad.|  
|Conservación de nombre de archivo de AS2|N|N|N|S|S|-|  
|Mensajería confiable de AS2|N|N|N|S|S|-|  
|Puede migrar [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] esquemas XDR EDI personalizados al repositorio EDI.|-|N|N|N|N|Debe migrar las aplicaciones EDI base a [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] o BizTalk Server 2009 y, a continuación, usar la herramienta Migración de entidades para migrar las aplicaciones a BizTalk Server 2010 y posterior.|  
|Procesamiento por lotes (acumulación de varios tipos de transacciones en una única transacción)|N|N|S|S|S|BizTalk Server 2009 y posterior admiten varias configuraciones de proceso por lotes para cada perfil de negocio.|  
|Entrada de procesamiento por lotes: intercambio XML (conservar un intercambio "por lotes" entrante) o el XML de conjunto de transacciones basado en las opciones de configuración|N|N|S|S|S|En [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] y posterior, esta es una adición a la compatibilidad de la anulación de procesamiento por lotes de entrada, es decir, la división de intercambios en archivos XML de conjunto de transacciones individuales.|  
|Intercambio y conjunto de transacciones generación y validación en tiempo de diseño en Visual Studio|N|N|S|S|S|-|  
|Conciliación y generación de TA1 (confirmación técnica)|N|N|S|S|S|-|  
|Marcas de validación XSD y EDI opcional|N|N|S|S|S|-|  
|Formato de documento/definición en nivel GS|N|N|S|S|S|-|  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con los estándares EDI](../core/edi-standards-support.md)   
 [Compatibilidad con esquema de documento EDI](../core/edi-document-schema-support.md)   
 [Compatibilidad con juego de caracteres de EDI](../core/edi-character-set-support.md)